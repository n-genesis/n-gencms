# N-GenCMS

![Version](https://img.shields.io/badge/version-1.0.0-blue?style=for-the-badge)
[![Framework](https://img.shields.io/badge/Framework-CodeIgniter%204.7.4-EE4326?style=for-the-badge&logo=codeigniter)](https://codeigniter.com/)
[![Authentication](https://img.shields.io/badge/Auth-Shield%201.4.0-blue?style=for-the-badge)](https://github.com/codeigniter4/shield)

[![License](https://img.shields.io/badge/license-Proprietary-lightgrey?style=for-the-badge)](#license)
[![Status](https://img.shields.io/badge/Status-Active%20Development-success?style=for-the-badge)](#)


**N-GenCMS** is a lightweight, high-performance custom Content Management System built explicitly for streamlined website administration. Developed on top of the robust **CodeIgniter 4** framework by **N-Gen Design**, this application eliminates system bloat, providing clients with an intuitive, distraction-free dashboard while giving developers clean MVC architecture and absolute control.

---

## ✨ Features

- **Quick Management Panel:** Color-coded action cards allowing immediate page creation, article publishing, and media handling.
- **Secure Authentication:** Integrated with CodeIgniter Shield for robust session management, role-based access control, and password hashing.
- **Template Architecture:** Modular template file handling to completely separate business logic from the design layer.
- **Granular Access Control:** Structured separation between daily front-facing content management and core system settings.
- **Optimized Engine:** Zero plugin bloat, delivering blazing-fast page load times and structural security.

---

## 🛠️ Tech Stack & Requirements

- **PHP:** 8.1 or higher (with `intl`, `mbstring`, `curl` extensions enabled)
- **Framework:** CodeIgniter 4.7.4
- **Authentication Engine:** CodeIgniter Shield 1.4.0+
- **Database:** MySQL 8.0+ / MariaDB 10.5+
- **Server:** Apache (with `mod_rewrite` enabled) or Nginx

---

## 🚀 Installation & Setup

Follow these steps to set up the CMS locally or deploy it to a server:

### 1. Clone the Repository
```bash
git clone https://github.com/n-genesis/n-gencms.git
cd n-gencms
```

### 2. Install Dependencies
Ensure you have Composer installed globally, then run:
```bash
composer install
```

### 3. Environment Configuration
Copy the sample environment file to create your active `.env`:
```bash
cp env .env
```
Open the `.env` file and configure your base URL and database credentials:
```env
# Set environment to development or production
CI_ENVIRONMENT = development

# App Settings
app.baseURL = 'http://localhost/ngencms/'

# Database Settings
database.default.hostname = localhost
database.default.database = ngen_cms_db
database.default.username = root
database.default.password = your_password
database.default.DBDriver = MySQLi
```

### 4. Initialize Authentication Framework (CodeIgniter Shield)
Set up the authentication configurations, service providers, and secure routing filters:
```bash
php spark shield:setup
```

### 5. Database Migrations & Seeders
Run the system migrations to construct the database schema (including core application and Shield authentication tables) and seed your initial accounts:
```bash
php spark migrate --all
php spark db:seed AdminSeeder
```

### 6. Start the Development Server
```bash
php spark serve
```
Navigate to `http://localhost/ngencms` to view the website, or `http://localhost/ngencms/admin/login` to access the login dashboard guarded by Shield.

---

## 📂 Directory Structure Highlight
While the application preserves CodeIgniter's secure structure, core custom implementations reside here:
* `app/Config/Auth.php` — Custom authentication rules, groups, and permission matrixes.
* `app/Controllers/Admin/` — Handles dashboard actions, system profiles, and user management.
* `app/Views/admin/` — Holds the custom UI panel, components, and layout views.
* `public/assets/` — Stores CSS styles, custom scripts, and client-uploaded images.

---

## 🔒 Security & Optimization
- **Session & Token Security:** Handled automatically by Shield with secure password hashing and tracking.
- **CSRF Protection:** Enabled globally via CodeIgniter security filters on all content operations forms.
- **Strict Routing:** Automatic routing is disabled (`$routes->setAutoRoute(false)`) to ensure all application routes are explicitly declared and protected by auth filters.

---

## 📄 License
Distributed under a **Proprietary License**. Commercial use, distribution, or modification without the express written permission of **N-Gen Design** is strictly prohibited.

---
*Developed with ❤️ by [N-Gen Design](https://ngendesign.net)*
