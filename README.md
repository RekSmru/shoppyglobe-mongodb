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
├── screenshots/      <-- add your screenshots here
│   ├── products.png
│   ├── users.png
│   └── cart.png
└── README.md         <-- documentation
---

## Setup Instructions

1. **Clone the repository**

```bash
git clone https://github.com/RekSmru/shoppyglobe-mongodb.git

```

```bash
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

Server runs at http://localhost:5000


MongoDB Collections Screenshots

Products Collection
![Products Collection]("./screenshots/products.png")

Cart Collection
![Carts Collection]("./screenshots/carts.png")

Users Collection
![Users Collection]("./screenshots/userss.png")

