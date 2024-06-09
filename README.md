#### <a name="_73bw7qk466o"></a>**Real Estate Management System** 

1. **Admin part**

- Creation of a map to better understand the nuances of the project: <https://lucid.app/lucidchart/02728596-8c92-4316-aae5-067e1625f0ca/edit?invitationId=inv_72e37f54-ffc5-4dd5-9b28-88e8e057088b&page=HWEp-vi-RSFO#>
- Start to change the name of the existing standard objects to our interpretation of the object that might be necessary to this project:
  - Product → Property
  - Lead → Client inquiries
  - Account → Client
  - Opportunity → Transactions
  - Creation of the fields of the objects modified:
- **Property:**
  - Name: Text
  - Location: Text
  - Rooms: Number
  - Price: Currency
  - Property type: Text
  - Availability: Checkbox
- **Client inquiries:**
  - Property name: lookup relationship with Property
  - Location: Formula field equals Location in Property
  - Price: Formula field equals Location in Property
  - Property type: Formula field equals Location in Property
  - Client Name: The same field that was in the Lead
  - Rating: The same field that was in the Lead
- **Client:**
  - Client Name: The same field that was in the Account
  - Phone: Phone
  - Email: Email
- **Transactions:** Modification of the opportunity process and adapted to transactions:
  - Visit
  - Proposition
  - Negotiation
  - closed lost
  - closed won





2. **Automatization part:**
- **Screen flow:**
- Creation of a screen flow that allows the client to check the availability of an estate and fill in his information into the system:
  - Creation of a variable that returns the property fields
  - Creation of a screen element with a check box component that returns the check availability field in the property.
  - Creation of a get record component that researches the available estate in the property
  - Creation of another screen element that puts every available estate in the data table component with the property's name and the price filed.
  - Creation of another screen element that allows the client to fill in his personal information into the system and automatically show the estate that he chooses in the data table component
  - Creation of a Create records element that puts every personal information in the client inquiries object fields to create a new client inquiry.
- **Experience Cloud**:
- Creation of an experience cloud site, adding the screen flow to the site and making it visible to the guest user:
  - To create an experience cloud site we need to write digital experience in the quick find in setup and then click new
  - We choose a template for our site
  - We add the screen flow to the site
  - We configure the site to make it visible to the guest user:
  - In the site builder, we go to settings and check the Guest users can see and interact with the site without logging.
  - We go to the guest user profile and add the screen flow in the Acces flow area.
  - We publish the site and open it in a private window.
- **Queues:**
- Creation of a queue that will assign the new client inquiry that came from the web to an agent:
  - Creation of the queue in Queues and making it active
  - Go to the assignment rule and assign the queue to the assignment rule.
  - In the assignment rule assign the appropriate profiles and fit in the proper criteria with the lead source equals the Web.
- **Record-Triggered flow:**
- Creation of a Record-Triggerd flow that will get the queue created to be triggered every time a client inquiry record is created and comes from the web: 
  - Creation of a Record-Trigger flow that will be triggered when a client inquiry is created and comes from the web.
  - Creation of a get-record element that will get the queue created by name
  - Creation of an update-record element that will update the owner ID of the client inquiry with the owner ID of the queue. 
