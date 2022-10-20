## Actors
- Client
- Beneficiaries
- Estate Administrator
- Family of the client
- Professionals
  - Attorney(s)
  - Account
  - Financial Advisor
  - Trustee
- Future MoneyTree software

## Use Cases

- Organize Estate Documents
  - UC1
  - System: Document storage
  - Primary actor: Client
  - This function is the main aspect of our system. A client should be able to access their account and store their assets, whatever they may be, and allow other people to have access to these assets.
  - The client logs into their account. They are prompted with a checklist to upload a set of documents that are necessary or important for their estate. They upload a new document into the system. They remove a document that is no longer up to date. The client adds contacts that can view certain documents, such as their attorney and financial advisor. They give specific permissions to each contact to regulate access to confidential documents.
  - Business requirement: BR1, BR2

- View Client's Documents
  - UC2
  - System: Document storage
  - Primary actor: Legal document professional
  - One of the main business requirements is to allow legal professionals, such as attorneys, to view certain documents as allowed by the client.
  - The professional receives an invitation from a client to add them to their network within the vault. This gives the professional access to a number of documents that the client has previously specified. The professional can check if the document is properly formatted and can contact the client about any issues.
  - Business requirement: BR1, BR2

- Create Professional Account
  - UC3
  - System: Document Storage
  - Primary actor: Legal document professional
  - One of the main business requirements is to allow legal professionals to review documents, and it is likely a professional may have access to multiple clients' documents.
  - The professional hears about EstateVault from a colleague and decides to create an account proactively with the intention of helping set up a client in the future.  They are set up with an account and wait for their client to invite them to their network.  Until this happens, the professional will have no actions on the account.  When the professional is added, they can select any of their clients to review documents and make any changes and contact the client about any issues.
  - Business requirement: BR2

- View Family Documents
  - UC4
  - System: Document Storage and Account Review
  - Primary actor: Family of estate owner
  - One of the business requirements brought to us was the ability to allow family, in the form of heirs, estate admins, etc., to view the clients documents. One things brought up several times was the importance of storage for usernames and passwords on various sites like Facebook, Twitter, bank accounts, etc.
  - The son of an estate owner logs into his account following the death of his father.  He navigates to the documents containing the login information for his father's Facebook.  He finds that information as well as a step by step guide to deleting the Facebook account.  
  - Business requirement: BR1, BR2

- Document Access Control
  - UC5
  - System: Document Access Control
  - Primary actor: Client/Estate Owner
  - One of the business requirements brought to us was the ability for a client to manage the outside access to their estate documents with legal professionals and anyone the client believes should be able.
  - The client logs into the estate vault and navigates to the documents tab.  They click on their will and choose to share access with their attorney.  From here, the attorney is able to accept access and review the will.  The client can see the will is shared with their attorney and can revoke access or add new viewers at any time.
  - Business requirement: BR1, BR2

- Notifications
  - UC6
  - System: Notification System
  - Primary actor: Client
  - One of the business requirements was in reference to a notification system used to make clients aware when documents have been unchanged or missing for too long.
  - The client sets up an account and adds a number of documents.  A couple of months go by with no changes, and the system emails the client asking them to log in and review or update their will just in case something has changed.  When the client logs back in, the notification tab lets them know there is a new notification.  Clicking this notification will navigate them to the documents needing review.
  - Business requirement: BR1, BR2

- Mobile Website
  - UC7
  - System: Mobile Friendly Website
  - Primary actor: Client
  - One of the first thing brought up during the discovery meeting was the importance of a website that can be viewed easily from a mobile device.
  - A client logs into their estate vault from their mobile phone.  The mobile website has a very similar flow to the desktop version aiding a smooth transition from one to the other.  The buttons are big enough to read and click without trouble.
  - Business requirement: BR1, BR2, BR3

- Client Account Creation
  - UC8
  - System: Account Creation
  - Primary actor: Client
  - In order for the entire system to function, the client needs a way to create an account and manage it.
  - A client visits the EstateVault website and chooses to sign up for an account.  They enter an email and a password as well as some personal information like name and phone number.  Once the account is set up, they can navigate to their account page on the dashboard and change the password or email associated with their account.
  - Business requirement: BR1, BR2, BR3
