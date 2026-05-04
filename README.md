# 🏦 Bank Transaction System

A secure and scalable **RESTful Banking API** built with **Node.js**, **Express**, and **MongoDB**. It supports user authentication, account management, and transaction handling with email notifications.

---

## 🚀 Features

- ✅ User Registration & Login
- 🔐 JWT-based Authentication with secure HTTP-only Cookies
- 🔑 Password Hashing using bcryptjs
- 💸 Bank Transaction Management (Deposit, Withdrawal, Transfer)
- 📧 Email Notifications via Nodemailer (OAuth2)
- 🌱 Environment Variable Support with dotenv
- 🗄️ MongoDB Database Integration via Mongoose

---

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| Node.js | Runtime Environment |
| Express.js v5 | Web Framework |
| MongoDB + Mongoose | Database |
| bcryptjs | Password Hashing |
| JSON Web Token (JWT) | Authentication |
| Nodemailer + OAuth2 | Email Notifications |
| cookie-parser | Cookie Handling |
| dotenv | Environment Variables |

---

## 📁 Project Structure

```
Bank_Transaction_system/
├── src/
│   ├── controllers/
│   ├── models/
│   ├── routes/
│   └── middleware/
├── server.js
├── package.json
├── .env
└── .gitignore
```

---

## ⚙️ Installation & Setup

### 1. Clone the Repository

```bash
git clone https://github.com/raimaAsghar/Bank_Transaction_system.git
cd Bank_Transaction_system
```

### 2. Install Dependencies

```bash
npm install
```

### 3. Configure Environment Variables

Create a `.env` file in the root directory and add the following:

```env
# Server
PORT=5000

# MongoDB
MONGO_URI=your_mongodb_connection_string

# JWT
JWT_SECRET=your_jwt_secret_key

# Email (OAuth2)
EMAIL_USER=your_email@gmail.com
CLIENT_ID=your_google_client_id
CLIENT_SECRET=your_google_client_secret
REFRESH_TOKEN=your_oauth2_refresh_token
```

### 4. Run the Application

```bash
# Development mode (with nodemon)
npm run dev

# Production mode
npm start
```

---

## 📧 Email Setup (Nodemailer + OAuth2)

This project uses **Gmail OAuth2** for sending email notifications.

**Steps to get OAuth2 credentials:**

1. Go to [Google Cloud Console](https://console.cloud.google.com/) and enable the **Gmail API**.
2. Create **OAuth 2.0 Client ID** credentials (Web Application type).
3. Add `https://developers.google.com/oauthplayground` as an Authorized Redirect URI.
4. Go to [OAuth 2.0 Playground](https://developers.google.com/oauthplayground/):
   - Use your own credentials (gear icon → settings).
   - Select scope: `https://mail.google.com/`
   - Click **Authorize APIs** → **Exchange authorization code for tokens**.
   - Copy the **Refresh Token**.
5. Add all credentials to your `.env` file.

---

## 🔌 API Endpoints

### Auth Routes
| Method | Endpoint | Description |
|---|---|---|
| POST | `/api/auth/register` | Register a new user |
| POST | `/api/auth/login` | Login and receive JWT |
| POST | `/api/auth/logout` | Logout user |

### Transaction Routes
| Method | Endpoint | Description |
|---|---|---|
| POST | `/api/transactions/deposit` | Deposit funds |
| POST | `/api/transactions/withdraw` | Withdraw funds |
| POST | `/api/transactions/transfer` | Transfer to another account |
| GET | `/api/transactions/history` | Get transaction history |

---

## 🔒 Security Features

- Passwords are hashed with **bcryptjs** before storing in the database.
- Authentication is handled via **JWT tokens** stored in secure HTTP-only cookies.
- Sensitive credentials are managed through **environment variables**.
- `.env` file is excluded from version control via `.gitignore`.

---

## 📦 Dependencies

```json
{
  "bcryptjs": "^3.0.3",
  "cookie-parser": "^1.4.7",
  "dotenv": "^17.2.3",
  "express": "^5.2.1",
  "jsonwebtoken": "^9.0.3",
  "mongoose": "^9.1.5",
  "nodemailer": "^7.0.12"
}
```

---

## 👩‍💻 Author

**Raima Asghar**
[GitHub](https://github.com/raimaAsghar)

---

## 📚 References & Acknowledgements

- Nodemailer OAuth2 setup reference: [Difference-Backend-video by Ankur](https://github.com/ankurdotio/Difference-Backend-video/tree/main/026-nodemailer)
- [Nodemailer Official Documentation](https://nodemailer.com/)
- [Google OAuth2 Documentation](https://developers.google.com/identity/protocols/oauth2)
- [OAuth 2.0 Playground](https://developers.google.com/oauthplayground/)

