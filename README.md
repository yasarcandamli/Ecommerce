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

  &nbsp;

  &nbsp;

# Frontend

This project is the **frontend** of an e-commerce platform built using **React**, **Redux**, and **Stripe**. It provides a fully functional interface for users to view products, add them to the cart, make payments, and manage their accounts.

## Features

- **Product Listing**: Products are displayed with categories and filter options.

- **Cart Management**: Users can add products to the cart, remove items, and update quantities.

- **Payment Processing**: Secure payments through Stripe.

- **User Login & Registration**: Users can log in or create an account.

- **Responsive Design**: Fully responsive UI for both mobile and desktop.

## Tech Stack

- **Frontend**: React, Redux, React Router, MUI (Material-UI)

- **DevTools**: React Developer Tools, Redux DevTools

- **CSS**: TailwindCSS, DaisyUI (UI components), Emotion (styled components)

- **Payment System**: Stripe

- **State Management**: Redux Toolkit (`@reduxjs/toolkit`)

- **Build & Development**: Vite (Fast development and production build)

## Setup

To get this project up and running locally, follow the steps below.

### Prerequisites

- **Node.js** (v18 and above)

- **npm** (v8 and above)

### Step 1: Clone the Repository

```bash
git clone https://github.com/yasarcandamli/Ecommerce
```

### Step 2: Install Dependencies

```bash
npm install
```

### Step 3: Configure Environment Variables

Create a .env file in the root directory and set the following variables:

```bash
VITE_BACKEND_URL=http://localhost:8080
VITE_STRIPE_PUBLISHABLE_KEY=your-stripe-publishable-key
VITE_FRONTEND_URL=http://localhost:5173
```

- **VITE_BACKEND_URL**: The URL of your backend API.

- **VITE_STRIPE_PUBLISHABLE_KEY**: Your Stripe public key.

- **VITE_FRONTEND_URL**: The URL where your frontend will run.

### Step 4: Start the Development Server

```bash
npm run dev
```

This will start the development server, and the application will be available at `http://localhost:5173`.

## API Endpoints

The frontend interacts with the backend API.

## Redux Store Structure

Redux is used to manage the app's state. Below is an overview of the reducers and actions:

**`authReducer`**
Handles user authentication state. User details, login, logout, and registration states are managed here.

**`cartReducer`**
Manages the user's cart. Cart items, total price, and cart ID are stored here.

**`productReducer`**
Manages product data and categories. Product listing and category selection are handled in this reducer.

**`errorReducer`**
Manages the loading states and error messages for API requests. It also handles category and button loaders.

**`paymentMethodReducer`**
Used for selecting a payment method in the cart. Stores the chosen payment method.

### Actions

- **fetchProducts**: Fetches products from the API.

- **fetchCategories**: Fetches categories from the API.

- **addToCart**: Adds a product to the cart.

- **removeFromCart**: Removes a product from the cart.

- **authenticateSignInUser**: Authenticates a user and logs them in.

- **registerNewUser**: Registers a new user.

- **createStripePaymentSecret**: Generates a Stripe payment client secret.

- **stripePaymentConfirmation**: Confirms the payment with Stripe.

### Troubleshooting

- Unable to Connect to Backend: Ensure that the VITE_BACKEND_URL in your .env file is correct and the backend server is running.

- Stripe Payment Issues: Double-check your Stripe public key and ensure it is properly added to the .env file.

- CORS Errors: If you're encountering CORS errors, make sure the backend is allowing requests from http://localhost:5173. (This problem handled in the backend - **`WebConfig.java`** )
