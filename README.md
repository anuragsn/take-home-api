Backend API for Product Management

This is the backend service for managing products, built using NestJS. It provides APIs for CRUD operations on product data.

Table of Contents

Installation
Configuration
Usage
Endpoints

# Installation

1. Clone the Repository

2. Install Dependencies
   Ensure you have Node.js installed. Then, install the required dependencies using:
   npm install

# Configuration

Before running the application, configure the environment variables.

1. Create a .env File
   Copy the example environment file and modify it according to your setup:
   cp .env.example .env
2. Adjust the values as needed for your environment

# Usage

1. Run the Application
   npm run start:dev
   The application will be available at http://localhost:3001.

# Endpoints

GraphQL Schema

The API is accessible through a single GraphQL endpoint:

GraphQL Endpoint: http://localhost:3001/graphql

Queries:
.

# products - Get a list of all products

query {
products {
id
name
price
quantity
description
}
}

Mutations

# createProduct(input: CreateProductInput!) - Create a new product.

mutation {
createProduct(
createProductInput: {
name: "New Product"
price: 100
quantity: 10
description: "This is a new product"
}
) {
id
name
price
quantity
description
}
}

# updateProduct(id: ID!, input: UpdateProductInput!) - Update an existing product by ID.

mutation {
updateProduct(
updateProductInput: {
id: 3,
name: "Updated Product",
price: 150,
quantity: 20,
description: "Updated Product"
}
) {
id
name
price
quantity
description
}
}

# removeProduct(id: ID!) - Delete a product by ID.

mutation {
removeProduct(id: 1)
}
