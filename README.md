# El Greco Art Explorer – Full-Stack Web App for Artwork Browsing & Admin Management

<p align="center">
  <a href="https://github.com/AntonisXT/el-greco-art-platform/releases">
    <img src="https://img.shields.io/github/v/release/AntonisXT/el-greco-art-platform?color=2ea44f&label=Version" alt="version">
  </a>
  <img src="https://img.shields.io/badge/Node.js-18%2B-43853d?logo=node.js&logoColor=white" alt="Node.js">
  <img src="https://img.shields.io/badge/Express.js-Backend-000000?logo=express&logoColor=white" alt="Express">
  <img src="https://img.shields.io/badge/MongoDB-Database-4ea94b?logo=mongodb&logoColor=white" alt="MongoDB">
  <img src="https://img.shields.io/github/actions/workflow/status/AntonisXT/el-greco-art-platform/ci.yml?label=Build&logo=github" alt="build status">
  <img src="https://img.shields.io/badge/Deployed%20on-Vercel-000000?logo=vercel&logoColor=white" alt="vercel">
  <a href="LICENSE"><img src="https://img.shields.io/badge/License-MIT-blue" alt="license"></a>
</p>

<p align="center">
  <img src="docs/demo.gif" alt="El Greco Art Platform Demo" width="720">
</p>

> A full-stack educational and portfolio-oriented web application for exploring El Greco’s artworks.  
> Features a secure admin CMS, a documented REST API, and a lightweight frontend for artwork, exhibition, and content browsing.

---

## 🌐 Live Deployment

