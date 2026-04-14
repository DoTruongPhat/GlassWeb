# 👓 GlassStore — Eyewear E-Commerce System

> A full-stack eyewear store management system built with **Spring Boot 3** (REST API) and **React** (frontend). Supports custom glasses design, prescription management, cart & order workflow, and staff operations.

<p>
  <img src="https://img.shields.io/badge/Java-21-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white"/>
  <img src="https://img.shields.io/badge/Spring_Boot-3.2.2-6DB33F?style=for-the-badge&logo=spring-boot&logoColor=white"/>
  <img src="https://img.shields.io/badge/Spring_Security-JWT-6DB33F?style=for-the-badge&logo=spring-security&logoColor=white"/>
  <img src="https://img.shields.io/badge/React-18-61DAFB?style=for-the-badge&logo=react&logoColor=black"/>
  <img src="https://img.shields.io/badge/SQL_Server-CC2927?style=for-the-badge&logo=microsoft-sql-server&logoColor=white"/>
  <img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white"/>
</p>

---

## 📋 Table of Contents
- [Features](#-features)
- [System Architecture](#-system-architecture)
- [Tech Stack](#-tech-stack)
- [API Overview](#-api-overview)
- [Getting Started](#-getting-started)
- [Project Structure](#-project-structure)
- [Team](#-team)

---

## ✨ Features

### 👤 Customer
- Register / Login with JWT authentication
- Browse ready-made glasses (frames + lenses)
- **Custom glasses design** — choose frame + lens + options
- Upload eye prescription (file upload)
- Manage eye profile (manual input or scan upload)
- Add to cart, checkout, place orders
- Pre-order for out-of-stock items
- Track order & shipment status in real-time
- Submit reviews and ratings
- Request returns
- Receive in-app notifications

### 🛠️ Staff / Admin
- Manage products: frames, lenses, lens options, ready-made glasses
- Process manufacturing orders
- Update order & shipment statuses
- Manage discounts and promotions
- Handle return requests
- User account management

---

## 🏗️ System Architecture

```
┌──────────────────────────────────────┐
│         React Frontend (Vite)        │
│  React Router · Axios · Lucide Icons │
└─────────────────┬────────────────────┘
                  │ HTTP / REST API
┌─────────────────▼────────────────────┐
│     Spring Boot 3.2 Backend (WAR)    │
│  Spring Security · JWT · JPA · Lombok│
└─────────────────┬────────────────────┘
                  │ JPA / Hibernate
┌─────────────────▼────────────────────┐
│         SQL Server Database          │
└──────────────────────────────────────┘
```

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| Backend | Java 21, Spring Boot 3.2.2, Spring Security, Spring Data JPA |
| Authentication | JWT (jjwt 0.12.6) |
| Frontend | React 18, React Router v6, Axios, Vite |
| Database | Microsoft SQL Server |
| ORM | Hibernate / JPA |
| Utilities | Lombok, Bean Validation |
| Containerization | Docker (multi-stage build) |

---

## 🔌 API Overview

| Module | Endpoints |
|--------|-----------|
| **Auth** | `POST /api/auth/register`, `POST /api/auth/login` |
| **Products** | `GET/POST/PUT/DELETE /api/frames`, `/api/lenses`, `/api/ready-made-glasses` |
| **Glasses Design** | `GET/POST /api/glasses-designs` |
| **Eye Profile** | `GET/POST /api/eye-profile` (manual + file upload) |
| **Cart & Order** | `GET/POST /api/cart`, `POST /api/orders`, `GET /api/orders/{id}` |
| **Pre-Order** | `POST /api/pre-orders` |
| **Discount** | `GET/POST/PUT/DELETE /api/discounts` |
| **Operations** | `PUT /api/orders/{id}/status`, `/api/shipments`, `/api/manufacturing` |
| **Reviews** | `GET/POST /api/reviews` |
| **Returns** | `POST /api/returns` |
| **Notifications** | `GET /api/notifications` |
| **User Management** | `GET/PUT/DELETE /api/users` (ADMIN only) |

> All protected endpoints require `Authorization: Bearer <JWT_TOKEN>` header.

---

## 🚀 Getting Started

### Prerequisites
- Java 21+
- Maven 3.9+
- SQL Server (or Docker)
- Node.js 18+ (for frontend)

### Backend

```bash
# Clone the repository
git clone https://github.com/tennyhoang/GlassStore.git
cd GlassStore

# Configure database in src/main/resources/application.properties
spring.datasource.url=jdbc:sqlserver://localhost:1433;databaseName=GlassStore
spring.datasource.username=your_username
spring.datasource.password=your_password

# Run
./mvnw spring-boot:run
# Backend starts at http://localhost:8080
```

### Frontend

```bash
cd GlassStore-frontend
npm install
npm run dev
# Frontend starts at http://localhost:5173
```

### Docker (Backend only)

```bash
docker build -t glassstore-backend .
docker run -p 8080:8080 glassstore-backend
```

---

## 📁 Project Structure

```
GlassStore/
├── src/main/java/.../glassesweb/
│   ├── Controller/         # REST API Controllers (13 controllers)
│   │   ├── AuthController.java
│   │   ├── ProductController.java
│   │   ├── CartOrderController.java
│   │   ├── EyeProfileController.java
│   │   ├── GlassesDesignController.java
│   │   └── ...
│   ├── DTO/                # Request/Response DTOs
│   ├── Entity/             # JPA Entities (24 entities)
│   ├── Repository/         # Spring Data JPA Repositories
│   ├── Service/            # Business Logic
│   └── Security/           # JWT & Spring Security config
│
GlassStore-frontend/
├── src/
│   ├── pages/
│   │   ├── customer/       # Cart, Checkout, Design, Eye Profile...
│   │   ├── staff/          # Staff dashboard pages
│   │   └── auth/           # Login, Register
│   ├── components/         # Reusable UI components
│   └── context/            # Auth, Cart, Wishlist context
```

---

## 👥 Team

Developed as a group project (Group 5) at **FPT University Ho Chi Minh City**
— Software Engineering, Semester 5.

| Role | Contribution |
|------|-------------|
| Backend API | Spring Boot REST, JWT Auth, JPA |
| Frontend | React, React Router, Axios |
| Database | SQL Server schema design |
| DevOps | Docker multi-stage build |

---

## 📄 License

This project is for educational purposes at FPT University.

---

<p align="center">Made with ❤️ by Group 5 — FPT University HCM</p>
