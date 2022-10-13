```mermaid
classDiagram
      DocumentController -- DocumentService
      NotificationController -- NotificationService
      UserController -- UserService
      UserService -- UserRepo
      NotificationService -- NotificationRepo
      DocumentService -- DocumentRepo
      UserService -- User
      DocumentService -- Document
      DocumentService -- User
      User <|-- Client
      User <|-- Legal Professional
      User <|-- Other
      NotificationController <.. Notifier Live Service
      
      class DocumentController{
      The DocumentController processes requests sent to the Document endpoint of the API.
      It is used to retrieve documents pertaining to the query sent.
      +getAllDocuments()
      +getDocument()
      }
      
      class NotificationController{
      The NotificationController processes requests sent to the Notification endpoint of the API.
      It is necessary for the Notifier MicroService to actually send notifications.
      +user: User
      +sendNotification() 
      }
      
      class UserController{
      The UserController processes requests sent to the User endpoint of the API.
      +getUser() User
      +createUser(user info)
      +deleteUser(user info)
      +editUser(user info)
      }
      
      class DocumentService{
      The DocumentService class handles logic between Controller and Repo layers. 
      It handles the object-relational mapping.
      +getAllDocuments()
      +getDocument()
          
      }
      class NotificationService{
      The NotificationService class handles logic between Controller and Repo layers. 
      It handles the object-relational mapping.
      +sendNotification() 
          
      }
      class UserService{
      The UserService class handles logic between Controller and Repo layers. 
      It handles the object-relational mapping.
      +getUser() User
      +createUser(user info)
      +deleteUser(user info)
      +editUser(user info)
          
      }
      
      class NotificationRepo{
      Queries the DB to retrieve data for notifications.
      +queryWhenNotificationLastSent()
      
      }
      
      class DocumentRepo{
      Queries the DB for documents relating to the query.
      +queryDocuments()
      +querySpecificDocument(String documentId)
      +insertNewDocument(Document document)
      +updateDocument(String documentId)
      +deleteDocument(String documentId)
      }
      
      class UserRepo{
      Queries the DB for user objects.
      +queryUser(User user)
      }
      
      class Document{
      The document object holds a file relating to a client. 
      +File document
      +String documentName
      +String documentId
      +getDocumentName() String
      +changeDocumentName(String newName)

      }
      
      class User{
      The user object holds a user's information such as name, login information, and accessibility preferences.
      +String firstName
      +String lastName
      +AccessibilitySettings accessibilitySettings
      +getAccessibilitySettings() AccessibilitySettings
      +setAccessibilitySettings() 
      }
      
      class Client{
      User who hires an attorney to review documents.
      +List~Legal Professional~ legalProfessionalList
      }
      
      class Legal Professional {
      Professional who reviews legal documents.
      +List~Client~ clientList
      }
      
      class Other{
      Family/friends of client, who are allowed to view certain documents.
      +List~Client~ clientList
      }
      
      class Notifier Live Service{
      Live service, seperate from this API, that utilizes the API to send notifications periodically to users of the system.
      }
```
