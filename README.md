Craftnote records API

#Overview
The Craftnote records API is a secure and scalable RESTful API that enables users to manage note records in a database.
It supports full CRUD operations — Create, Read, Update, and Delete — following MuleSoft’s contract-first design principle using RAML specifications.

This project demonstrates best practices in MuleSoft API development, including security, error handling, CI/CD, and environment management.

---

##  Features
- RESTful endpoints for note management
- RAML-based API specification
- Secure client credentials authentication
- Encrypted credentials in configuration files
- Environment-specific configurations (Dev)
- CI/CD enabled through Anypoint Platform
- Error handling and reconnection strategies
- Minimum 75% MUnit test coverage

---

API Endpoints

 Method      Endpoint        Description 
--------|------------------------
 GET       api/notes             Retrieve all notes. Ensures `updatedAt` is not null.
 ______________________________________________________________________________________________________ 
GET        api/notes/{noteId}    Retrieve a note by `noteId`. 
________________________________________________________________________________________________________________
POST      api/notes        Create a new note with required fields (`id`, `title`, `content`, `createdAt`, `updatedAt`).
__________________________________________________________________________________________________________________ 
PUT       api/notes/{noteId}   Update an existing note or create it if it doesn’t exist.
_______________________________________________________________________________________________________________ 
DELETE    api/notes/{noteId}`  Delete a note by `noteId`. 
_______________________________________________________________________________________________

Example Request Body (POST/PUT)

```json
{
  "title": "Project Notes",
  "content": "Initial design and database structure discussion."
}
```

---
 Database Configuration

Field            Type            Details 
------------------------------------
`Id`             INT              Primary key, auto-increment (starts at 101) 
___________________________________________________________________________________
`title`          VARCHAR(50)      Note title 
____________________________________________________________________________________
`content`      VARCHAR(250)       Note content 
____________________________________________________________________________________
`createdAt`    TIMESTAMP          Note creation time 
_____________________________________________________________________________________
`updatedAt`     TIMESTAMP         Note update time 
_____________________________________________________________________________________

Connection Details
```
Host: localhost
Schema: craftsoftNotes
Username: root
Password: YOUR_PASSWORD

Security
- Uses Client Credentials Flow for authentication.
- All passwords and API keys are encrypted and masked in configuration files.
- Sensitive data is never logged or exposed in runtime.

---

Development Guidelines
- Use RAML for API specification (contract-first design).
- Apply Enterprise Data Model principles.
- Conduct API mocking and consumer testing before implementation.
- Maintain API versioning and detailed documentation.
- Define error handling frameworks and reconnection strategies in flows.

---

Testing
- Use **MUnit** for unit and integration testing.
- Achieve **≥ 75% coverage** across flows.
- Validate API behavior with mocked endpoints.

---

Deployment & Environments
-An environment: Development
- Manage lifecycle through MuleSoft Anypoint Platform.
- Maintain environment-specific property files for each stage.

---

Documentation & Support
- API documented fully in RAML specification.
- Include request/response examples and error codes.
- Provide user support channels for consumer feedback.

---

Technologies Used
- MuleSoft Anypoint Studio
- RAML 1.0
- MySQL / Online DB
- MUnit Testing Framework
- CI/CD with Anypoint Platform

---

Contributors
Team members: Wudineh, Tiruwork, Birhanie, Helina and Tesfaye  
Project Date: October 13, 2025
