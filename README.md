# Whatsapp-Salesforce
a package for Whatsapp integration with Salesforce that adds these capabilities:
* Send a template message for the phone Number of any Contact or Lead in the Org
* Receive the replies from the Contacts and Leads
* Receive Message from Phone number does not saved to the system and create a new Contact with this number with name of this Phone number WA profile name.
* Update the status of the sent messages (ex: Delivered, Sent, and Seen)
* Send a custom message during the 24 hours after the Contact or the Lead replies to the Template Message
* Send template messages to all campaign members in a campaign
## Components:
### Objects:
* WA_message: hold inbound and outbound WA messages related to a Contact or Lead
* WA_template: hold approved WA template messages to be used
### LWC
* whatsappIntegration: to select from the approved template messages and send it (for Contact or Lead).
* sendCustomMessages: to send custom message (for Contact or Lead).
* whatsappForCampagin: to send template messages for the campagin members.

# After Installation Instructions:
### Salesforce
* Create a new Force.com Site and make the default Web Address: "yourSiteURL/WA", check the active checkbox
  * Eneter the created Site.
  * click Public access Settings.
  * Apex Class Access
  * then add WA_SF.WA_webhook
* add in the Salesforce Org -> custom Labels:
  * add your WA permenant token to this Label "WaPermnantTokenn"
  * add any Token to this Label "WaWebhoohTokenn"
  * add the Phone Number Id to this Label "WaPhoneNumberIdd"
  * add the Whatsapp App secret from the app setting --> basic to this Label "AppSecrett"
### Whatsapp
* add in the WA webhook
  * Callback URL: yourSiteURL/WA/services/apexrest/WA_SF/whatsapp/webhook/v1/
  * Verify token: the Token you added in the Custom Label "WaWebhoohToken"
## Add the WA approved Template message to Salesforce to Use it
 add new record in WA Template Object:
* Name: the approved WA template name (ex: hello_world)
* Request body: the request body of the approved template (ex: { "messaging_product": "whatsapp","to": "whatsappNumber","type": "template","template": {"name": "hello_world","language": {"code": "en_US"}}} )
* Save, then you will find it in the drop down box of the LWC to send it as a template message

