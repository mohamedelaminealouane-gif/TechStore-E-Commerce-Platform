# 🛒 TechStore  E-Commerce Platform for Tech & Home Appliances

> **A full-stack e-commerce web application built with Laravel and MySQL, featuring a complete storefront, shopping experience, and admin dashboard  all styled with Bootstrap.**

![Laravel](https://img.shields.io/badge/Laravel-FF2D20?style=flat-square&logo=laravel&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white)
![Bootstrap](https://img.shields.io/badge/Bootstrap-7952B3?style=flat-square&logo=bootstrap&logoColor=white)
![PHP](https://img.shields.io/badge/PHP-777BB4?style=flat-square&logo=php&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)

---



## 🧠 About the Project

**TechStore** is a fully functional e-commerce platform designed for selling tech products and home appliances. It provides customers with a smooth shopping experience — from browsing products and managing a cart to placing and tracking orders — while giving administrators full control over the catalog, orders, and users through a dedicated back-office dashboard.

Built on the **Laravel** MVC framework with a **MySQL** database and **Bootstrap** UI, TechStore is clean, responsive, and ready to scale.

---

## ✨ Features

### 🧑‍💻 Customer Side
- 🔐 **Authentication** — Register, login, and logout securely
- 🛍️ **Product Catalog** — Browse tech products and home appliances with search and filtering
- 📄 **Product Detail Pages** — Full product info, images, and specs
- 🛒 **Shopping Cart** — Add, update, and remove items in real time
- 📦 **Order Placement** — Checkout flow with order confirmation
- 📋 **Order History** — View past and current orders with status tracking
- 👤 **User Profile** — Manage personal info and account settings

### 🛠️ Admin Dashboard
- 📊 **Dashboard Overview** — Key stats at a glance (orders, revenue, users)
- 📦 **Product Management** — Add, edit, delete products with images and categories
- 🗂️ **Category Management** — Organize catalog by product type
- 🧾 **Order Management** — View all orders, update statuses, manage fulfillment
- 👥 **User Management** — View and manage registered customers
- 🔑 **Role-Based Access** — Admin and customer roles with protected routes

---

## 🗂️ Tech Stack

| Layer | Technology |
|-------|------------|
| Backend framework | [Laravel](https://laravel.com) (PHP) |
| Database | MySQL |
| Frontend | Bootstrap 5, Blade templates |
| Authentication | Laravel Breeze / Auth |
| ORM | Eloquent ORM |
| Templating | Laravel Blade |
| Asset management | Vite / Laravel Mix |

---

## 🗃️ Database Schema (Overview)

```
users           → id, name, email, password, role, timestamps
categories      → id, name, slug, description, timestamps
products        → id, category_id, name, slug, description, price, stock, image, timestamps
orders          → id, user_id, total_price, status, timestamps
order_items     → id, order_id, product_id, quantity, unit_price, timestamps
cart_items      → id, user_id, product_id, quantity, timestamps
```

---

## 🚀 Getting Started

### Prerequisites

Make sure you have the following installed:

- PHP >= 8.1
- Composer
- MySQL
- Node.js & npm
- Laravel CLI

### Installation

**1. Clone the repository**
```bash
git clone https://github.com/your-username/techstore.git
cd techstore
```

**2. Install PHP dependencies**
```bash
composer install
```

**3. Install Node dependencies**
```bash
npm install && npm run build
```

**4. Set up environment variables**
```bash
cp .env.example .env
php artisan key:generate
```

**5. Configure your database** — Edit `.env` with your MySQL credentials:
```env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=techstore
DB_USERNAME=root
DB_PASSWORD=your_password
```

**6. Run migrations and seed the database**
```bash
php artisan migrate --seed
```

**7. Start the development server**
```bash
php artisan serve
```

Visit `http://localhost:8000` — the store is live!

---

## 🔐 Default Credentials (after seeding)

| Role | Email | Password |
|------|-------|----------|
| Admin | admin@techstore.com | password |
| Customer | user@techstore.com | password |


## 📁 Project Structure

```
techstore/
├── app/
│   ├── Http/Controllers/
│   │   ├── Admin/          ← Admin dashboard controllers
│   │   └── Shop/           ← Customer-facing controllers
│   ├── Models/             ← Eloquent models
│   └── Middleware/         ← Role-based access middleware
├── database/
│   ├── migrations/         ← Database schema
│   └── seeders/            ← Sample data
├── resources/
│   └── views/
│       ├── admin/          ← Admin dashboard Blade views
│       ├── shop/           ← Storefront Blade views
│       └── layouts/        ← Shared layouts
├── routes/
│   └── web.php             ← Web routes (admin + customer)
└── public/                 ← Public assets
```

---

## 🛤️ Routes Overview

| Method | URI | Description |
|--------|-----|-------------|
| GET | `/` | Homepage / product catalog |
| GET | `/products/{slug}` | Product detail page |
| GET | `/cart` | Shopping cart |
| POST | `/cart/add` | Add item to cart |
| POST | `/orders` | Place an order |
| GET | `/orders` | Customer order history |
| GET | `/admin/dashboard` | Admin dashboard |
| GET | `/admin/products` | Manage products |
| GET | `/admin/orders` | Manage orders |
| GET | `/admin/users` | Manage users |

---

## 🔒 Role-Based Access

- **Customers** can browse, add to cart, checkout, and view their own orders.
- **Admins** have access to the full dashboard via a protected `/admin` route group, enforced by middleware.

Unauthorized access to admin routes redirects to the homepage with an error.

---

## 📸 Screenshots

> *(Replace with your actual screenshots)*

| Page | Preview |
|------|---------|
| Homepage | `screenshots/homepage.png` |
| Product Page | `screenshots/product.png` |
| Shopping Cart | `screenshots/cart.png` |
| Admin Dashboard | `screenshots/admin.png` |

---

## 🤝 Contributing

Contributions are welcome! Please fork the repo, create a feature branch, and open a pull request.

```bash
git checkout -b feature/your-feature-name
git commit -m "feat: add your feature"
git push origin feature/your-feature-name
```

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).

---

*Built with ❤️ using Laravel · MySQL · Bootstrap*
