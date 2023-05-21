# Whatsapp-Salesforce
a package for Whatsapp integration with Salesforce that adds these capabilities:
* Send a template message for the phone Number of any Contact or Lead in the Org
* Receive the replies from the Contacts and Leads
* Receive Message from Phone number does not saved to the system and create a new Contact with this number with name of this Phone number WA profile name.
* Update the status of the sent messages (ex: Delivered, Received, and Seen)
* Send a custom message during the 24 hours after the Contact or the Lead replies to the Template Message
* Send template messages to all campaign members in a campaign

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
## Add the WA approved Template message to Salesforce to Use it
 add new record in WA Template Object:
* Name: the approved WA template name (ex: hello_world)
* Request body: the request body of the approved template (ex: { "messaging_product": "whatsapp","to": "whatsappNumber","type": "template","template": {"name": "hello_world","language": {"code": "en_US"}}} )
* Save, then you will find it in the drop down box of the LWC to send it as a template message
