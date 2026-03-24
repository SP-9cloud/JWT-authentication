JWT Authentication API (Node.js + Express)

A backend REST API built using Node.js and Express.js that demonstrates JWT-based authentication along with User and Post CRUD operations.

This project shows how to build secure APIs using token-based authentication, where users can register, log in, and perform operations on protected resources like posts.

🚀 Features
User Registration & Login
JWT-based Authentication & Authorization
Password hashing using bcrypt
Protected routes using middleware
User Signup & Login operations
Post CRUD operations
RESTful API design
Error handling and validation

🧰 Tech Stack
Backend
Node.js
Express.js
Authentication & Security
JSON Web Token (JWT)
bcrypt
Database
MongoDB (Mongoose)
Validation & Utilities
express-validator
dotenv

🔑 What is JWT?

JSON Web Token (JWT) is a standard used for securely transmitting information between client and server.
After login, the server generates a token which is used to access protected routes. ()

📂 Project Structure
JWT-authentication
│
├── controllers
├── models
├── routes
├── middleware
├── utils
│
├── app.js
├── package.json
└── .env

⚙️ Installation
1️⃣ Clone the repository
git clone https://github.com/SP-9cloud/JWT-authentication.git
2️⃣ Navigate to project folder
cd JWT-authentication
3️⃣ Install dependencies
npm install
🔐 Environment Variables

Create a .env file:

PORT=3000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_secret_key
🗄️ Database Setup

Make sure MongoDB is running locally or use MongoDB Atlas.

Example:

mongodb://localhost:27017/jwt-auth
▶️ Running the Application
npm start

or

nodemon app.js

Server will run at:

http://localhost:3000
🔐 Authentication Flow
User registers (signup)
Password is hashed using bcrypt
User logs in
Server generates JWT token
Token is sent in request headers

Example:

Authorization: Bearer <token>
📌 API Endpoints

Auth Routes
POST /signup      → Register user
POST /login       → Login user

Post Routes
POST /posts       → Create post (Protected)
GET /posts        → Get all posts
GET /posts/:id    → Get post by ID
PUT /posts/:id    → Update post
DELETE /posts/:id → Delete post
🛡️ Protected Routes

Protected routes require a valid JWT token.

Example middleware:

const token = req.headers.authorization.split(" ")[1];
jwt.verify(token, process.env.JWT_SECRET);
⚠️ Error Handling

Centralized error handling ensures consistent API responses.

Example:

{
 "error": "Unauthorized access"
}
