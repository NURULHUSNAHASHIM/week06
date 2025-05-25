# Week 6 Lab: Password Hashing, JWT Authentication & Role-Based Access Control

## 📌 Description / Objective

This lab enhances the security of an e-hailing system backend by implementing:

- **Password Hashing** using bcrypt.
- **JWT Authentication** to generate and validate user sessions.
- **Role-Based Access Control (RBAC)** to restrict endpoints based on user roles.
- **Postman Testing** to simulate real-world client-server interactions.

The main objective is to ensure that only authenticated users with proper roles can access or modify sensitive resources in the system.

---

## 🛠️ Lab Procedures

### 🔐 Part 1: Password Hashing
- Install required libraries:  
  ```bash
  npm install bcrypt jsonwebtoken
  ```
- Modify `POST /users` to hash passwords using `bcrypt`.

### 🔑 Part 2: JWT Authentication
- Create a `.env` file with:
  ```
  JWT_SECRET=your_secure_key_here
  JWT_EXPIRES_IN=1h
  ```
- Update `POST /auth/login` to return a JWT token on successful login.

### 🧑‍⚖️ Part 3: Role-Based Access Control (RBAC)
- Create authentication and authorization middleware using JWT.
- Protect admin-only endpoints using `authorize(['admin'])`.

### 📬 Part 4: Postman Testing
1. **Register User** via `POST /users` with email, password, and role.
2. **Login** via `POST /auth/login` to receive a JWT token.
3. **Access Admin Endpoint** using the token in an `Authorization` header:
   ```
   Authorization: Bearer <your_token>
   ```

---

## 🧪 Troubleshooting Tips

- **401 Unauthorized**: Check for missing/invalid token or expired session.
- **403 Forbidden**: Your role does not have access to the endpoint.
- **Hashing Errors**: Ensure `bcrypt` is installed and used asynchronously.
- **Token Errors**: Verify your `.env` values and JWT structure.
- Use [https://jwt.io](https://jwt.io) to decode and inspect your token.

---

## 🧾 Project Structure

```
project-root/
│
├── .env                    # JWT secret and expiration time
├── server.js               # Main server file with routes and middleware
├── auth/                  
│   ├── authenticate.js     # JWT auth middleware
│   └── authorize.js        # RBAC middleware
├── routes/
│   └── users.js            # User registration and login routes
├── package.json
└── postman/
    └── jwt-auth-tests.json # Postman collection for testing
```

---

## 🪪 License

This project is licensed under the [MIT License](https://opensource.org/licenses/MIT). You are free to use, modify, and distribute this code as long as you include the original copyright.

---
