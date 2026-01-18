# Car Rental Systems

A full-stack car rental application with separate customer and admin interfaces.

## Project Structure

```
.
├── backend/          # Node.js/Express API server
├── frontend/         # Customer-facing React application
└── admin/           # Admin dashboard React application
```

## Technology Stack

### Backend
- **Runtime**: Node.js with ES modules
- **Framework**: Express 5.x
- **Database**: MongoDB with Mongoose ODM
- **Authentication**: JWT (jsonwebtoken) + bcrypt/bcryptjs
- **Payment**: Stripe integration
- **Security**: Helmet, CORS, validator
- **Development**: Nodemon for auto-reload
- **File Upload**: Multer
- **Logging**: Morgan

### Frontend (Customer)
- **Framework**: React 19.x with Vite
- **Routing**: React Router DOM 7.x
- **Styling**: Tailwind CSS 4.x
- **UI/UX**:
  - Framer Motion for animations
  - Lucide React & React Icons for icons
  - React Toastify for notifications
- **3D Graphics**: Three.js with React Three Fiber & Drei
- **Payment**: Stripe React integration
- **HTTP Client**: Axios

### Admin Dashboard
- **Framework**: React 19.x with Vite
- **Routing**: React Router DOM 7.x
- **Styling**: Tailwind CSS 4.x
- **UI Components**: Lucide React, React Icons, React Toastify
- **HTTP Client**: Axios

## Development

### Backend
```bash
cd backend
npm install
npm start    # Runs with nodemon
```

### Frontend
```bash
cd frontend
npm install
npm run dev     # Development server
npm run build   # Production build
npm run preview # Preview production build
```

### Admin
```bash
cd admin
npm install
npm run dev     # Development server
npm run build   # Production build
npm run preview # Preview production build
```

## Key Features

- JWT-based authentication and authorization
- Stripe payment processing
- File upload capabilities (likely for car images)
- Separate customer and admin interfaces
- 3D car visualization (Three.js in frontend)
- Responsive design with Tailwind CSS
- Real-time notifications
- Security hardening with Helmet

## Environment Configuration

The backend uses dotenv for environment variables. Required configuration likely includes:
- MongoDB connection string
- JWT secret
- Stripe API keys
- Server port
- CORS origins

## Git Information

- **Current Branch**: fervent-banzai
- **Recent Commits**:
  - Updated database
  - Updated UI
  - Added admin frontend

This is a git worktree branched from the main repository.
