# Week 6 Lab: Password Hashing, JWT Authentication & Role-Based Access Control

## Objective

This lab secures an e-hailing system using:

- Password hashing with bcrypt
- JWT-based authentication
- Role-Based Access Control (RBAC)
- API testing using Postman

---

## Features

- **Secure User Registration:** Passwords hashed with bcrypt before storing.
- **JWT Authentication:** Tokens issued on login, stored in Authorization headers.
- **Role-Based Access Control:** Access to routes restricted by user role (`admin`, `driver`, `customer`).
- **Postman Testing:** Simulate client-side interactions with API.

---

## Technologies Used

- Node.js
- Express
- MongoDB
- bcrypt
- jsonwebtoken
- Postman

---

## Installation & Setup

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/your-repo.git
   cd your-repo
