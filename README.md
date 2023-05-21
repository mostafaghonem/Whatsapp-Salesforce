# Whatsapp-Salesforce
a package for Whatsapp integration with Salesforce that adds the capability of sending and receiving text messages from Salesforce to the phone number of any Contact or Lead in the Org.

## After Installation Instructions:
### Salesforce
* Create a new Site and make the default Web Address: "yourSiteURL/WA", check the active checkbox
  * Eneter the created Site.
  * click Public access Settings.
  * Apex Class Access
  * then add WA_webhook
* add in the Salesforce Org -> custom Labels:
  * add your WA permenant token to this Label "WaPermnantToken"
  * add any Token to this Label "WaWebhoohToken"
### Whatsapp
* add in the WA webhook
  * Callback URL: yourSiteURL/WA/services/apexrest/whatsapp/webhook/v1/
  * Verify token: the Token you added in the Custom Label "WaWebhoohToken"
