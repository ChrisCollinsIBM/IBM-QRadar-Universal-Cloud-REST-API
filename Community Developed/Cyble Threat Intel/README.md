Author Name: Cyble Inc

Maintainer Name: developers@cyble.com

Version Number: 1.0

Endpoint Documentation: This workflow can be used to pull alerts/events from Cyble Vision.

Detailed documentation can be found at: https://cyble.ai/centers/help-center

Event Types Currently Supported by the workflow: Cyble Threat Intel Alerts

## Workflow Parameter Description

For integrating QRadar with Cyble Vision via the workflow, you will need following information:

| **Parameter Label** | **Parameter** | **Description**                                                                                                             |
|---------------------|---------------|-----------------------------------------------------------------------------------------------------------------------------|
| Hostname            | hostname      | Enter _hostname_ of Cyble Vision. Contact your Customer Success Manager to get this value.                                  |
| Api Key             | api_key       | Enter _api_key_ for authentication and fetching events from Cyble. Contact your Customer Success Manager to get this value. |
| Fetch Since         | fetch_since   | Enter _fetch_since_ (number of days) for retrieving previous days' data on the first run.                                   |

## QRadar Log Source Configuration

If you want to ingest data from an endpoint using Universal Rest API Protocol, configure a log source on the QRadar® Console using the Workflow field so that the defined endpoint can communicate with QRadar by using the Universal Rest API protocol.

1. Log in to QRadar. 
2. Go to the admin panel, click on the _QRadar Log Source Management_ app icon. 
3. Click _New Log Source_ > Single Log Source. 
4. On the _Select Log Source Type_ page, select _Universal DSM_, and go to Step 2. 
5. On the _Select Protocol Type_ page, select _Universal Cloud REST API_, and go to Step 3. 
6. On the Configure the Log Source parameters page, configure the log source parameters:
    - Insert a name for this log source (_Cyble Threat Intel_);
7. On the Configure the Protocol Parameters page, configure:
    - Insert a log source identifier (*cyble_threat_intel*);
    - Copy the Workflow XML you downloaded from Cyble Threat Intel panel and paste it into the *Workflow* field;
    - Copy the Workflow Params (make sure your _hostname_, _api_key_ & _fetch_since_ are populated) into the *Workflow Parameters Values* field;
    - Set Recurrence as per your choice. Recommended value is 30M. 
8. In the Test protocol parameters window, click _Start Test_. All tests should pass.
9. To fix any errors, click _Configure Protocol Parameters_. Configure the parameters and click Test Protocol Parameters. 
10. Click _Finish_
11. Navigate to the __Admin__ tab. From the top bar choose __Deploy Changes__
