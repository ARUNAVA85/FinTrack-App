# FinTrack - A personal finance tracker application

A scalable Spring Boot backend for personal finance tracking, featuring JWT authentication, automated transaction management, and spending analytics.

## 🚀 Features

- **JWT Authentication**: Secure login and registration with access and refresh tokens.
- **Transaction Management**: Full CRUD operations for income and expenses.
- **Budget Tracking**: Customizable monthly budget allocation (defaults to 30% of income).
- **Categorization**: Automatic and manual categorization of transactions.
- **Spending Analytics**: Real-time summary of spending habits by category.
- **Webhooks**: Mock endpoints for automatic updates from banks/UPI.

## 🛠️ Tech Stack

- **Framework**: Java Spring Boot 3.2.0
- **Security**: Spring Security + JWT (jjwt)
- **Database**: PostgreSQL (Hibernate/JPA)
- **Object Mapping**: ModelMapper
- **Build Tool**: Maven

## 📋 Prerequisites

- Java 17
- Maven
- PostgreSQL Database

## ⚙️ Configuration

The application uses the following environment variables:

- `DATABASE_URL`: PostgreSQL connection string.
- `SESSION_SECRET`: Secret key for JWT signing.

Key settings in `src/main/resources/application.properties`:
- `jwt.access-token-expiration`: 30 minutes (1800000ms)
- `jwt.refresh-token-expiration`: 30 days (2592000000ms)

## 🏗️ Architecture

Following SOLID principles and clean architecture:
- `config`: Security, CORS, and general application configuration.
- `controller`: REST API endpoints.
- `dto`: Data Transfer Objects for API requests/responses.
- `entity`: Database models.
- `repository`: Data access layer.
- `service`: Business logic implementation.
- `security`: JWT filter, authentication provider, and custom user details.

## 🚦 API Endpoints

### Auth
- `POST /api/auth/register`: Create new account
- `POST /api/auth/login`: Authenticate user
- `POST /api/auth/refresh`: Refresh access token
- `GET /api/auth/profile`: Get current user details

### Transactions
- `GET /api/transactions`: List all transactions
- `POST /api/transactions`: Add new transaction
- `GET /api/transactions/summary`: Get dashboard stats
- `DELETE /api/transactions/{id}`: Remove transaction

### Categories
- `GET /api/categories`: List transaction categories
- `POST /api/categories`: Create new category

## 🧪 Development

To run the backend locally:
```bash
mvn spring-boot:run
```
