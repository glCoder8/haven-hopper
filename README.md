# Haven Hopper

## Overview
Haven Hopper is a rental application that allows users to browse, search, and book rentals. It includes role-based access control for admins, hosts (rental owners), and users. The platform supports multiple payment methods and host applications.

## 📦 Technologies Used
- **Backend**: Laravel 11
- **Frontend**: Vue.js, Inertia.js, TailwindCSS
- **Admin Panel**: FilamentPHP 3
- **Database**: MySQL
- **Payment Integration**: Stripe

---

## 🔑 User Roles & Permissions
### 1. Admin
- Approves/rejects rental listings.
- Approves/rejects host applications.
- Manages all data.
- Creates and manages amenities.
- Manages locations.
- Checks activity logs.

### 2. Host (Rental Owner)
- Can create and manage rental listings.
- Can approve cash payment bookings.

### 3. User
- Can browse and search rentals.
- Must register and log in to book rentals.
- Can apply to become a host.

### 4. Visitor
- Can browse and search available rentals.
- Cannot book rentals without registration.

---

## 📌 Features
### 1. Rental Management
- Hosts can create rentals.
- Rentals require admin approval before appearing on the homepage.

### 2. Booking System
- Users can book rentals.
- Payment methods:
  - **Cash**: Requires host approval.
  - **Stripe**: No manual approval required.

### 3. Host Application Process
- Users register first and verify their email.
- Users can apply to become a host by submitting a form.
- Admins can approve or reject host applications.

### 4. Search & Filtering
- Visitors and users can search rentals based on:
  - Category
  - Location
  - Total guests
  - Available dates

### 5. Authentication & Authorization
- Users must register and log in to book rentals.
- Email verification is required before applying as a host.
- Admins manage all approvals and data.

### 6. Admin Panel Enhancements
- Admins can create and manage **amenities**.
- Admins can manage **locations**.
- Admins can **check activity logs** for tracking actions.

---

## 💻 Installation Guide
### Prerequisites
- PHP 8.2+
- Composer
- Node.js & npm
- MySQL or any other configured database

### Setup Steps
1. Clone the repository:
   ```sh
   git clone https://github.com/glCoder8/haven-hopper.git
   cd haven-hopper
   ```
2. Install dependencies:
   ```bash
   composer install
   npm install && npm run build
   ```
3. Set up environment variables:
   ```bash
   cp .env.example .env
   php artisan key:generate
   ```
   - Configure database credentials in `.env`.
4. Run migrations and seed data:
   ```bash
   php artisan migrate --seed
   ```
5. Set up storage
   ```bash
   php artisan storage:link
   ```
6. Configure mail client from `.env`
7. Start the development server:
   ```bash
   php artisan serve
   npm run dev
   ```

---

## 📈 Some Endpoints
### Authentication
- `POST /register` - Register a new user.
- `POST /login` - Authenticate user.
- `POST /logout` - Log out user.

### Rentals
- `GET /rentals` - List all rentals.
- `GET /rentals/{id}` - Get rental details.

### Booking
- `POST /bookings` - Create a booking.
- `GET /bookings` - List user bookings.

### Host Actions
- `GET /host` - Host Dashboard.

### Admin Actions
- `GET /admin` - Admin Dashboard.

### All Endpoints
    ```bash
    php artisan route:list --except-vendor
    ```

---

## 🚀 Deployment
- Configure `.env` for production.
- Use `php artisan config:cache` for optimized configuration.
- Set up a queue worker for background jobs:
  ```bash
  php artisan queue:work
  ```

