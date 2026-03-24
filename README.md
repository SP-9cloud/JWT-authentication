# 🔐 JWT Authentication API (Node.js + Express)

A backend REST API built using **Node.js and Express.js** that demonstrates **JWT-based authentication** along with **User and Post CRUD operations**.

This project shows how to build secure APIs using **token-based authentication**, where users can register, log in, and perform operations on protected resources like posts.

---

# 🚀 Features

* User Registration & Login
* JWT-based Authentication & Authorization
* Password hashing using bcrypt
* Protected routes using middleware
* User Signup & Login operations
* Post CRUD operations
* RESTful API design
* Error handling and validation

---

# 🧰 Tech Stack

### Backend

* Node.js
* Express.js

### Authentication & Security

* JSON Web Token (JWT)
* bcrypt

### Database

* MongoDB (Mongoose)

### Validation & Utilities

* express-validator
* dotenv

---

# 🔑 What is JWT?

JSON Web Token (JWT) is a standard used for securely transmitting information between client and server.
After login, the server generates a token which is used to access protected routes. ([Wikipedia][1])

---

# 📂 Project Structure

```id="z1v2xt"
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
```

---

# ⚙️ Installation

### 1️⃣ Clone the repository

```id="hm1b1c"
git clone https://github.com/SP-9cloud/JWT-authentication.git
```

---

### 2️⃣ Navigate to project folder

```id="kkxzz7"
cd JWT-authentication
```

---

### 3️⃣ Install dependencies

```id="k1u2hv"
npm install
```

---

# 🔐 Environment Variables

Create a `.env` file:

```id="7wh5hj"
PORT=3000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_secret_key
```

---

# 🗄️ Database Setup

Make sure MongoDB is running locally or use MongoDB Atlas.

Example:

```id="fbh2pr"
mongodb://localhost:27017/jwt-auth
```

---

# ▶️ Running the Application

```id="lg9uvb"
npm start
```

or

```id="3zvnpx"
nodemon app.js
```

Server will run at:

```id="nnd9ey"
http://localhost:3000
```

---

# 🔐 Authentication Flow

1. User registers (signup)
2. Password is hashed using bcrypt
3. User logs in
4. Server generates JWT token
5. Token is sent in request headers

Example:

```id="9q2k7h"
Authorization: Bearer <token>
```


# 🛡️ Protected Routes

Protected routes require a valid JWT token.

Example middleware:

```javascript id="1q1f4h"
const token = req.headers.authorization.split(" ")[1];
jwt.verify(token, process.env.JWT_SECRET);
```

---

# ⚠️ Error Handling

Centralized error handling ensures consistent API responses.

Example:

```json id="aqi9kr"
{
 "error": "Unauthorized access"
}
```
