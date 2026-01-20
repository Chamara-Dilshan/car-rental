# DRIVEHUB - Car Rental Project

## Project Overview
DRIVEHUB is a full-stack car rental application with customer-facing frontend, admin dashboard, and Node.js backend. Users can browse cars, check availability, make bookings, and pay via Stripe. Admins can manage car listings and view bookings.

## Contact Information
- **Address**: No 168, Lakshauyana, Polonnaruwa
- **Phone**: +94 765479242
- **Email**: chamaradilshan.dev@gmail.com
- **Designed by**: Chamara Dilshan

## Tech Stack

### Backend (`/backend`)
- **Runtime**: Node.js with ES Modules
- **Framework**: Express.js v5
- **Database**: MongoDB Atlas with Mongoose
- **Authentication**: JWT (jsonwebtoken)
- **Payment**: Stripe
- **File Upload**: Multer
- **Security**: Helmet, CORS, bcrypt

### Frontend (`/frontend`)
- **Framework**: React 19 with Vite
- **Styling**: Tailwind CSS v4
- **Routing**: React Router DOM v7
- **HTTP Client**: Axios
- **Animations**: Framer Motion
- **3D Graphics**: Three.js with React Three Fiber
- **Payment**: Stripe React SDK

### Admin (`/admin`)
- **Framework**: React 19 with Vite
- **Styling**: Tailwind CSS v4
- **Routing**: React Router DOM v7
- **HTTP Client**: Axios

## Project Structure
```
Car-Rental/
├── backend/
│   ├── config/db.js          # MongoDB connection
│   ├── controllers/          # Business logic
│   ├── models/               # Mongoose schemas (User, Car, Booking)
│   ├── middlewares/          # Auth, file upload
│   ├── routes/               # API endpoints
│   ├── uploads/              # Uploaded car images
│   └── server.js             # Express app entry
├── frontend/
│   └── src/
│       ├── pages/            # Route pages
│       ├── components/       # Reusable UI components
│       └── assets/           # Static assets
└── admin/
    └── src/
        ├── pages/            # Admin pages
        └── components/       # Admin UI components
```

## Development Commands

### Backend
```bash
cd backend
npm install
npm start          # Runs nodemon server.js on port 5000
```

### Frontend
```bash
cd frontend
npm install
npm run dev        # Vite dev server on port 5173
npm run build      # Production build
```

### Admin
```bash
cd admin
npm install
npm run dev        # Vite dev server on port 5174
npm run build      # Production build
```

## Environment Variables

### Backend (`backend/.env`)
```
MONGODB_URL=mongodb+srv://...
STRIPE_SECRET_KEY=sk_test_...
FRONTEND_URL=http://localhost:5173
```

Note: JWT_SECRET is currently hardcoded in `middlewares/auth.js` - consider moving to .env.

## Database Models

### User (`models/userModel.js`)
- name, email, password (hashed), timestamps

### Car (`models/carModel.js`)
- make, model, year, dailyRate, status, imageUrl
- Embedded bookings array for availability tracking
- Methods: `isAvailableForRange()`, `getAvailabilitySummary()`

### Booking (`models/bookingModel.js`)
- References: user, car
- Dates: pickupDate, returnDate
- Customer details, address, payment info
- Status: pending, confirmed, completed, cancelled
- Pre/post save hooks sync with Car.bookings

## API Endpoints

| Route | Purpose |
|-------|---------|
| `POST /api/auth/register` | User registration |
| `POST /api/auth/login` | User login, returns JWT |
| `GET /api/cars` | List all cars |
| `POST /api/cars/add` | Add new car (admin) |
| `GET /api/bookings` | User's bookings |
| `POST /api/bookings` | Create booking |
| `POST /api/payments/create-session` | Stripe checkout |
| `GET /api/ping` | Health check |

## Code Conventions
- ES Modules (`import`/`export`) throughout
- Async/await for all asynchronous operations
- JWT Bearer token authentication
- Controllers handle business logic, routes define endpoints
- React functional components with hooks
- Tailwind utility classes for styling

## Important Files
- `backend/server.js` - Express app configuration and middleware
- `backend/config/db.js` - MongoDB connection with setup guide
- `backend/middlewares/auth.js` - JWT verification middleware
- `backend/models/carModel.js` - Complex availability logic
- `frontend/src/App.jsx` - Main routing configuration
- `admin/src/App.jsx` - Admin routing configuration

## Common Tasks

### Adding a new API endpoint
1. Create controller function in `backend/controllers/`
2. Add route in `backend/routes/`
3. Import and use in `backend/server.js`

### Adding a new car field
1. Update schema in `backend/models/carModel.js`
2. Update controller logic in `backend/controllers/carController.js`
3. Update frontend forms in `frontend/src/components/`
4. Update admin forms in `admin/src/components/`

### Adding a new page
1. Create page component in `src/pages/`
2. Add route in `src/App.jsx`
3. Update navigation in `src/components/Navbar/`

## Notes
- No testing framework is currently configured
- CORS is configured to allow frontend origins
- Static files served from `/uploads` endpoint
- Stripe webhook handling may need setup for production
