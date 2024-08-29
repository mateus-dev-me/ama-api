# **AMA API**

![Go Version](https://img.shields.io/badge/go-v1.23.0-blue) ![License](https://img.shields.io/badge/license-MIT-green)


> A REST API developed in Golang for managing questions and answers, similar to an AMA (Ask Me Anything) system. The API allows users to ask questions and have those questions answered by administrators.

## **Index**

1. [Project Overview](#project-overview)
2. [Project Structure](#project-structure)
3. [Installation](#installation)
4. [Usage](#usage)
5. [API Documentation](#api-documentation)
6. [Contribution](#contribution)

## **Project Overview**

This project aims to provide a platform where users can ask questions and get answers. It is ideal for scenarios where audience interaction is valued, such as Q&A sessions, discussion forums, or online communities.

### **Main Features:**
- User registration and authentication.
- Creation, reading, updating and deletion (CRUD) of questions and answers.
- Filtering and searching questions by tags and categories.
- Moderation of questions and answers.
  
## **Project Structure**

```bash
.
├── internal
│   ├── api
│   │   ├── spec
│   │   │   └── swagger.json
│   │   ├── utils.go
│   │   └── api.go
│   └── store
│       └── pgstore
│           ├── models.go
│           ├── queries
│           │   └── queries.sql
│           ├── queries.sql.go
│           ├── migrations
│           │   ├── tern.conf
│           │   ├── 002_create_messages_table.sql
│           │   └── 001_create_rooms_table.sql
│           ├── sqlc.yaml
│           └── db.go
├── docs
│   ├── 01.jpg
│   ├── 02.jpg
│   └── 03.jpg
├── cmd
│   ├── tools
│   │   └── terndotenv
│   │       └── main.go
│   └── app
│       └── main.go
├── gen.go
├── go.mod
├── go.sum
├── Dockerfile.yml
├── compose.yml
├── .env.example.yml
└── README.md
```
## **Installation**

### **Prerequisites:**

- **Go** (version 1.23.0 or higher)
- **Docker** (for containerized setup)
- **PostgreSQL** (or other supported database)

### **Installation Steps:**

1. Clone the repository:

    ```bash
    git clone https://github.com/mateus-dev-me/ama-api.git
    cd ama-api
    ```

2. Set environment variables:

Create a `.env` file based on the `.env.example` file and set your credentials and database parameters.

3. Install dependencies:

    ```bash
    go mod tidy
    ```

4. Perform database migrations:

    ```bash
    go generate
    ```

## **Usage**

### **Start Server:**

```bash
go run ./cmd/app/main.go
```
The API will be available at `http://localhost:8080/api`

## API Documentation

The documentation file is at `./internal/api/spec/swagger.json`

![Tag Room](./docs/01.jpeg) 
![Tag Messages](./docs/02.jpeg) 
![Tag Replies](./docs/03.jpeg) 

## **Contribution**

1. Fork the project.
2. Create a branch for your feature (git checkout -b feature/nova-feature).
3. Commit your changes (git commit -m 'Add new feature').
4. Push your branch to the remote repository (git push origin feature/nova-feature).
5. Open a Pull Request.


