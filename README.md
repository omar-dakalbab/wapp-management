# WhatsApp Management API

A backend API for managing WhatsApp Business conversations via the WhatsApp Cloud API. Supports receiving messages through webhooks, sending messages, real-time updates via Socket.io, and user authentication with role-based access.

## Tech Stack

- **Runtime**: Node.js with Express.js
- **Database**: MongoDB with Mongoose
- **Real-time**: Socket.io for live message updates
- **WhatsApp**: WhatsApp Cloud API (via Meta)
- **Auth**: JWT + bcrypt, role-based (admin/employee)
- **Logging**: Winston with daily rotating log files
- **Other**: Axios, CORS, dotenv

## Features

- WhatsApp webhook verification and incoming message handling
- Send messages via WhatsApp Cloud API
- Real-time message broadcasting to connected clients via Socket.io
- Message deduplication (prevents duplicate webhook deliveries)
- User registration and login with JWT authentication
- Role-based access control (admin / employee)
- Contact and message storage in MongoDB
- Structured logging with Winston

## Setup

1. Install dependencies:
   ```bash
   npm install
   ```

2. Create a `.env` file with the following variables:
   ```
   PORT=3000
   VERIFY_TOKEN=<your-webhook-verify-token>
   ACCESS_TOKEN=<your-whatsapp-access-token>
   PHONE_NUMBER_ID=<your-phone-number-id>
   MONGO_URI=<your-mongodb-connection-string>
   JWT_SECRET=<your-jwt-secret>
   ```

3. Start the server:
   ```bash
   npm start
   ```

## Project Structure

```
app.js               # Entry point, Express + Socket.io setup
config/config.js     # Environment variable loading
controllers/         # Route handlers (webhook, message, auth)
models/              # Mongoose schemas (Message, User, Contact)
routes/              # Express route definitions
middleware/          # Auth middleware, error handler
utils/               # Database connection, logger, AppError
```
