# Handling Secure Data

When moving data to sandboxes, and copying production data, it's important to hide / encrypt secure information of users, such as SSN, passwords, and anything else people could use maliciously.

As of now, masking data is limited with current toolsets, however, there are methods that are available and commonly used on the SalesForce market place, as well as 3rd party applications that can allow you more flexibility with how you want to manage secure data.

### Methods to Hide Secure Data

* Use the SandboxPostCopyInterface and write your own apex class that implements method runApexClass\(context\). This can kick off a batch class to do the anonymization. allows you to run an Apex class as soon as the sandbox is refreshed. Use that class to run a batch class that makes your data encrypted.
* Vendor appexchange solution like OwnBackup[https://appexchange.salesforce.com/listingDetail?listingId=a0N30000007p6RYEAY](https://appexchange.salesforce.com/listingDetail?listingId=a0N30000007p6RYEAY)
* Informatica has a product for managing sandboxes and cleaning data[https://blogs.informatica.com/2018/02/08/choose-informatica-cloud-test-data-management-for-your-salesforce-security-model/\#fbid=YSF\_UYEgXDd](https://blogs.informatica.com/2018/02/08/choose-informatica-cloud-test-data-management-for-your-salesforce-security-model/#fbid=YSF_UYEgXDd)
* Create permissions so non-admins can't see that stuff
* On the standard user object, create an encrypted custom field to store the user's Social Security number. Set the field's Mask Type attribute to hide the first five digits of the social security number, and add field-level help to inform users of the required format. Then, create a validation rule that uses the REGEX\(\) function to verify that the value of the custom field is in the correct format. Finally, create a new custom profile that allows a select group of users to the see the Social Security numbers unmasked.
  * For more information, visit [here](https://developer.secure.force.com/cookbook/recipe/storing-and-displaying-confidential-information)
* Create two new fields to hold the address and phone number of these specific contacts and then in the Field Level Security of those contacts set the fields to not visible for your standard user profile.
  * **Benefits:** these users won't be able to view the field through any means, even through reports or API tools.
* Using the [Dataloader](https://dataloader.io/), you can mass update the records to remove any sensitive data. This is a manual process though, and it will need to be done each time the sandboxes are refreshed.
* [Encrypt Custom Fields](https://help.salesforce.com/articleView?id=fields_about_encrypted_fields.htm&type=5) & Restrict other Salesforce users from seeing custom text fields you want to keep private. Only users with the permission “View Encrypted Data” can see data in encrypted custom text fields.

