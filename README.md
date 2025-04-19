# 🏥 Patient Management System

## 📋 Overview

A modern, microservice-based patient management system built with Spring Boot. This system provides a comprehensive solution for healthcare providers to manage patient information, billing, and analytics through a secure, scalable architecture.

## 🏗️ Architecture

This project follows a microservice architecture with the following components:

![image](https://github.com/user-attachments/assets/aef17f47-80fd-41c3-bbc4-545c6c1d45b6)


### 🧩 Key Components:

- **API Gateway**: Routes requests to appropriate services and handles authentication
- **Auth Service**: Manages user authentication and token validation
- **Patient Service**: Core service for patient data management
- **Billing Service**: Handles billing operations via gRPC
- **Analytics Service**: Processes patient data for reporting and insights

## 🚀 Features

- **Secure Authentication**: JWT-based authentication and authorization
- **Patient Management**: Create, read, update, and delete patient information
- **Service Communication**: Implements both REST APIs and gRPC for efficient service-to-service communication
- **Event-Driven Architecture**: Uses Kafka for event propagation between services
- **OpenAPI Documentation**: Each service includes Swagger documentation
- **Cloud-Ready**: Infrastructure as code using AWS CDK
- **Containerized**: Each service includes Dockerfiles for containerization

## 💻 Technology Stack

- **Backend**: Java 17, Spring Boot 3.4
- **APIs**: REST, gRPC
- **Database**: PostgreSQL
- **Event Streaming**: Apache Kafka
- **Documentation**: OpenAPI/Swagger
- **Infrastructure**: Docker, AWS CDK
- **Security**: JWT
- **CI/CD**: GitHub Actions, AWS CodePipeline

## 🔧 Getting Started

### Prerequisites

- Java 17+
- Maven
- Docker and Docker Compose
- AWS CLI (for deployment)

### Local Development

1. Clone the repository:

   ```bash
   git clone https://github.com/yourusername/patient-management.git
   cd patient-management
   ```

2. Build the services:

   ```bash
   mvn clean install
   ```

3. Start the services using Docker:

   ```bash
   docker-compose up -d
   ```

4. Access the API at `http://localhost:4004`

### API Documentation

Access Swagger UI for each service:

- Patient Service: `http://localhost:4004/api-docs/patients`
- Auth Service: `http://localhost:4004/api-docs/auth`

## 🔐 Authentication

1. Obtain a JWT token:

   ```
   POST /auth/login
   {
     "username": "admin",
     "password": "password"
   }
   ```

2. Use the token in subsequent requests:
   ```
   Authorization: Bearer <token>
   ```

## 📦 Service Details

### Patient Service

- **Endpoint**: `/api/patients`
- **Features**: CRUD operations for patient data
- **Communication**: Sends events to Kafka and communicates with Billing Service via gRPC

### Auth Service

- **Endpoint**: `/auth`
- **Features**: Authentication, token validation
- **Security**: JWT tokens with configurable expiration

### Billing Service

- **Protocol**: gRPC
- **Port**: 9001
- **Features**: Create billing accounts linked to patients

## 📚 Development Guidelines

- Follow RESTful API design principles
- Write comprehensive unit and integration tests
- Use proper error handling and logging
- Follow the established project structure
- Document all public APIs

## 📝 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 👥 Contributors

- [Your Name](https://github.com/yourusername) - Project Lead
