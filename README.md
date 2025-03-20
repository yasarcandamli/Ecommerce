# E-Commerce App

# Backend

## Overview

This project is a Spring Boot-based backend API for an e-commerce platform, offering essential functionalities such as user authentication, product and category management, shopping cart operations, and payment processing.

## Technologies Used

- **Spring Boot 3.4.0** - Backend framework

- **Spring Security** - Authentication & Authorization (JWT-based)

- **Spring Data JPA** - ORM for database operations

- **PostgreSQL** - Database

- **ModelMapper** - Object mapping

- **Lombok** - Code simplification

- **Stripe API** - Payment processing

- **Maven** - Dependency management

## Features

- User authentication & role-based access control (RBAC)

- Product management (CRUD operations, image upload)

- Category management

- Shopping cart operations (Add, remove, update items)

- Order processing & checkout

- Stripe payment integration

- JWT-based authentication & authorization

- Pagination & sorting for product queries

- Custom exception handling

## Project Structure

The project follows a standard Spring Boot structure.

## Installation & Setup

### Prerequisites

Ensure you have the following installed:

- Java 17

- PostgreSQL

- Maven

### Configuration

Create a `.env` file and set the required environment variables for the database and Stripe API.

### Running the Project

1. Clone the repository:

2. Navigate to the project directory:

3. Build and run the application:

4. The API will be available at `http://localhost:8080`

## API Endpoints

### Authentication

- `POST /api/auth/register` - Register a new user

- `POST /api/auth/login` - Authenticate user and receive a JWT token

### Products

- `POST /api/products/{categoryId}` - Add a new product

- `GET /api/products` - Retrieve all products (supports pagination & filtering)

- `GET /api/products/search?keyword={keyword}` - Search for products by name

- `PUT /api/products/{productId}` - Update product details

- `DELETE /api/products/{productId}` - Remove a product

### Categories

- `POST /api/categories` - Create a new category

- `GET /api/categories` - Retrieve all categories

### Cart

- `POST /api/cart/add/{productId}` - Add a product to cart

- `GET /api/cart` - Get cart items

- `DELETE /api/cart/remove/{productId}` - Remove product from cart

### Orders & Payment

- `POST /api/orders/checkout` - Checkout and create an order

- `POST /api/payment` - Process Stripe payment

### Security

- Uses **JWT-based authentication** for securing endpoints.

- Role-based access: Users have roles (`USER`, `ADMIN`) that define their access.

- Security configurations are handled in `SecurityConfig.java`.

### Logging & Debugging

- Enable debugging by modifying `application.properties`
