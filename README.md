# ShoppyGlobe Backend API

## Project Overview
This is the backend for the **ShoppyGlobe E-commerce application**, built with **Node.js**, **Express.js**, and **MongoDB**.  
It supports:

- User registration & login (JWT authentication)
- Product listing
- Shopping cart (add/update/delete items)
- API error handling and validation


## Technologies Used

- Node.js
- Express.js
- MongoDB / Mongoose
- JWT (JSON Web Token) for authentication
- bcryptjs for password hashing
- Thunder Client (for API testing)


## Project Structure

```bash
shoppyglobe-backend/
│
├── server.js
├── .env
├── package.json
├── config/
│   └── db.js
├── models/
│   ├── Product.js
│   ├── Cart.js
│   └── User.js
├── routes/
│   ├── productRoutes.js
│   ├── cartRoutes.js
│   └── authRoutes.js
├── middleware/
│   └── authMiddleware.js
├── screenshots/      
│   ├── products.png
│   ├── users.png
│   └── cart.png
└── README.md         
```

## Setup Instructions

1. **Clone the repository**

```bash
git clone https://github.com/RekSmru/shoppyglobe-mongodb.git
cd shoppyglobe-mongodb
```

## Install dependencies

```bash
npm init -y
npm install express mongoose body-parser
npm install nodemon --save-dev
npx nodemon server.js
```
## Setup environment variables

```bash
PORT=5000
MONGO_URI=mongodb://127.0.0.1:27017/shoppyglobe
JWT_SECRET=your_jwt_secret
```

### Start the server

```bash
npx nodemon server.js
```
Server running on port 5000
- http://localhost:5000

## API Testing (Thunder Client)

You can test all APIs using **Thunder Client** in VS Code. Follow these steps:


### Register a New User
 POST /register

- Open Thunder Client → click **New Request**  
- Select **POST** method  
- URL: `http://localhost:5000/register`  
- Go to **Body → JSON** and add:

```bash
{
  "name": "John Doe",
  "email": "john@example.com",
  "password": "123456"
}
```

### Login User
 POST /login

- Open Thunder Client → New Request → POST
- URL: http://localhost:5000/login
- Body → JSON:

```bash
{
  "email": "john@example.com",
  "password": "123456"
}
```

### Response:

```bash
{
  "token": "eyJhbGciOiJIUzI1NiIsInR..."
}
```
### Add Product to Cart (Protected)
  POST /cart
  Headers:

```bash
Authorization: Bearer <your_token_here>
Content-Type: application/json
```
Body:

```bash
{
  "productId": "64fc2e7b7e1b8a1234567890",
  "quantity": 2
}
```
Response:
```bash
{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjY5ZDZiMTJjNWEzYjJkZTEzMDg2ZmI2NCIsImlhdCI6MTc3NTY4OTYyOSwiZXhwIjoxNzc1Nzc2MDI5fQ.QN5mRgTfn4D7UN_wWWWvekCLjIG0C"
}
```
- Copy the token from response for protected routes

### Get products
```bash
GET http://localhost:5000/products
```

### Get product by ID
```bash
GET http://localhost:5000/products/<productId>
```
### Add to cart
```bash
POST http://localhost:5000/cart
Header: Authorization: Bearer <token>
```
- Body:
```bash
{
  "productId": "<productId>",
  "quantity": 2
}
```

### Update cart
- PUT http://localhost:5000/cart/<productId>
```bash
{
  "quantity": 5
}
```

### Delete cart item
```bash
DELETE http://localhost:5000/cart/<productId>
```

## MongoDB Collections Screenshots

Products Collection
![Products Collection](./screenshots/products.png)

Cart Collection
![Carts Collection](./screenshots/carts.png)

Users Collection
![Users Collection](./screenshots/userss.png)

