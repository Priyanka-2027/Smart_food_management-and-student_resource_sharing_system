# foods
# 🍱 FoodShare - Sustainable Food Management Platform

<div align="center">

![GitHub License](https://img.shields.io/badge/license-MIT-blue.svg)
![Node Version](https://img.shields.io/badge/node-%3E%3D14.0.0-green.svg)
![React Version](https://img.shields.io/badge/react-%3E%3D19.0.0-blue.svg)
![MongoDB](https://img.shields.io/badge/MongoDB-%3E%3D5.0-green.svg)

**A comprehensive platform connecting students, dining halls, and NGOs to minimize food waste while enabling sustainable resource sharing.**

[Live Demo](#) • [Documentation](#-installation--setup) • [Contribute](#-contribution-guide)

</div>

---

## 📌 Overview

**FoodShare** is an intelligent ecosystem that bridges the gap between **dining halls (Mess)**, **students**, and **NGOs** to create a sustainable food management system. The platform tackles food waste in educational institutions while enabling peer-to-peer resource sharing among students.

### 🎯 Problem Statement

- **Food Waste Crisis**: Dining halls generate significant daily food waste
- **Limited Resources**: Students struggle to afford or find basic items
- **Siloed Communities**: No effective channel for food donations to NGOs
- **Lack of Transparency**: No feedback mechanism for meal quality

### ✨ Solution

FoodShare provides:
- **Leftover Food Sharing**: Direct connection between dining halls and NGOs for food donation
- **Swap Marketplace**: Students exchange items (books, clothes, notebooks) sustainably
- **Daily Menu Management**: Transparent meal planning with student feedback
- **Real-time Tracking**: Complete workflow from food preparation to NGO collection
- **Role-based Access**: Distinct interfaces for students, mess staff, and NGO representatives

---

## 🚀 Key Features

### 🔐 **Multi-Role Authentication**
- Email/OTP-based signup with verification
- Google OAuth integration
- Role-based access control (Student, Mess, NGO)
- JWT-based stateless authentication (30-day expiry)
- Secure password hashing with bcrypt

### 🥘 **Leftover Food Management**
- Post excess food with images, quantity, and expiry time
- Real-time pickup scheduling
- Request tracking and acceptance workflow
- Photo evidence at collection and delivery stages
- Status tracking: Posted → Requested → Accepted → Collected → Completed

### 📚 **Swap Marketplace**
- Post items for swap or donation (notebooks, books, dresses, bags)
- Category-based filtering
- Hostel-block specific visibility
- Gender preference settings
- Complete request lifecycle management

### 📊 **Daily Menu System**
- Mess staff creates daily menus with meal types (breakfast, lunch, dinner)
- Support for alternative food options
- Prevents duplicate meal postings
- Accessible to all students

### 📈 **Analytics & Feedback**
- Students rate meal quality per item
- Real-time analytics dashboard for mess staff
- Meal insights to improve food quality
- Historical feedback tracking

### 📱 **Multi-Channel Notifications**
- Email verification via Nodemailer
- SMS notifications via Twilio (configurable)
- Real-time request status updates

---

## 🛠 Tech Stack

### **Frontend**
| Technology | Version | Purpose |
|------------|---------|---------|
| React | 19.2.4 | UI framework |
| Vite | 8.0.0 | Build tool & dev server |
| React Router | 7.13.1 | Client-side routing |
| Axios | 1.13.6 | HTTP client |
| Framer Motion | 12.38.0 | Animations & transitions |
| Chart.js | 4.5.1 | Analytics visualization |
| Lucide React | 1.8.0 | Icon library |
| JWT Decode | 4.0.0 | Token parsing |

### **Backend**
| Technology | Version | Purpose |
|------------|---------|---------|
| Node.js | 14+ | Runtime environment |
| Express | 5.2.1 | Web framework |
| MongoDB | 5.0+ | NoSQL database |
| Mongoose | 9.3.0 | ODM & schema validation |
| JWT | 9.0.3 | Authentication |
| Bcrypt | 6.0.0 | Password hashing |
| Multer | 2.1.1 | File upload handling |
| Nodemailer | 8.0.5 | Email service |
| Twilio | 5.13.1 | SMS service |
| Google Auth Library | 10.6.2 | OAuth validation |
| CORS | 2.8.6 | Cross-origin support |

### **Tools & Libraries**
- **Linting**: ESLint
- **Dev Server**: Nodemon
- **Environment Management**: dotenv

---

## 📁 Project Structure

```
foods-main/
│
├── auth-system/
│   │
│   ├── backend/                    # Express.js REST API
│   │   ├── controllers/            # Business logic for each route
│   │   │   ├── authController.js          # Authentication & profile
│   │   │   ├── menuController.js          # Menu CRUD operations
│   │   │   ├── leftoverController.js      # Leftover food lifecycle
│   │   │   ├── swapItemController.js      # Marketplace items
│   │   │   ├── requestController.js       # Swap/donation requests
│   │   │   └── feedbackController.js      # Analytics & feedback
│   │   │
│   │   ├── models/                 # Mongoose schemas
│   │   │   ├── User.js                   # User profiles (student, mess, ngo)
│   │   │   ├── Menu.js                   # Daily meal menus
│   │   │   ├── LeftoverFood.js           # Food donation tracking
│   │   │   ├── SwapItem.js               # Marketplace items
│   │   │   ├── Request.js                # Swap/donation requests
│   │   │   ├── Feedback.js               # Meal ratings
│   │   │   └── TempRegistration.js       # OTP verification storage
│   │   │
│   │   ├── routes/                 # API route definitions
│   │   │   ├── authRoutes.js       (11 endpoints)
│   │   │   ├── menuRoutes.js       (3 endpoints)
│   │   │   ├── leftoverRoutes.js   (6 endpoints)
│   │   │   ├── swapItemRoutes.js   (4 endpoints)
│   │   │   ├── requestRoutes.js    (6 endpoints)
│   │   │   └── feedbackRoutes.js   (4 endpoints)
│   │   │
│   │   ├── middleware/
│   │   │   ├── authMiddleware.js         # JWT protection & role validation
│   │   │   └── uploadMiddleware.js       # Image upload handling (Multer)
│   │   │
│   │   ├── utils/
│   │   │   ├── emailService.js          # Nodemailer email sending
│   │   │   └── smsService.js            # Twilio SMS integration
│   │   │
│   │   ├── uploads/                     # Static file storage
│   │   ├── server.js                    # Express app entry point
│   │   ├── package.json
│   │   └── .env                         # Environment variables
│   │
│   └── frontend/                   # React + Vite SPA
│       ├── src/
│       │   ├── pages/              # Route components
│       │   │   ├── Login.jsx            # Email/Google login
│       │   │   ├── Signup.jsx           # Registration wizard
│       │   │   ├── CompleteProfile.jsx  # Phone number collection
│       │   │   ├── StudentDashboard.jsx # Student home
│       │   │   ├── MessDashboard.jsx    # Mess staff interface
│       │   │   └── NgoDashboard.jsx     # NGO interface
│       │   │
│       │   ├── components/         # Reusable UI components
│       │   │   ├── Navbar.jsx           # Navigation bar
│       │   │   ├── Sidebar.jsx          # Student sidebar
│       │   │   ├── StudentSidebar.jsx   # Student-specific nav
│       │   │   ├── NgoSidebar.jsx       # NGO-specific nav
│       │   │   ├── DailyMenu.jsx        # Menu display
│       │   │   ├── AddMenuForm.jsx      # Menu creation (mess)
│       │   │   ├── LeftoverFoodForm.jsx # Post leftover food
│       │   │   ├── PostItemForm.jsx     # Create marketplace item
│       │   │   ├── MyListings.jsx       # Student's items
│       │   │   ├── SwapMarketplace.jsx  # Browse & swap items
│       │   │   ├── FoodRequests.jsx     # Manage food requests
│       │   │   ├── MyRequests.jsx       # Student's requests
│       │   │   ├── Analytics.jsx        # Mess analytics view
│       │   │   └── PageTransition.jsx   # Route animations
│       │   │
│       │   ├── context/
│       │   │   └── AuthContext.jsx      # Global auth state
│       │   │
│       │   ├── services/
│       │   │   └── api.js               # Axios interceptor & base config
│       │   │
│       │   ├── styles/              # Component styles
│       │   │   ├── Login.css
│       │   │   ├── Signup.css
│       │   │   ├── MenuForm.css
│       │   │   ├── FoodRequests.css
│       │   │   ├── SwapMarketplace.css
│       │   │   ├── Analytics.css
│       │   │   ├── FeedbackForm.css
│       │   │   ├── MessDashboard.css
│       │   │   └── [others]
│       │   │
│       │   ├── App.jsx              # Root component
│       │   ├── main.jsx             # Entry point
│       │   └── index.css            # Global styles
│       │
│       ├── public/                  # Static assets
│       ├── package.json
│       ├── vite.config.js
│       ├── eslint.config.js
│       └── .env
│
└── README.md                        # This file
```

---

## 🏗 System Architecture

```mermaid
graph TB
    Client["📱 Frontend Client"]
    API["⚙️ Express API Server"]
    DB["🗄️ MongoDB Database"]
    Auth["🔐 JWT/OAuth"]
    Email["📧 Nodemailer"]
    SMS["📱 Twilio"]
    Storage["💾 Multer Storage"]

    Client -->|HTTP/HTTPS| API
    API -->|Validate| Auth
    API -->|Query/Insert| DB
    API -->|Send| Email
    API -->|Send| SMS
    API -->|Store| Storage
    
    Client -->|React Router| Client
    API -->|Middleware| API

    style Client fill:#4a90e2
    style API fill:#7ed321
    style DB fill:#f5a623
    style Auth fill:#bd10e0
    style Email fill:#50e3c2
    style SMS fill:#b8e986
    style Storage fill:#d0021b
```

---

## 📊 Database Schema Diagram

```mermaid
erDiagram
    USER ||--o{ MENU : "manages"
    USER ||--o{ LEFTOVERFOOD : "posts"
    USER ||--o{ SWAPITEM : "owns"
    USER ||--o{ REQUEST : "creates/receives"
    USER ||--o{ FEEDBACK : "submits"
    
    MENU {
        ObjectId _id
        Date date
        String mealType
        Array items
        DateTime timestamps
    }
    
    LEFTOVERFOOD {
        ObjectId _id
        String itemName
        Number quantity
        String foodType
        Date preparedTime
        Date expiryTime
        String pickupStatus
        ObjectId ngoId
        String foodImage
        DateTime timestamps
    }
    
    SWAPITEM {
        ObjectId _id
        String itemName
        String description
        String category
        String condition
        String image
        String exchangeType
        String status
        ObjectId studentId
        DateTime timestamps
    }
    
    REQUEST {
        ObjectId _id
        ObjectId requesterId
        ObjectId ownerId
        ObjectId itemId
        String type
        String status
        Number quantityRequested
        DateTime timestamps
    }
    
    FEEDBACK {
        ObjectId _id
        ObjectId studentId
        ObjectId menuId
        Array ratings
        DateTime timestamps
    }
    
    USER {
        ObjectId _id
        String name
        String email
        String password
        String phoneNumber
        String role
        String authType
        Boolean isVerified
        DateTime timestamps
    }
```

---

## 🔄 User Flow Diagram

```mermaid
graph TD
    A["🚀 User Arrives"] -->|Email?| B["📧 Email Signup"]
    A -->|Google?| C["🔑 Google OAuth"]
    
    B --> D["📝 Enter Details"]
    D --> E{"📤 OTP Verification"}
    E -->|Success| F["👤 Complete Profile"]
    E -->|Fail| D
    
    C --> F
    
    F --> G{"Role Selection"}
    G -->|Student| H["👨‍🎓 Student Dashboard"]
    G -->|Mess| I["👨‍💼 Mess Dashboard"]
    G -->|NGO| J["🤝 NGO Dashboard"]
    
    H --> H1["📚 Swap Marketplace"]
    H --> H2["🥘 Browse Menus"]
    H --> H3["❤️ Rate Meals"]
    
    I --> I1["🍽️ Post Daily Menu"]
    I --> I2["📊 View Analytics"]
    I --> I3["🥘 Post Leftover Food"]
    
    J --> J1["🍱 Browse Leftovers"]
    J --> J2["📋 Request Food"]
    J --> J3["✅ Collect & Complete"]
    
    style A fill:#e3f2fd
    style H fill:#c8e6c9
    style I fill:#fff9c4
    style J fill:#ffe0b2
```

---

## 📡 API Routes Documentation

### 🔐 **Authentication Routes** (`/api/auth`)

| Method | Endpoint | Role | Description | Request Body |
|--------|----------|------|-------------|--------------|
| POST | `/signup/validate` | Public | Check if email is available | `{ email }` |
| POST | `/signup/initiate` | Public | Generate and send OTP | `{ name, email, password, role, gender, hostelBlock, phoneNumber }` |
| POST | `/signup/verify` | Public | Verify OTP | `{ email, otp }` |
| POST | `/signup/final` | Public | Complete registration (legacy) | User credentials |
| POST | `/google/validate` | Public | Validate Google token | `{ token, role }` |
| POST | `/google` | Public | Google OAuth login | `{ googleToken, role }` |
| POST | `/login` | Public | Email/password login | `{ email, password }` |
| GET | `/profile` | Protected | Get user profile | Headers: `Authorization: Bearer {token}` |
| POST | `/forgot-password` | Public | Request password reset | `{ email }` |
| POST | `/reset-password` | Public | Reset password with token | `{ email, token, newPassword }` |

### 🍽️ **Menu Routes** (`/api/menu`)

| Method | Endpoint | Role | Description | Request Body |
|--------|----------|------|-------------|--------------|
| POST | `/` | Mess | Create daily menu | `{ date, mealType, items: [{ itemName, replacementOption1?, replacementOption2? }] }` |
| GET | `/` | Public | Get all menus | Query: `?date=YYYY-MM-DD&mealType=breakfast` |
| DELETE | `/:id` | Mess | Delete menu item | - |

### 🥘 **Leftover Food Routes** (`/api/leftovers`)

| Method | Endpoint | Role | Description | Request Body |
|--------|----------|------|-------------|--------------|
| POST | `/` | Mess | Post leftover food | FormData: `{ itemName, quantity, foodType, preparedTime, expiryTime, date, comfortablePickupTime, foodImage }` |
| GET | `/` | Protected | Get leftovers list | Query: `?status=Posted&date=YYYY-MM-DD` |
| POST | `/request/:id` | NGO | Request food pickup | `{ ngoName, personName, phoneNumber, pickupTime }` |
| PUT | `/accept/:id` | Mess | Accept food request | - |
| PUT | `/reject/:id` | Mess | Reject food request | - |
| PUT | `/collect/:id` | NGO | Mark as collected | FormData: `{ collectionImage }` |
| PUT | `/complete/:id` | NGO | Mark delivery complete | FormData: `{ deliveryImage }` |

### 📚 **Swap Item Routes** (`/api/items`)

| Method | Endpoint | Role | Description | Request Body |
|--------|----------|------|-------------|--------------|
| POST | `/` | Student | Create new swap item | FormData: `{ itemName, description, returnItemDetails?, category, condition, image, quantity, exchangeType, hostelBlock, genderVisibility }` |
| GET | `/` | Protected | Get all items | Query: `?category=Notebooks&status=active&hostelBlock=A` |
| GET | `/my-listings` | Student | Get user's items | - |
| DELETE | `/:id` | Student | Delete own item | - |

### 📨 **Request Routes** (`/api/requests`)

| Method | Endpoint | Role | Description | Request Body |
|--------|----------|------|-------------|--------------|
| POST | `/` | Student | Create swap/donate request | FormData: `{ itemId, type, quantityRequested, offeredItemDetails?, swapImage?, pickupBlock?, pickupTime? }` |
| GET | `/incoming` | Student | Get requests received | - |
| GET | `/outgoing` | Student | Get requests sent | - |
| PUT | `/:id/accept` | Student | Accept swap request | `{ meetingBlock, meetingTime, genderPreference }` |
| PUT | `/:id/reject` | Student | Reject request | - |
| PUT | `/:id/cancel` | Student | Cancel request | - |

### 📊 **Feedback Routes** (`/api/feedback`)

| Method | Endpoint | Role | Description | Request Body |
|--------|----------|------|-------------|--------------|
| GET | `/analytics` | Mess | Get analytics dashboard | Query: `?dateRange=7days&mealType=lunch` |
| GET | `/status` | Student | Check feedback status | Query: `?date=YYYY-MM-DD&mealType=breakfast` |
| POST | `/` | Student | Submit meal ratings | `{ date, mealType, ratings: [{ itemName, rating }] }` |
| GET | `/student` | Student | Get feedback history | - |

---

## ⚙️ Installation & Setup

### Prerequisites
- **Node.js** v14 or higher
- **npm** or **yarn**
- **MongoDB** (local or Atlas)
- **Git**

### 1️⃣ Clone Repository

```bash
git clone https://github.com/yourusername/foodshare.git
cd foods-main
```

### 2️⃣ Backend Setup

```bash
cd auth-system/backend

# Install dependencies
npm install

# Create .env file
cp .env.example .env  # (Create if doesn't exist)
```

### 3️⃣ Frontend Setup

```bash
cd ../frontend

# Install dependencies
npm install

# Create .env file
cp .env.example .env  # (Create if doesn't exist)
```

---

## 🔐 Environment Variables

### Backend `.env` File

```env
# Server Configuration
PORT=5000
NODE_ENV=development

# Database
MONGO_URI=mongodb+srv://username:password@cluster.mongodb.net/foodshare?retryWrites=true&w=majority

# JWT Configuration
JWT_SECRET=your_super_secret_jwt_key_min_32_characters_long

# Google OAuth
GOOGLE_CLIENT_ID=your_google_client_id.apps.googleusercontent.com

# Email Configuration (Gmail)
EMAIL_USER=your.email@gmail.com
EMAIL_PASS=your_app_specific_password

# SMS Configuration (Twilio)
TWILIO_ACCOUNT_SID=your_twilio_account_sid
TWILIO_AUTH_TOKEN=your_twilio_auth_token
TWILIO_PHONE_NUMBER=+1234567890

# File Uploads
MAX_FILE_SIZE=5242880  # 5MB in bytes
UPLOAD_PATH=./uploads
```

### Frontend `.env` File

```env
VITE_API_BASE_URL=http://localhost:5000/api
VITE_GOOGLE_CLIENT_ID=your_google_client_id.apps.googleusercontent.com
VITE_APP_NAME=FoodShare
```

### Environment Variables Explained

| Variable | Purpose | Example |
|----------|---------|---------|
| `MONGO_URI` | MongoDB connection string | `mongodb+srv://...` |
| `JWT_SECRET` | Secret key for JWT signing | Any random 32+ char string |
| `GOOGLE_CLIENT_ID` | OAuth credential from Google Cloud | `xxx.apps.googleusercontent.com` |
| `EMAIL_USER` | Gmail account for sending OTPs | `admin@gmail.com` |
| `EMAIL_PASS` | Gmail app password (2FA) | App-specific 16-char password |
| `TWILIO_ACCOUNT_SID` | Twilio account identifier | From Twilio dashboard |
| `TWILIO_AUTH_TOKEN` | Twilio authentication token | From Twilio dashboard |
| `VITE_API_BASE_URL` | API server address (frontend) | `http://localhost:5000/api` |

---

## ▶️ How to Run

### 🔧 Development Mode

#### Start Backend Server

```bash
cd auth-system/backend
npm run dev      # Uses nodemon for auto-reload
# Or
npm start        # Runs with node
```

**Expected Output:**
```
Connected to MongoDB
Server running on port 5000
```

#### Start Frontend Development Server (New Terminal)

```bash
cd auth-system/frontend
npm run dev
```

**Output:**
```
  ➜  Local:   http://localhost:5173/
  ➜  Press h to show help
```

**Access Application:** Open browser and navigate to `http://localhost:5173`

### 📦 Production Build

#### Frontend Build

```bash
cd auth-system/frontend
npm run build     # Creates optimized build in dist/
npm run preview   # Preview production build locally
```

#### Backend Production

```bash
cd auth-system/backend
npm start         # Runs on configured PORT
```

### 🧪 Run Linting

```bash
cd auth-system/frontend
npm run lint      # Check code quality with ESLint
```

---

## 🧾 Logging & Project Behavior

### Error Handling Strategy

The application implements **layered error handling**:

1. **Frontend**: Axios interceptor catches HTTP errors, displays user-friendly messages
2. **Backend**: 
   - **Express Middleware**: CORS, JSON parsing errors caught early
   - **Route Handlers**: Try-catch blocks capture logic errors
   - **Database Operations**: Mongoose validation errors reported with context
   - **Authentication**: JWT verification failures return 401 Unauthorized

### Middleware Stack

```
Request → CORS Check → JSON Parse → Auth Middleware (if protected route)
         → Route Handler → Controller Logic → Database Operations
         → Response with Status Code
```

### Logging & Debugging Files

The backend includes test utilities:
- `test_flow.js` - Full authentication flow testing
- `test_email.js` - Email sending verification
- `test_changes.js` - Database changes verification
- `debug_db.js` - MongoDB connection debugging
- `check_db.js` - Database integrity checks
- `check_items.js` - Swap items validation

**Usage:**
```bash
# Test email service
node test_email.js

# Debug database connection
node debug_db.js

# Check items in database
node check_items.js
```

### Request/Response Pattern

All API responses follow standard format:

```javascript
// Success Response
{
  "success": true,
  "data": { /* payload */ },
  "message": "Operation successful"
}

// Error Response
{
  "success": false,
  "message": "Descriptive error message",
  "error": "Error details (development only)"
}
```

---

## 📈 Features Breakdown

### 🔐 **Advanced Authentication System**

- **Two-Factor Security**: Email OTP verification during signup
- **Dual Auth Methods**: Email/Password or Google OAuth (seamless switching)
- **Token-Based Sessions**: 30-day JWT tokens with role encoding
- **Password Security**: bcrypt with salt rounds for protection
- **Stateless Design**: No server-side session storage needed

### 🍱 **Leftover Food Management Engine**

**Complete Workflow:**
```
Mess Posts Food → NGO Requests → Mess Accepts 
→ NGO Collects (photo proof) → NGO Delivers (photo proof) → Completed
```

**Smart Features:**
- Time-based expiry tracking (preparation to expiry windows)
- Photo evidence at collection & delivery stages
- Request details capture (NGO name, person, contact, pickup time)
- Status state machine to prevent invalid transitions
- Real-time availability indicators

### 📚 **Peer-to-Peer Swap Marketplace**

**Categories Supported:**
- Notebooks
- Books
- Dresses
- Bags
- Daily-use items

**Privacy Controls:**
- Hostel-block specific visibility
- Gender-based filtering (for sensitive items)
- Request lifecycle management (pending → accepted/rejected)

**Exchange Types:**
- Swap with return expectations
- Donate (one-way giving)
- Quantity-based requests

### 📊 **Analytics & Feedback System**

**Mess Analytics Dashboard:**
- Real-time meal ratings per item
- Meal preference trends
- Student feedback aggregation
- Date-based filtering

**Feedback Submission:**
- Rate each meal item individually
- Prevention of duplicate feedback (per date + meal type)
- Historical feedback tracking per student

### 📱 **Multi-Channel Communication**

- **Email**: OTP delivery, password resets, notifications
- **SMS**: Optional Twilio integration for alerts
- **In-App**: Real-time request status updates

---

## 📦 Deployment Guide

### 🌐 Frontend Deployment (Vercel)

1. **Connect Repository**
   ```bash
   vercel login
   vercel link
   ```

2. **Configure Build Settings**
   - Framework: Vite
   - Build Command: `npm run build`
   - Output Directory: `dist`

3. **Set Environment Variables**
   - `VITE_API_BASE_URL`: Your production API URL
   - `VITE_GOOGLE_CLIENT_ID`: OAuth credential

4. **Deploy**
   ```bash
   vercel --prod
   ```

### 🔙 Backend Deployment (Render)

1. **Create Render Account** and connect GitHub repo

2. **Configure Web Service**
   - Environment: Node
   - Build Command: `npm install`
   - Start Command: `npm start`
   - Region: Closest to users

3. **Add Environment Variables**
   - All `.env` variables from [Environment Variables](#-environment-variables)

4. **Deploy**
   - Render auto-deploys on git push

### 🗄️ Database Deployment (MongoDB Atlas)

1. **Create Cluster**
   - M0 Free tier for development
   - M2 Small (0.5 GB) for production

2. **Configure Network Access**
   - Whitelist Render IP
   - Create database user

3. **Get Connection String**
   ```
   mongodb+srv://username:password@cluster.mongodb.net/dbname
   ```

### 📋 Deployment Checklist

- [ ] Frontend API URL points to production backend
- [ ] MongoDB Atlas connection active
- [ ] Email service credentials configured
- [ ] Google OAuth redirect URIs updated
- [ ] CORS settings allow production domain
- [ ] JWT secret is strong and unique
- [ ] File uploads configured for cloud storage (S3 optional)
- [ ] Environment variables set in all services
- [ ] Nodemailer/Twilio accounts active
- [ ] SSL certificate enabled

---

## 🧠 Future Improvements

### 🔄 **Phase 2 Features**

1. **Cloud File Storage**
   - Migrate from local uploads to AWS S3/CloudFront
   - Automatic image optimization & CDN distribution

2. **Real-time Notifications**
   - WebSocket integration for instant updates
   - Push notifications for mobile

3. **Advanced Analytics**
   - Predictive food demand analysis
   - Waste reduction metrics dashboard
   - NGO impact reports

4. **Mobile Application**
   - React Native app for iOS/Android
   - Offline food listing capability
   - Location-based search

5. **Payment Integration**
   - Razorpay/Stripe for donations
   - Meal pre-ordering with discount system

6. **AI-Powered Features**
   - Food demand forecasting
   - Dietary preference matching
   - Spam/fraud detection

7. **Accessibility**
   - Multi-language support (Hindi, Regional Languages)
   - Screen reader optimization
   - RTL support

8. **Gamification**
   - User badges for sustainability
   - Leaderboards for swap participation
   - Rewards system for donations

---

## 🤝 Contribution Guide

We welcome contributions from the community! Follow these steps:

### 📋 Prerequisites

- Fork the repository
- Clone your fork: `git clone https://github.com/yourusername/foodshare.git`
- Create a feature branch: `git checkout -b feature/YourFeature`

### 💻 Development Workflow

1. **Create Feature Branch**
   ```bash
   git checkout -b feature/add-notifications
   ```

2. **Make Changes**
   - Follow existing code style
   - Write meaningful commit messages
   - Test changes locally

3. **Commit & Push**
   ```bash
   git add .
   git commit -m "feat: add real-time notifications"
   git push origin feature/add-notifications
   ```

4. **Submit Pull Request**
   - Clear description of changes
   - Link related issues
   - Include screenshots for UI changes

### 📝 Code Standards

**Frontend (React):**
- Use functional components with hooks
- Props validation with PropTypes/TypeScript
- Component naming: PascalCase
- File structure: Feature-based organization

**Backend (Node.js):**
- Follow Express.js conventions
- MVC architecture (Models → Controllers → Routes)
- Error handling with try-catch
- API versioning support

### 🐛 Reporting Issues

1. Check existing issues first
2. Provide clear reproduction steps
3. Include environment details (OS, Node version, etc.)
4. Attach screenshots/logs if applicable

### 🔄 Branching Strategy

- `main` - Production-ready code
- `develop` - Staging and integration
- `feature/*` - New features
- `bugfix/*` - Bug fixes
- `docs/*` - Documentation updates

---

## 📜 License

This project is licensed under the **MIT License** - see [LICENSE](LICENSE) file for details.

### Summary
- ✅ **Free to use** in personal and commercial projects
- ✅ **Modification allowed** with proper attribution
- ✅ **Distribution permitted**
- ⚠️ **No liability** - use at your own risk
- ⚠️ **No warranty** provided

---

## 🤖 Tech Support & Documentation

### 📚 Resources

- **[API Documentation](./docs/API.md)** - Detailed endpoint documentation
- **[Database Schema](./docs/SCHEMA.md)** - MongoDB collection structure
- **[Deployment Guide](./docs/DEPLOYMENT.md)** - Production setup
- **[Troubleshooting](./docs/TROUBLESHOOTING.md)** - Common issues & solutions

### 💬 Get Help

- **GitHub Issues**: Report bugs or request features
- **Discussions**: Ask questions and discuss ideas
- **Email Support**: [support@foodshare.com]

---

## 🙏 Acknowledgments

- **React Community** for excellent frontend library
- **Express.js** for robust backend framework
- **MongoDB** for flexible NoSQL database
- **Google** for OAuth infrastructure
- **All Contributors** who make this project better

---

## 📊 Project Stats

| Metric | Value |
|--------|-------|
| **Lines of Code** | ~5000+ |
| **API Endpoints** | 34+ |
| **Database Models** | 7 |
| **Frontend Components** | 15+ |
| **Supported User Roles** | 3 |
| **Features** | 7+ Core |

---

<div align="center">

### Made with ❤️ for a Sustainable Future

**If you find this project helpful, please consider:**
- ⭐ Starring the repository
- 🐛 Reporting bugs
- 💡 Suggesting improvements
- 🤝 Contributing code

---

**[⬆ Back to Top](#-foodshare---sustainable-food-management-platform)**

</div>
