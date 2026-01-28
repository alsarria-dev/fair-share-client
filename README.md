# Fair Share - Client

## 📋 Table of Contents

- [Introduction](#introduction)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Configuration](#configuration)
- [Running the Application](#running-the-application)
- [Components Overview](#components-overview)
- [Key Features Explained](#key-features-explained)
- [Authentication](#authentication)
- [Build & Deployment](#build--deployment)
- [Version History](#version-history)
- [Authors](#authors)

## Introduction

Fair Share is an expense management web application built during the Ironhacks web development bootcamp. This frontend application provides a user-friendly interface for managing shared expenses within groups, tracking balances, and maintaining user profiles.

The application is built with React and communicates with a Node.js/Express backend, utilizing the full MERN stack (MongoDB, Express, React, Node.js) combined with modern frontend technologies like Vite, Axios, and Recharts for data visualization.

## Features

- ✅ **User Authentication**: Secure signup and login with JWT tokens
- ✅ **User Profiles**: Create and manage user profiles with profile pictures
- ✅ **Group Management**: Create, edit, and delete expense groups
- ✅ **Expense Tracking**: Add, edit, and delete expenses within groups
- ✅ **Financial Calculations**: Automatic balance, paid, and borrowed calculations
- ✅ **Data Visualization**: Charts and graphs for expense overviews
- ✅ **Group Administration**: Only group creators can edit group details
- ✅ **User Permissions**: Expense editing limited to expense creators
- ✅ **Photo Uploads**: Support for user profile and group pictures via Supabase
- ✅ **Responsive Design**: Fully responsive UI for all device sizes
- ✅ **Private Routes**: Protected routes requiring authentication

## Tech Stack

**Frontend:**
- **[React](https://react.dev/)** - JavaScript UI library
- **[Vite](https://vitejs.dev/)** - Next-generation build tool and dev server
- **[React Router DOM](https://reactrouter.com/)** - Client-side routing

**Data & Communication:**
- **[Axios](https://axios-http.com/)** - HTTP client for API requests
- **[Supabase](https://supabase.com/)** - Backend-as-a-Service for file storage

**UI & Visualization:**
- **[Recharts](https://recharts.org/)** - React charting library
- **[React Select](https://react-select.com/)** - Accessible select component
- **CSS3** - Styling and responsive design

**Development:**
- **[ESLint](https://eslint.org/)** - JavaScript linter
- **[Node.js](https://nodejs.org/)** - JavaScript runtime

**Deployment:**
- **[Vercel](https://vercel.com/)** - Frontend hosting and deployment

## Project Structure

```
fair-share-client/
├── index.html                    # HTML entry point
├── package.json                  # Project dependencies
├── vite.config.js                # Vite configuration
├── vercel.json                   # Vercel deployment config
├── src/
│   ├── main.jsx                  # React app entry point
│   ├── App.jsx                   # Main app component
│   ├── App.css                   # Main app styles
│   ├── index.css                 # Global styles
│   ├── context/
│   │   └── auth.context.jsx      # Authentication context
│   ├── Components/
│   │   ├── Header.jsx            # Header navigation
│   │   ├── Header.css
│   │   ├── Footer.jsx            # Footer component
│   │   ├── Footer.css
│   │   ├── SideBar.jsx           # Navigation sidebar
│   │   ├── SideBar.css
│   │   ├── IsPrivate.jsx         # Route protection wrapper
│   │   ├── Overview.jsx          # Overview dashboard
│   │   ├── Overview.css
│   │   ├── Expenses.jsx          # Expense list view
│   │   ├── Expenses.css
│   │   ├── ExpenseCard.jsx       # Individual expense card
│   │   ├── ExpenseCard.css
│   │   ├── Add/
│   │   │   ├── AddExpense.jsx    # Add expense form
│   │   │   ├── AddExpense.css
│   │   │   ├── AddGroup.jsx      # Add group form
│   │   │   └── AddGroup.css
│   │   └── ExpenseOverview/
│   │       ├── GroupView.jsx     # Group-level overview
│   │       ├── GroupView.css
│   │       ├── PersonalView.jsx  # Personal statistics view
│   │       └── PersonalView.css
│   ├── Pages/
│   │   ├── HomePage.jsx          # Main dashboard page
│   │   ├── HomePage.css
│   │   ├── LandingPage.jsx       # Landing/welcome page
│   │   ├── LandingPage.css
│   │   ├── LoginPage.jsx         # User login page
│   │   ├── LoginPage.css
│   │   ├── SignUpPage.jsx        # User registration page
│   │   ├── SignUpPage.css
│   │   ├── DetailsPage.jsx       # Group/expense details page
│   │   ├── DetailsPage.css
│   │   ├── UserProfilePage.jsx   # User profile management
│   │   └── UserProfilePage.css
│   ├── utils/
│   │   └── config.js             # API configuration
│   └── assets/
│       └── images/               # Image assets
└── public/                       # Static files
```

## Installation

### Prerequisites

- Node.js (v14 or higher)
- npm or yarn
- Git

### Steps

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd fair-share-client
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Create environment variables**
   ```bash
   cp .env.example .env.local
   ```

4. **Update .env.local file** with your configuration:
   ```
   VITE_API_URL=http://localhost:5005
   VITE_SUPABASE_URL=your_supabase_url
   VITE_SUPABASE_KEY=your_supabase_key
   ```

## Configuration

### Vite Configuration (`vite.config.js`)

The Vite configuration is set up with React plugin support for JSX transformation and Fast Refresh.

### Environment Variables

| Variable | Description |
|----------|-------------|
| `VITE_API_URL` | Backend API server URL |
| `VITE_SUPABASE_URL` | Supabase project URL |
| `VITE_SUPABASE_KEY` | Supabase API key |

### Authentication Context (`src/context/auth.context.jsx`)

Provides global authentication state management for the application including:
- User login/logout
- Token management
- User data persistence
- Protected route access

## Running the Application

### Development Mode

Start the development server with hot reload:
```bash
npm run dev
```

The application will be available at `http://localhost:5173` (or the next available port)

### Production Build

Create an optimized production build:
```bash
npm run build
```

### Preview Production Build

Preview the production build locally:
```bash
npm run preview
```

### Linting

Check for code quality issues:
```bash
npm run lint
```

## Components Overview

### Authentication Components

- **LoginPage**: User login interface with email and password validation
- **SignUpPage**: User registration with personal information
- **IsPrivate**: Higher-order component for route protection

### Navigation Components

- **Header**: Top navigation bar with user profile and logout
- **SideBar**: Side navigation for groups and main sections
- **Footer**: Application footer

### Data Display Components

- **Overview**: Main dashboard showing financial summaries
- **Expenses**: List of all expenses in selected group
- **ExpenseCard**: Individual expense display card
- **GroupView**: Group-specific financial overview
- **PersonalView**: User's personal financial summary

### Form Components

- **AddExpense**: Form to create new expenses with group selection
- **AddGroup**: Form to create new expense groups
- **UserProfilePage**: User profile editing and management

### Pages

- **LandingPage**: Welcome page for unauthenticated users
- **HomePage**: Main authenticated dashboard
- **DetailsPage**: Detailed view of groups and expenses
- **UserProfilePage**: User account and profile management

## Key Features Explained

### 1. User Authentication

Users must create an account and log in to access the app. Authentication uses JWT tokens stored in localStorage.

### 2. Group Management

- Create groups for organizing expenses
- Only group creators (admins) can edit group details
- Add multiple users to a group
- Upload custom group profile pictures

### 3. Expense Tracking

- Create expenses within groups
- Specify which group members owe/paid
- Only expense creators can edit their expenses
- Attach invoice photos via Supabase

### 4. Financial Calculations

The app automatically calculates:
- **Paid**: Total amount user has paid
- **Borrowed**: Total amount user owes
- **Balance**: Net balance (paid - borrowed)
- **Total**: Sum of all transactions

These metrics are provided at both group and personal levels.

### 5. Data Visualization

- Expense charts and graphs using Recharts
- Personal and group-level financial overviews
- Visual representation of financial relationships

## Authentication

The application implements JWT-based authentication:

1. **User Registration**: New users create an account with email and password
2. **Login**: Users authenticate and receive a JWT token
3. **Token Storage**: Token is stored in localStorage for persistence
4. **Protected Routes**: Only authenticated users can access the app
5. **Route Guards**: `IsPrivate` component wraps protected routes
6. **Token Expiration**: Tokens expire based on backend configuration

## Build & Deployment

### Vercel Deployment

The application is configured for deployment on Vercel:

```bash
npm run build
```

Vercel automatically deploys from the main branch. Configuration is in `vercel.json`.

### Building for Production

```bash
npm run build
```

This creates an optimized production build in the `dist/` directory.

## Authors

- **Lee Kiowa Roy Fiala**
  - [LinkedIn](https://www.linkedin.com/in/lee-kiowa-fiala/)
  - [GitHub](https://github.com/kiowafg/)

- **Alvaro Sarria Rico**
  - [LinkedIn](https://www.linkedin.com/in/alsarria-dev/)
  - [GitHub](https://github.com/alsarria-dev)

## Acknowledgements


- Marcel Bosch Espin
- Nisol Medina Perozo
- Tania Futakova
- Mikel Jimenez Calcedo
- Arnaldo Mera Rojas

---

**Deployed**: [Fair Share App](https://app-fair-share.vercel.app)  
**License**: MIT
