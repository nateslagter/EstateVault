# Domain Model
![Domain Model for First Iteration](https://github.com/nateslagter/EstateVault/blob/main/Design/DomainModelFirstIteration.jpeg)

## Class's

### User
- Any person using the system

### Non-Client Account
- A user who can only view documents that are shared with them.

### Clients
- A client is a user who is storing their files in the document vault.

### Client Documents
- Documents that a user has uploaded and given access to the non-client user to view.

### Profile
- A user creates a profile for which to be used when logging in to the site

### Account Information
- Basic information listed for the user account.

### Dashboard
- Displays the links to allow the user to access their document vault, assets & liabilities, account settings, checklist, contacts etc.

### Account Settings
- Displays basic settings for the account(i.e. Accessibility settings, notification settings, etc.).

### Checklist
- A list of task to be exectuted, allows the user to know what to do next from the dashboard.

### Contacts
- A list of people the user wishes to be able to share documents with, and/or store neccesary information to be able to contact them when neccesary.

### Documents
- Houses the pages for Personal and Estate documents for the user.

### Personal Documents
- A page that allows the user to browse/upload/delete/preview/download/rename files that pertain to their personal life that are necesary for the user.

### Estate Documents
- A page that allows the user to browse/upload/delete/preview/download/rename files that pertain to their estate that are neccesary for the user.

### Access Control
- Access control allows the user to choose a person from their contacts to grant access to view a document in their vault

### Upload/Delete Documents
- The user can upload a file they need, or delete a file that is no longer needed.