- **Frontend (Vercel):** [el-greco-art-explorer.vercel.app](https://el-greco-art-explorer.vercel.app)
- **Backend (Render):** [el-greco-art-explorer.onrender.com](https://el-greco-art-explorer.onrender.com)
- **API Docs (Swagger):** [el-greco-art-explorer.onrender.com/api/docs](https://el-greco-art-explorer.onrender.com/api/docs)

---

## 📚 Table of Contents
- [Overview](#-overview)
- [Key Features](#-key-features)
- [Tech Stack](#-tech-stack)
- [Security](#-security)
- [Architecture](#-architecture)
- [Public Navigation & User Experience](#-public-navigation--user-experience)
- [Administrator Management](#-administrator-management)
- [Project Structure](#-project-structure)
- [Setup Instructions](#-setup-instructions)
- [API Documentation](#-api-documentation)
- [Testing & CI/CD](#-testing--cicd)
- [Performance & Scalability](#-performance--scalability)
- [Screenshots](#-screenshots)
- [Versions](#-versions)
- [Roadmap](#-roadmap)
- [Contributing](#-contributing)
- [License](#-license)

---

## 🚀 Overview

The **El Greco Art Explorer** is a full-stack web application built as an academic and portfolio project.  
It provides an interactive way to browse the artworks, exhibitions, and biography of **Doménikos Theotokópoulos (El Greco)**, along with a secure admin dashboard for content management.

Developed to practice full-stack architecture, backend security, clean REST API design, and modern frontend patterns, the project demonstrates real-world application structure without aiming to be a commercial platform.

---

## ✨ Key Features

- 🧱 **Full-Stack Architecture** - Clear separation of backend logic, database models, and frontend rendering for maintainability.  
- 🔒 **Secure Authentication** - JWT-based admin system with HttpOnly cookies, CSRF protection, rate limiting, and server-side validation.  
- 🧹 **Data Sanitization & Validation** - Prevents XSS and ensures integrity across all CRUD operations.  
- ⚡ **Optimized Performance** - Server-side pagination and query optimization for large collections (paintings, exhibitions, links).  
- 📘 **Comprehensive REST API** - Fully documented with OpenAPI 3.0 (Swagger UI).  
- 🖥️ **Admin CMS Dashboard** - Secure interface for creating, updating, and organizing all platform content.  
- 💡 **Responsive Frontend** - Built with Vanilla JS (ES Modules) and async data fetching for real-time UI updates.  
- 🚀 **Automated CI/CD** - GitHub Actions for linting, testing (Jest/Supertest), and deployment to Render & Vercel.  

---

## 🧩 Tech Stack

| Layer | Technology |
|-------|-------------|
| **Frontend** | HTML5, CSS3, Vanilla JS (ES Modules) |
| **Backend** | Node.js, Express.js |
| **Database** | MongoDB (Mongoose) |
| **Security** | Helmet, CSRF, sanitize-html, JWT, Rate Limiting |
| **Testing** | Jest, Supertest |
| **Documentation** | OpenAPI 3.0 + Swagger UI |
| **CI/CD** | GitHub Actions |
| **Deployment** | Render (Backend), Vercel (Frontend) |

---

## 🔒 Security

- **Authentication & Access**
  - JWT authentication via HttpOnly cookies for a secure single-role admin system.  
  - Session refresh mechanism automatically renews JWT and CSRF tokens every 8 hours for long-lived sessions.  

- **Security Middleware**
  - Helmet with a custom **Content Security Policy (CSP)** to prevent XSS and clickjacking attacks.  
  - Rate limiting for authentication routes and brute-force protection.  
  - CSRF protection using the **double submit cookie** method.  
  - Input sanitization powered by `sanitize-html` for safe user-managed content.  

- **Validation & Error Handling**
  - Centralized request validation with **Joi** for consistent schema enforcement.  
  - Unified and secure API error responses for predictable client behavior.  

- **Cookie & CORS Configuration**
  - Secure cookie attributes (`HttpOnly`, `SameSite`, `Secure`) aligned with Render–Vercel deployment setup.  
  - Controlled cross-origin access between frontend and backend for safe API communication.  

---

## 🧱 Architecture

- **System Architecture**
  - Full-stack setup connecting the **Vercel-hosted frontend**, **Render backend**, and **MongoDB Atlas** database through secure REST APIs over HTTPS.  
  - Follows a client–server model with cookie-based authentication and stateless API design.  

- **Backend Architecture**
  - Modular **Express.js** structure with separate layers for routes, middleware, models, validation, and security.  
  - Built for scalability and maintainability with clear separation of concerns.  

- **Frontend Architecture**
  - Lightweight **Vanilla JS (ES Modules)** interface hosted on Vercel.  
  - Uses async API calls for dynamic data rendering and real-time content updates.  

- **Database Layer**
  - **MongoDB + Mongoose** schemas for artworks, exhibitions, biography, links, and categories.  
  - Optimized read performance via `.lean()` queries and indexed collections.  

- **API Design**
  - RESTful endpoints with consistent CRUD patterns.  
  - Fully documented using **OpenAPI 3.0 (Swagger UI)** for testing and integration.  

- **Error Handling & Logging**
  - Centralized error middleware provides structured and meaningful responses.  
  - Designed for easier debugging and monitoring in production environments.  

- **Scalability & Configuration**
  - Server-side pagination and optimized queries for large datasets.  
  - Environment-based configuration via `.env` for flexible multi-environment deployment.  

---

## 🖼️ Public Navigation & User Experience

The public interface allows visitors to **explore El Greco’s artworks, exhibitions, and biography** interactively.

- **Main Menu** – Top navigation gives access to key sections: *Biography*, *Paintings*, *Exhibitions*, and *Links*, presenting El Greco’s journey in a structured way.  
- **Sidebar Subcategories** – Each section includes thematic subcategories for intuitive browsing.  
- **Dynamic Content Rendering** – The interface updates instantly based on user selections, maintaining a fluid, gallery-like experience. 

---

## 👤 Administrator Management

The administrator dashboard provides complete control over all platform content, ensuring a secure and efficient content management experience.

**Admin Capabilities**
- Dedicated dashboard with secure authentication and session handling.  
- Full **CRUD operations** for:
  - **Paintings**, **Exhibitions**, **Biography**, **Subcategories**, and **Links**  
- Real-time interface updates with instant validation, success, and error feedback.  
- Structured input forms for consistent and reliable data management.  

---

## 🧱 Project Structure

```plaintext
el-greco-art-platform/
│
├─ backend/                            # Express.js backend (API, security, validation)
│   ├─ config/                         # Database and environment configuration
│   │   └─ db.js
│   │
│   ├─ middleware/                     # Custom Express middlewares
│   │   ├─ authMiddleware.js           # JWT authentication & authorization
│   │   ├─ csrfMiddleware.js           # CSRF protection (double submit cookie)
│   │   ├─ errorHandler.js             # Centralized error handling
│   │   └─ rateLimiter.js              # Login rate limiter
│   │
│   ├─ models/                         # Mongoose models (MongoDB collections)
│   │   ├─ biography.js
│   │   ├─ biographySection.js
│   │   ├─ category.js
│   │   ├─ exhibition.js
│   │   ├─ linkItem.js
│   │   ├─ painting.js
│   │   ├─ subcategory.js
│   │   └─ user.js
│   │
│   ├─ routes/                         # Express route controllers
│   │   ├─ authRoutes.js               # Login / Logout / Check / Refresh
│   │   ├─ categoryRoutes.js           # CRUD for categories & subcategories
│   │   ├─ biographyRoutes.js          # CRUD for biography sections
│   │   ├─ paintingRoutes.js           # Upload & CRUD for paintings
│   │   ├─ exhibitionRoutes.js         # CRUD for exhibitions
│   │   ├─ linkRoutes.js               # CRUD for related links
│   │   └─ index.js                    # Root API router
│   │
│   ├─ scripts/                        # Utility and seeding scripts
│   │   └─ seed-admin.js               # Creates initial admin user
│   │
│   ├─ server/                         # Core backend logic & helpers
│   │   ├─ security/                   # Security policies (Helmet, CSP)
│   │   │   ├─ csp.js
│   │   │   └─ index.js
│   │   ├─ utils/                      # Helper utilities
│   │   │   ├─ paginate.js             # Generic pagination helper
│   │   │   ├─ slugifyElToKey.js       # Slug generator for subcategories
│   │   │   └─ sanitizeHtml.js         # HTML sanitization
│   │   ├─ validation/                 # Joi validation schemas
│   │   │   ├─ schemas.js
│   │   │   └─ validate.js
│   │   └─ index.js                    # Exports core middlewares and setup
│   │
│   └─ server.js                       # Main Express application entry point
│
├─ frontend/                           # Static frontend (Vercel deployment)
│   ├─ index.html                      # Main entry page
│   ├─ js/                             # ES modules for UI & API communication
│   │   ├─ app.js                      # Dashboard and UI logic
│   │   ├─ auth.js                     # JWT, CSRF & session refresh handling
│   │   ├─ fetchData.js                # API fetch utilities
│   │   └─ text.js                     # Dynamic content rendering
│   └─ css/                            # Stylesheets and layout
│       └─ style.css
│
├─ docs/                               # Documentation & visual assets
│   ├─ openapi.yaml                    # Full OpenAPI 3.0 specification
│   ├─ demo.gif                        # Demo preview animation
│   └─ screenshots/                    # UI and dashboard screenshots
│
├─ .github/workflows/ci.yml            # GitHub Actions for CI (lint + test)
├─ .env.example                        # Example environment configuration
├─ vercel.json                         # Vercel rewrites and headers
├─ package.json                        # Node.js dependencies & scripts
└─ README.md                           # Project documentation
```

### 🧭 Highlights
- **backend/** - Modular Express.js backend with routes, middleware, models, validation, and security logic. 
- **frontend/** - Secure, lightweight Vanilla JS interface for admin and public content.  
- **docs/** - Full OpenAPI documentation and project visuals.  
- **scripts/** - Automation scripts (e.g., admin seeding).  
- **CI/CD** - GitHub Actions, Render, and Vercel integration for automated testing and deployment.

---

## 💻 Setup Instructions

### 1. Clone & Install
```bash
git clone https://github.com/AntonisXT/el-greco-art-platform.git
cd el-greco-art-platform/backend
npm install
```

### 2. Configure Environment
```bash
cp .env.example .env
# Add MONGO_URI, JWT_SECRET, FRONTEND_ORIGIN, etc.
```

### 3. Seed Admin User
```bash
node scripts/seed-admin.js <username> <password>
```

### 4. Run Backend
```bash
npm run dev
```

### 5. Serve Frontend (optional)
```bash
npx serve ../frontend

> When serving the frontend locally, ensure `FRONTEND_ORIGIN` in `.env` matches your local URL (e.g. `http://localhost:5500`), otherwise CORS or CSRF may block requests.

```

---

## 🧠 API Documentation
Full OpenAPI spec is available at:
- [`docs/openapi.yaml`](docs/openapi.yaml)
- [Swagger UI → API Docs](https://el-greco-art-explorer.onrender.com/api/docs)

---

## 🧪 Testing & CI/CD
- **Testing:** Implemented with Jest & Supertest for API validation and endpoint smoke tests.  
- **Continuous Integration:** GitHub Actions workflow runs linting, testing, and build checks on each commit.  
- **Continuous Deployment:** Automated deployment to **Vercel** (frontend) and **Render** (backend), ensuring smooth integration and delivery.  
- **Node.js Version:** Recommended Node.js 20+ for full compatibility with CI environments.

---

## ⚡ Performance & Scalability

- Efficient pagination helper for large collections (paintings, exhibitions, links).
- Image uploads limited to 10MB per file to maintain stability.  
- `.lean()` queries used for faster read operations in MongoDB.
- Session refresh mechanism implemented for automatic renewal of JWT and CSRF tokens
- Future plan: enable caching and compression headers for improved performance.
- Future plan: migrate image storage to cloud object storage (e.g., S3 or Supabase) for better scalability.  

---

## 📸 Screenshots

#### 🏛️ Public View
| Biography | Paintings |
|------------|------------|
| ![Biography](docs/screenshots/public-biography.jpg) | ![Paintings](docs/screenshots/public-paintings.jpg) |

| Exhibitions | Links |
|--------------|--------|
| ![Exhibitions](docs/screenshots/public-exhibitions.jpg) | ![Links](docs/screenshots/public-links.jpg) |

---

#### ⚙️ Admin Panel
| Login | Manage Subcategories |
|------------|----------------------|
| ![Dashboard](docs/screenshots/admin-dashboard.jpg) | ![Subcategories](docs/screenshots/crud-subcategory.jpg) |

| Edit Biography | Manage Paintings |
|----------------|------------------|
| ![Biography Edit](docs/screenshots/biography-edit.jpg) | ![Paintings Manage](docs/screenshots/paintings-manage.jpg) |

| Manage Exhibitions | Manage Links |
|--------------------|---------------|
| ![Exhibitions Manage](docs/screenshots/exhibitions-manage.jpg) | ![Links Manage](docs/screenshots/links-manage.jpg) |

---

## 🧭 Versions

| Version | Highlights |
|----------|-------------|
| **v1.0** | LocalStorage-based admin, CRUD only for exhibitions & links, minimal UI |
| **v2.0 (current)** 🟢 | Major refactor with modular backend, Single-role admin authentication (JWT-based), expanded data models, complete admin dashboard, enhanced security layers, and redesigned responsive UI/UX |

> 🏷️ [View Release Notes → v2.0.0](https://github.com/AntonisXT/el-greco-art-platform/releases/tag/v2.0.0)

---

### 🚀 Roadmap

#### 🖥️ UI & UX
- [ ] Improve mobile responsiveness  
- [ ] Add dark mode  
- [ ] Add Greek / English Localization

#### ⚙️ Backend & Performance
- [ ] Image preview & lazy loading  
- [ ] Migrate image storage to cloud (S3/Supabase)  
- [ ] Add compression & caching headers  
- [ ] Full-text search functionality

#### 🧠 Features & Intelligence
- [ ] AI artwork tagging  
- [ ] Add analytics dashboard  

#### 🔒 Security & Roles
- [ ] Multi-admin roles & permissions  
- [ ] Expand automated testing coverage  

---

## 🤝 Contributing

This project was developed as a personal academic and portfolio project.  
Contributions, bug reports, or feature suggestions are welcome via GitHub issues or pull requests.

---

## 📜 License
[MIT License](LICENSE) © 2025 [AntonisXT](https://github.com/AntonisXT)

---

<p align="center">
  Built with ❤️ by 
  <a href="https://www.linkedin.com/in/antonios-tsiakiris" target="_blank">Antonios Tsiakiris</a>
</p>
