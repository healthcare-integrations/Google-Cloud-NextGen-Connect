<p align="center">
  <img src="https://healthcareintegrations.com/images/logos/HealthcareIntegrations.png" width="455" height="124">
</p>

# Google-Cloud-NextGen-Connect

This is a NextGen Connect (formerly known as Mirth Connect) channel that allows you to transmit HL7 2.x messages to the Google Cloud Healthcare API. Prior knowledge of HL7 and NextGen Connect is encouraged but not required.


## Prerequisites
* [NextGen Connect (Mirth Connect) Version 3.7.0 (runs on Windows, Linux, and OS X)](https://www.nextgen.com/products-and-services/NextGen-Connect-Integration-Engine-Downloads)
* [A Google Cloud Account](https://cloud.google.com/)
* [Access to the Google Cloud Healthcare API](https://cloud.google.com/healthcare/)
* [A Service Account with the 'Healthcare HL7v2 Message Ingest' role](https://cloud.google.com/iam/docs/creating-managing-service-accounts)
* [The Service Account Keyfile (JSON file) for the Service Account](https://cloud.google.com/iam/docs/creating-managing-service-account-keys)
* [A Google Healthcare API Dataset](https://cloud.google.com/healthcare/docs/how-tos/datasets)
* [A Google Healthcare API HL7v2 Store](https://cloud.google.com/healthcare/docs/how-tos/hl7v2)

### Installation of NextGen Connect
Installation of NextGen Connect is outside of the scope of this document. Installation varies depending on the OS and your environment. If you need help installing NextGen Connect, Healthcare Integrations offers installation guidance, support, and troubleshooting at an hourly rate. We provide as much or as little support as you need. 

Contact us at:

[https://wwww.healthcareintegrations.com](https://wwww.healthcareintegrations.com)

<a href="mailto:Contact@healthcareintegrations.com">Contact@HealthcareIntegrations.com</a>

### Importing the channel into NextGen Connect
Download the file named "Google Healthcare API.xml" from this Repo. This is the channel that will be imported into NextGen Connect.

Once you are logged into NextGen Connect, click on Channels:
![Dashboard](/Images/Dashboard.png)

Click on Import Channel, then select the saved XML file from this GitHub Repo and import it:
![Channels](/Images/Channels.png)

Click on the Source tab at the top of your screen:
![Source](/Images/Source.png) 

Click on Edit Transformer:
![Transformers](/Images/Transformers.png)

In the first Transformer, update the following settings:
* API_VERSION (only if needed)
* PROJECT_ID
* LOCATION_ID
* DATASET_ID
* HL7_STORE_ID
![Step1](/Images/Step1.png)

In the second Transformer, either paste in your JSON key matching the same format as the example, or provide the path to the JSON key on the system where NextGen Connect is installed:
![Step2](/Images/Step2.png)

Click Back to Channel in the top left.
![Back](/Images/Back.png)

Update your settings here to match how you are sending HL7 data to this channel. A typical setup uses a TCP listener to receive HL7 messages from an EMR or other system, or reads HL7 messages as files in a specified folder. NextGen Connect provides many different options for receiving data.

Once your changes are made, click Deploy Channel under Channel Tasks:
![Deploy Channel](/Images/Step3.png)

Your channel is now live and ready to start receiving data. We suggest sending some test messages to ensure the channel is working as it should be. You can use the following sample HL7 message for testing:

```
MSH|^~\&|FROM_APP|FROM_FACILITY|TO_APP|TO_FACILITY|20150503223000||ADT^A01|20150503223000|P|2.5|
EVN|A01|20110613083617|
PID|1|843125^^^^MRN|21004053^^^^MRN||SULLY^BRIAN||19611209|M|||123 MAIN ST^^MOUNTAIN SPRINGS^CO^80439|
PV1||I|H73 RM1^1^^HIGHWAY 73 CLINIC||||5148^MARY QUINN|||||||||Y||||||||||||||||||||||||||||20150503223000|
```


## Useful links
* [Google Healthcare API Documentation](https://cloud.google.com/healthcare/docs/)
* [Google Healthcare API Authentication Documentation](https://cloud.google.com/healthcare/docs/how-tos/authentication)
* [NextGen Connect User Guide](https://bridge.nextgen.com/media/3244/)

## Older Versions of NextGen Connect/Mirth Connect

The current channel is only supported by NextGen Connect Version 3.7.0 or newer. If you are running an older version of NextGen Connect/Mirth Connect, please contact us at Contact@HealthcareIntegrations.com with your version number and we will provide a version to you. Alternatively, please create a new Issue in this repo and specify your version number there. We will add additional versions to this repo as needed.

