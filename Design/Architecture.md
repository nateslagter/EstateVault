```mermaid
classDiagram
      DocumentController <|-- DocumentService
      NotificationController <|-- NotificationService
      UserController <|-- UserService
      UserService <|-- UserRepo
      NotificationService <|-- NotificationRepo
      DocumentService <|-- DocumentRepo
      UserService <|-- User
      DocumentService <|-- Document
      DocumentService <|-- User
      class DocumentService{
          
      }
      class NotificationService{
          
      }
      class UserService{
          
      }
```
