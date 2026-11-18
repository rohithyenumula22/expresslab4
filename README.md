<div align="center">

# 🔐 Authentication System
### Lab 04 — User Registration, Login & JWT

**A secure backend authentication system built with Node.js, Express.js, SQLite and JWT.**

**Backend Development Fundamentals | Aurora University**

</div>

---

## Student Information

| Details | Information |
|:---|:---|
| **Student Name** | rohith yenumula |
| **College** | Aurora University |
| **Registration Number** | 252U1R1266 |
| **Section** | CSE-2E |
| **Course** | Backend Development Fundamentals |
| **Lab Number** | Lab 04 |
| **Project Title** | Registration, Login and JWT |

---

##  About The Project

This project is a backend authentication application that provides secure user registration and login functionality.

It allows users to create accounts using a username, name and password. Passwords are securely hashed using **bcrypt** before being stored in the SQLite database.

During login, the application verifies the user's credentials and generates a **JSON Web Token (JWT)** for successful authentication.

The project demonstrates the fundamentals of backend development, database integration, password security and token generation.

---

## Key Features

<table>
<tr>
<td width="50%">

### 👤 User Registration
- Create new user accounts.
- Validate required fields.
- Prevent duplicate usernames.

</td>
<td width="50%">

###  User Login
- Verify user credentials.
- Compare hashed passwords.
- Reject invalid login attempts.

</td>
</tr>
<tr>
<td width="50%">

###  Password Security
- bcrypt password hashing.
- Secure password comparison.
- No plain-text password storage.

</td>
<td width="50%">

### JWT Generation
- Generate JWT after login.
- Store username in payload.
- Set token expiration time.

</td>
</tr>
</table>

---

##  Technology Stack

| Technology | Purpose |
|:---|:---|
| Node.js | JavaScript runtime |
| Express.js | Backend API development |
| SQLite | Database management |
| bcrypt | Password hashing |
| JSON Web Token | Authentication token generation |
| Postman | API testing |
| Visual Studio Code | Development environment |

---

##  Project Structure

```text
lab4/
│
├── 📁 screenshots/
│   ├── register-success.png
│   ├── register-failure.png
│   ├── login-success.png
│   ├── login-failure.png
│   └── jwt-verification.png
│
├── 📄 server.js
├── 📄 database.js
├── 📄 package.json
├── 📄 package-lock.json
├── 📄 .gitignore
├── 📄 README.md
│
└── 🗄️ users.db
```

---

## ⚙️ Installation & Setup

### 1. Clone the Repository

```bash
git clone https://github.com/deepakgodugu0568/expressnode_lab4.git
```

### 2. Navigate to Project Folder

```bash
cd expressnode_lab4
```

### 3. Install Dependencies

```bash
npm install
```

### 4. Start the Application

```bash
npm run dev
```

### 5. Open in Browser

```text
http://localhost:3000/
```

**Expected Output:**

```text
Registration and Login API is Running
```

---

## 🌐 API Documentation

### Available Endpoints

| Method | Endpoint | Description | Status |
|:---:|:---|:---|:---:|
| GET | `/` | Check server status | 200 |
| POST | `/register/` | Register a new user | 200 |
| POST | `/login/` | Authenticate user and generate JWT | 200 |

### 1️⃣ User Registration

**POST** `/register/`

Request Body:

```json
{
    "username": "rohith123",
    "name": "rohith",
    "password": "rohith@123"
}
```

Success Response:

```text
User registered successfully
```

Duplicate username:

```text
User already exists
```

### 2️⃣ User Login

**POST** `/login/`

Request Body:

```json
{
    "username": "rohith123",
    "password": "rohith@123"
}
```

Success Response:

```json
{
    "jwt_token": "your_generated_jwt_token"
}
```

Invalid credentials return a `400 Bad Request` response.

---

## 🔐 How JWT Authentication Works

The application follows a simple authentication process:

```text
       👤 USER
          |
          ▼
    📝 Registration
          |
          ▼
    🔒 bcrypt Hashing
          |
          ▼
    🗄️ SQLite Database
          |
          ▼
       🔑 Login
          |
          ▼
    🔍 Password Verification
          |
          ▼
     🎟️ JWT Generation
          |
          ▼
    ✅ Token Returned
```

### JWT Structure

A JSON Web Token contains three parts:

| Component | Description |
|:---|:---|
| Header | Contains token type and signing algorithm |
| Payload | Contains username and timestamps |
| Signature | Verifies token authenticity |

The generated JWT was decoded and inspected using JWT.io.

---

## 🧪 API Testing – Postman

The following test cases were performed to verify the application.

| Test Case | Expected Result |
|:---|:---|
| Register with valid details | ✅ Success |
| Register duplicate username | ❌ 400 Bad Request |
| Login with correct credentials | ✅ JWT Generated |
| Login with wrong password | ❌ 400 Bad Request |
| Login with unknown username | ❌ 400 Bad Request |
| Login with missing fields | ❌ 400 Bad Request |

---

## 📸 Project Screenshots

### 1. Successful User Registration

![Registration Success](https://github.com/rohithyenumula22/expresslab4/blob/f214f20d55d901953529c9bbfdd5825404827f0c/screenshots/registration%20successful.png)

### 2. user already exits

![user already exits](https://github.com/rohithyenumula22/expresslab4/blob/f214f20d55d901953529c9bbfdd5825404827f0c/screenshots/user%20already%20exits.png)

### 3. Successful User Login

![Login Success](https://github.com/rohithyenumula22/expresslab4/blob/f214f20d55d901953529c9bbfdd5825404827f0c/screenshots/login%20successful.png)

### 4. Invalid Login

![Login Failure](https://github.com/rohithyenumula22/expresslab4/blob/f214f20d55d901953529c9bbfdd5825404827f0c/screenshots/wrong%20password.png)
![Login Failure](https://github.com/rohithyenumula22/expresslab4/blob/f214f20d55d901953529c9bbfdd5825404827f0c/screenshots/wrong%20username.png)

### 5. JWT Token Verification

![JWT Verification](https://github.com/rohithyenumula22/expresslab4/blob/f214f20d55d901953529c9bbfdd5825404827f0c/screenshots/decoding%20jwt.png)

---

## 🎯 Learning Outcomes

By completing this laboratory exercise, I gained practical knowledge of:

- Building REST APIs using Express.js.
- Connecting Node.js applications with SQLite.
- Implementing user registration and login.
- Hashing passwords using bcrypt.
- Generating JWT authentication tokens.
- Handling invalid credentials and duplicate users.
- Testing APIs using Postman.
- Understanding the structure of JSON Web Tokens.

---

## 🚀 Future Improvements

- Implement JWT verification middleware.
- Protect private API routes.
- Move secret keys into environment variables.
- Add password validation rules.
- Implement user logout and token expiration handling.

---

## 📌 Project Information

| Category | Details |
|:---|:---|
| Project | Registration, Login and JWT |
| Lab | 04 |
| Development | Node.js & Express.js |
| Database | SQLite |
| Testing | Postman |
| Deployment | Localhost |
| Status | ✅ Completed |

---

<div align="center">

### 💻 Developed by Deepak Godugu

**Backend Development Fundamentals — Lab 04**

*Learning • Building • Securing • Improving*

⭐ If you find this project useful, consider giving the repository a star!

</div>
