# vmware
Chat Code
<html>
    <head>
        <meta name="viewport" content="width=device-width, initial-scale=1, minimum-scale=1"/>
        <link rel="stylesheet" type="text/css" href="https://gsluat-vmware--gs.cs19.force.com/LiveAgent/servlet/servlet.FileDownload?file=015f4000001xd72&oid=00D290000009JpA" media="all"/>
    </head>
    <body>
        <script type='text/javascript' src='https://service.force.com/embeddedservice/5.0/esw.min.js'></script>
        <script type='text/javascript'>
            var initESW = function(gslbBaseURL) {
                embedded_svc.settings.displayHelpButton = true; //Or false
                embedded_svc.settings.language = ''; //For example, enter 'en' or 'en-US'

                embedded_svc.settings.defaultMinimizedText = 'Chat with Support'; //(Defaults to Chat with an Expert)
                embedded_svc.settings.disabledMinimizedText = 'Chat Support Offline'; //(Defaults to Agent Offline)

                embedded_svc.settings.loadingText = 'Loading...'; //(Defaults to Loading)
                //embedded_svc.settings.storageDomain = 'yourdomain.com'; //(Sets the domain for your deployment so that visitors can navigate subdomains during a chat session)

                // Settings for Chat
                //embedded_svc.settings.directToButtonRouting = function(prechatFormData) {
                    // Dynamically changes the button ID based on what the visitor enters in the pre-chat form.
                    // Returns a valid button ID.
                //};
                //embedded_svc.settings.prepopulatedPrechatFields = {}; //Sets the auto-population of pre-chat form fields
                //embedded_svc.settings.fallbackRouting = []; //An array of button IDs, user IDs, or userId_buttonId
                //embedded_svc.settings.offlineSupportMinimizedText = '...'; //(Defaults to Contact Us)

                embedded_svc.settings.enabledFeatures = ['LiveAgent'];
                embedded_svc.settings.entryFeature = 'LiveAgent';
                
                /*Variables defined for details to be displayed only in the current detail page*/
                var caseRecType = 'GS-SS Customer Support';
                var caseEnt = 'LICENT';
                
                /*Variables defined for Case details*/
                var caseOrigin = 'Chat MyVMware';
                var caseStatus = 'Open';
                var caseSubStatus = 'Assigned';
                var caseDesc = 'Enter Description Here';
                var caseSubj = 'Enter Subject Line Here';
                var caseSupLev = '1';
                var caseProbCat = 'Licensing';
                var caseSev = 'S3';
                var casePriority = '3 - Medium';
                var dcaId='001f400000ysvGr';
                var portalSession = '<Portal Session Key>';
                var isClosed = false;
                
                /*Added service name and other details to be displayed in the current detail page*/
                embedded_svc.settings.extraPrechatFormDetails = [
                    {"label": "First Name", "displayToAgent": true,"transcriptFields":["First_Name__c"]},
                    {"label": "Last Name", "displayToAgent": true,"transcriptFields":["Last_Name__c"]},
                    {"label": "Email", "displayToAgent": true,"transcriptFields":["Contact_Email__c"]},
                    {"label": "Phone", "displayToAgent": true,"transcriptFields":["Contact_Phone__c"]},
                    {"label": "Case Severity", "value": caseSev, "displayToAgent": true,"transcriptFields":["Case_Severity__c"]},
                    {"label": "Case Problem Category", "value": caseProbCat, "displayToAgent": true,"transcriptFields":["Case_Problem_Category__c"]},
                    {"label": "Case Entitlement", "value": caseEnt, "displayToAgent": true,"transcriptFields":["Case_Entitlement__c"]},
                    {"label": "Case Support Level", "value": caseSupLev, "displayToAgent": true,"transcriptFields":["Case_Support_Level__c"]},
                    {"label": "Case Record Type", "value": caseRecType, "displayToAgent": true,"transcriptFields":["Case_Record_Type__c"]},
                    {"label": "Case Origin", "value": caseOrigin, "displayToAgent": true,"transcriptFields":["Case_Origin__c"]},
                    {"label": "Case Status", "value": caseStatus, "displayToAgent": true,"transcriptFields":["Case_Status__c"]},
                    {"label": "Case Sub Status", "value": caseSubStatus, "displayToAgent": true,"transcriptFields":["Case_Sub_Status__c"]},
                    {"label": "Case Subject", "value": caseSubj, "displayToAgent": true,"transcriptFields":["Case_Subject__c"]},
                    {"label": "Case Description", "value": caseDesc, "displayToAgent": true,"transcriptFields":["Case_Description__c"]},
                    {"label": "DCA Account ID", "value": dcaId, "displayToAgent": false},
                    {"label": "Portal Session ID", "value": portalSession, "displayToAgent": false,"transcriptFields":["Portal_Session_ID__c"]},
                    {"label": "Case Priority", "value": casePriority, "displayToAgent": true,"transcriptFields":["Case_Priority__c"]},
                    {"label": "Case Closed", "value": isClosed, "displayToAgent": false}
                ];
                
                /*Maps the value with Case fields and creates a Case and also links to chat based on whether contact is null, existing or a user*/
				embedded_svc.settings.extraPrechatInfo = [{
					"entityFieldMaps": [
						{"doCreate":true, "doFind":true, "fieldName":"Email", "isExactMatch":true, "label":"Email"},
						{"doCreate":true, "doFind":false, "fieldName":"FirstName", "isExactMatch":false, "label":"First Name"},
						{"doCreate":true, "doFind":false, "fieldName":"LastName", "isExactMatch":false, "label":"Last Name"},
						{"doCreate":true, "doFind":false, "fieldName":"Phone", "isExactMatch":false, "label":"Contact Phone Number"},
						{"doCreate":true, "doFind":false, "fieldName":"AccountId", "isExactMatch":false, "label":"DCA Account ID"}
					],
					"entityName":"Contact",
					"saveToTranscript": "ContactId",
					"showOnCreate": true
				},
				{
															  "entityFieldMaps": [
																  {"doCreate": false,"doFind": true,"fieldName": "ContactEmail","isExactMatch": true,"label": "Email"},
																  {"doCreate": false,"doFind": true,"fieldName": "IsClosed","isExactMatch": true,"label": "Case Closed"}
															  ],
															  "entityName": "Case"
														  }];
			
                
                embedded_svc.init(
					'https://vmware-gs--gsluat.my.salesforce.com',
					'https://gsluat-vmware--gs.cs19.force.com/LiveAgent',
					gslbBaseURL,
					'00D290000009JpA',
					'CS_Chat_With_Pre_Chat_Page',
					{
						baseLiveAgentContentURL: 'https://c.la4-c1cs-phx.salesforceliveagent.com/content',
						deploymentId: '572290000008OtY',
						buttonId: '573290000008PUx',
						baseLiveAgentURL: 'https://d.la4-c1cs-phx.salesforceliveagent.com/chat',
						eswLiveAgentDevName: 'EmbeddedServiceLiveAgent_Parent04I290000004CUVEA2_174b467cb68',
						isOfflineSupportEnabled: false
					}
				);
			};

			if (!window.embedded_svc) {
				var s = document.createElement('script');
				s.setAttribute('src', 'https://vmware-gs--gsluat.my.salesforce.com/embeddedservice/5.0/esw.min.js');
				s.onload = function() {
					initESW(null);
				};
				document.body.appendChild(s);
			} else {
				initESW('https://service.force.com');
			}
        </script>
    </body>
</html>
