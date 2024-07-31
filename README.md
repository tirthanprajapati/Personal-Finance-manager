# Personal Finance Manager

## Project Overview

The Personal Finance Manager is a web application designed to help users track their expenses, plan budgets, manage income, and set financial goals. The application features data visualization for income vs. expenses and integrates with bank APIs for automatic transaction updates.

## Features

- **Expense Tracking:** Track daily, weekly, monthly, and yearly expenses.
- **Budget Planning:** Set and manage budgets for various categories.
- **Income Management:** Log and manage different sources of income.
- **Financial Goal Setting:** Set and track financial goals with deadlines.
- **Data Visualization:** Visualize income vs. expenses using charts.
- **Bank API Integration:** Integrate with bank APIs for automatic transaction updates.

## System Design

### Architecture Overview

- **Frontend:** React.js
- **Backend:** Node.js with Express.js
- **Database:** MongoDB
- **Authentication:** JWT (JSON Web Tokens) for user authentication and authorization
- **Data Visualization:** Chart.js or D3.js for charts
- **Bank API Integration:** Plaid API (or similar) for transaction updates
- **Hosting:** Frontend on Netlify or Vercel, Backend on Heroku or DigitalOcean

### Component Breakdown

1. **Frontend (React.js):**
   - **Authentication:**
     - Login Component
     - Signup Component
   - **Dashboard:**
     - Overview Component (summary of financial status)
     - Expense Tracking Component
     - Budget Planning Component
     - Income Management Component
     - Financial Goals Component
     - Charts Component (income vs. expenses)
   - **Settings:**
     - User Profile Component
     - Bank Account Integration Component

2. **Backend (Express.js):**
   - **Authentication Routes:**
     - `/api/auth/login` (POST)
     - `/api/auth/signup` (POST)
     - `/api/auth/logout` (POST)
   - **User Routes:**
     - `/api/user/profile` (GET, PUT)
   - **Finance Routes:**
     - `/api/expenses` (GET, POST, PUT, DELETE)
     - `/api/income` (GET, POST, PUT, DELETE)
     - `/api/budget` (GET, POST, PUT, DELETE)
     - `/api/goals` (GET, POST, PUT, DELETE)
     - `/api/charts` (GET)
   - **Bank Integration Routes:**
     - `/api/bank/link` (POST)
     - `/api/bank/transactions` (GET)

### Database Schema

1. **User:**
   ```json
   {
     "id": "ObjectId",
     "username": "string",
     "password": "string",
     "email": "string",
     "profile": {
       "name": "string",
       "age": "number",
       "currency": "string"
     },
     "bankAccounts": ["ObjectId"]
   }