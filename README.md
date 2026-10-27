# E-Commerce Web Application

A full-stack, responsive E-Commerce web application built with **Laravel** and **Bootstrap**. It features a modern storefront with product browsing, real-time search, category and tag filtering, session-based shopping cart, coupon codes, checkout, order processing, and a full administrative control panel powered by Laravel Voyager.

---

## Features

- **Storefront & Catalog**:
  - Featured products showcase and "Hot Sales" section.
  - Category, tag, and price filtering for intuitive product discovery.
  - Detailed single-product view with pricing and image galleries.
- **Search System**:
  - Live search functionality with keyword querying across products.
- **Shopping Cart**:
  - Robust session-based shopping cart allowing add, update quantity, and remove operations with dynamic subtotal and tax calculation.
- **Checkout & Orders**:
  - Checkout flow with coupon discount code support.
  - Automated order creation and order confirmation email notifications.
- **Admin Panel (Laravel Voyager)**:
  - Dedicated admin dashboard at `/admin` for site administration.
  - Complete BREAD (CRUD) operations for Products, Categories, Orders, Tags, and Users.
  - Analytics and visitor tracking.
- **User Authentication**:
  - Built-in user authentication (Registration, Login, Password Reset, and Role-Based Access Control).

---

## Prerequisites

Ensure you have the following installed on your machine:

- **PHP** >= 8.0 (with required extensions: `openssl`, `pdo`, `mbstring`, `tokenizer`, `xml`, `ctype`, `json`, `sqlite3` or `pdo_mysql`)
- **Composer** (PHP dependency manager)
- **Node.js** (v14+ recommended) & **NPM**
- **Database**: MySQL / MariaDB **or** SQLite

---

## Step-by-Step Installation Guide

Follow these steps to set up and run the project locally on your PC:

### 1. Clone the Repository
Open your terminal (PowerShell, Command Prompt, or Bash) and clone the repository:
```bash
git clone https://github.com/Kanikashri19/E-Commerce.git
cd E-Commerce
```

### 2. Install PHP Dependencies
Install backend dependencies via Composer:
```bash
composer install
```

### 3. Install Frontend Dependencies & Build Assets
Install npm packages and compile CSS/JS assets:
```bash
npm install
npm run dev
```

### 4. Configure Environment Variables
Copy the example environment configuration file:

- **Windows (Command Prompt / PowerShell):**
  ```powershell
  copy .env.example .env
  ```
- **macOS / Linux:**
  ```bash
  cp .env.example .env
  ```

#### Database Configuration (Choose one option):

- **Option A: SQLite (Quickest & easiest, no database server required)**
  1. Create an empty SQLite database file inside the `database` folder:
     - Windows PowerShell:
       ```powershell
       New-Item -ItemType File -Path "database/database.sqlite" -Force
       ```
     - Linux/macOS:
       ```bash
       touch database/database.sqlite
       ```
  2. Open your `.env` file and set:
     ```env
     DB_CONNECTION=sqlite
     ```
     *(Comment out or leave blank `DB_HOST`, `DB_PORT`, `DB_DATABASE`, `DB_USERNAME`, `DB_PASSWORD`)*

- **Option B: MySQL / MariaDB**
  1. Create a new database in MySQL (e.g. named `ecommerce`):
     ```sql
     CREATE DATABASE ecommerce;
     ```
  2. Open `.env` and set your database credentials:
     ```env
     DB_CONNECTION=mysql
     DB_HOST=127.0.0.1
     DB_PORT=3306
     DB_DATABASE=ecommerce
     DB_USERNAME=root
     DB_PASSWORD=your_password
     ```

### 5. Generate Application Key
Generate the unique application encryption key:
```bash
php artisan key:generate
```

### 6. Run Database Migrations & Seed Dummy Data
Run the custom automated installer to create tables, seed sample products, categories, tags, demo orders, and set up storage symlinks:
```bash
php artisan ecommerce:install
```
> When prompted for confirmation, type `yes` to proceed.

### 7. Start the Local Development Server
Start the local Laravel development server:
```bash
php artisan serve
```

---

## Accessing the Application

Once the server is running, open your web browser and navigate to:

- **Storefront**: [http://127.0.0.1:8000/](http://127.0.0.1:8000/)
- **Admin Panel**: [http://127.0.0.1:8000/admin](http://127.0.0.1:8000/admin)

### Default Admin Credentials
- **Email:** `admin@admin.com`
- **Password:** `password`

---

## Useful Artisan Commands

- Clear compiled views cache:
  ```bash
  php artisan view:clear
  ```
- Clear application cache:
  ```bash
  php artisan cache:clear
  ```
- Recompile frontend assets in watch mode during development:
  ```bash
  npm run watch
  ```

---

## Author & Contact

- **Name:** Kanika Shrivastava
- **Phone:** +91 7224001779
- **Email:** [kanishri.19@gmail.com](mailto:kanishri.19@gmail.com)
- **GitHub:** [@Kanikashri19](https://github.com/Kanikashri19)
- **LinkedIn:** [Kanika Shrivastava](https://www.linkedin.com/in/kanika-shrivastava-34405828b/)

---

## License

This project is open-source and available under the [MIT License](LICENSE).
