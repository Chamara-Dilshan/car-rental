# 🚗 DRIVEHUB - Car Rental Application

A full-stack car rental platform that enables users to browse available cars, make bookings, and process payments seamlessly. Includes a comprehensive admin dashboard for managing the car fleet and bookings.

## ✨ Features

### Customer Features
- 🔍 Browse available cars with detailed information
- 📅 Check real-time car availability
- 💳 Secure payment processing via Stripe
- 📝 Create and manage bookings
- 👤 User authentication and profile management

### Admin Features
- ➕ Add and manage car listings
- 📊 View all bookings and customer information
- 🖼️ Upload car images
- 📈 Track rental status

## 🛠️ Tech Stack

### Backend
- **Runtime**: Node.js (ES Modules)
- **Framework**: Express.js v5
- **Database**: MongoDB Atlas with Mongoose
- **Authentication**: JWT (jsonwebtoken)
- **Payment**: Stripe
- **File Upload**: Multer
- **Security**: Helmet, CORS, bcrypt

### Frontend
- **Framework**: React 19
- **Build Tool**: Vite
- **Styling**: Tailwind CSS v4
- **Routing**: React Router DOM v7
- **HTTP Client**: Axios
- **Animations**: Framer Motion
- **3D Graphics**: Three.js with React Three Fiber
- **Payment**: Stripe React SDK

### Admin Dashboard
- **Framework**: React 19
- **Build Tool**: Vite
- **Styling**: Tailwind CSS v4
- **Routing**: React Router DOM v7
- **HTTP Client**: Axios

## 📁 Project Structure

```
Car-Rental/
├── backend/
│   ├── config/
│   │   └── db.js              # MongoDB connection
│   ├── controllers/           # Business logic
│   ├── models/                # Mongoose schemas
│   │   ├── userModel.js
│   │   ├── carModel.js
│   │   └── bookingModel.js
│   ├── middlewares/           # Auth & file upload
│   ├── routes/                # API endpoints
│   ├── uploads/               # Car images storage
│   └── server.js              # Entry point
├── frontend/
│   └── src/
│       ├── pages/             # Route pages
│       ├── components/        # Reusable components
│       └── assets/            # Static assets
└── admin/
    └── src/
        ├── pages/             # Admin pages
        └── components/        # Admin components
```

## 🚀 Getting Started

### Prerequisites
- Node.js (v14 or higher)
- MongoDB Atlas account
- Stripe account
- npm or yarn

### Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd car-rental
   ```

2. **Backend Setup**
   ```bash
   cd backend
   npm install
   ```

   Create a `.env` file in the backend directory:
   ```env
   MONGODB_URL=mongodb+srv://your-mongodb-url
   STRIPE_SECRET_KEY=sk_test_your-stripe-secret-key
   FRONTEND_URL=http://localhost:5173
   ```

3. **Frontend Setup**
   ```bash
   cd frontend
   npm install
   ```

4. **Admin Setup**
   ```bash
   cd admin
   npm install
   ```

### Running the Application

1. **Start Backend Server**
   ```bash
   cd backend
   npm start
   # Runs on http://localhost:5000
   ```

2. **Start Frontend**
   ```bash
   cd frontend
   npm run dev
   # Runs on http://localhost:5173
   ```

3. **Start Admin Dashboard**
   ```bash
   cd admin
   npm run dev
   # Runs on http://localhost:5174
   ```

## 🔌 API Endpoints

| Method | Endpoint | Description | Auth Required |
|--------|----------|-------------|---------------|
| POST | `/api/auth/register` | User registration | No |
| POST | `/api/auth/login` | User login | No |
| GET | `/api/cars` | List all cars | No |
| POST | `/api/cars/add` | Add new car | Yes (Admin) |
| GET | `/api/bookings` | Get user bookings | Yes |
| POST | `/api/bookings` | Create booking | Yes |
| POST | `/api/payments/create-session` | Stripe checkout | Yes |
| GET | `/api/ping` | Health check | No |

## 💾 Database Models

### User
- name, email, password (hashed)
- Timestamps

### Car
- make, model, year, dailyRate, status, imageUrl
- Embedded bookings array
- Methods: `isAvailableForRange()`, `getAvailabilitySummary()`

### Booking
- References: user, car
- pickupDate, returnDate
- Customer details, address, payment info
- Status: pending, confirmed, completed, cancelled

## 🏗️ Building for Production

```bash
# Frontend
cd frontend
npm run build

# Admin
cd admin
npm run build
```

## 📝 Environment Variables

### Backend
- `MONGODB_URL` - MongoDB connection string
- `STRIPE_SECRET_KEY` - Stripe secret key
- `FRONTEND_URL` - Frontend application URL

> **Note**: JWT_SECRET is currently hardcoded in `middlewares/auth.js`. Consider moving to environment variables for production.

## 🔐 Security Features
- JWT-based authentication
- Password hashing with bcrypt
- CORS configuration
- Helmet.js security headers
- Secure payment processing with Stripe

## 📞 Contact

- **Address**: No 168, Lakshauyana, Polonnaruwa
- **Phone**: +94 765479242
- **Email**: chamaradilshan.dev@gmail.com
- **Designed by**: Chamara Dilshan

## 📄 License

This project is for educational purposes.

---

Made with ❤️ by Chamara Dilshan
