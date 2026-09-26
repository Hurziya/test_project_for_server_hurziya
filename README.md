# 🛍️ Product API

A simple RESTful API for managing products, built with Django and Django REST Framework. Fully containerized with Docker for easy setup and local development.

![Python](https://img.shields.io/badge/Python-3.12-blue)
![Django](https://img.shields.io/badge/Django-REST%20Framework-green)
![Docker](https://img.shields.io/badge/Docker-ready-blue)

## 📋 Table of Contents

- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Getting Started](#-getting-started)
- [API Endpoints](#-api-endpoints)
- [Project Structure](#-project-structure)

## ✨ Features

- Full CRUD operations for products (create, read, update, delete)
- Product model with name, price, and description
- Auto-tracked creation and update timestamps
- Clean, minimal REST API built with DRF's `ModelViewSet`

## 🛠 Tech Stack

- **Backend:** Python, Django, Django REST Framework
- **Database:** PostgreSQL
- **Containerization:** Docker, Docker Compose

## 🚀 Getting Started

### Requirements

- [Docker](https://www.docker.com/) and Docker Compose installed on your machine

### Steps

**1. Clone the repository:**

```bash
git clone https://github.com/HURZIYA/test_project_for_server.git
cd test_project_for_server
```

**2. Start the containers:**

```bash
docker-compose up -d --build
```

**3. Apply migrations:**

```bash
docker-compose exec web python manage.py migrate
```

**4. Create a superuser (for admin access):**

```bash
docker-compose exec web python manage.py createsuperuser
```

Once running, the app will be available at:

```
http://127.0.0.1:8000/
```

## 📖 API Endpoints

| Method | Endpoint          | Description               |
|--------|-------------------|----------------------------|
| GET    | `/api/products/`      | List all products          |
| POST   | `/api/products/`      | Create a new product       |
| GET    | `/api/products/{id}/` | Retrieve a single product  |
| PUT    | `/api/products/{id}/` | Update a product           |
| PATCH  | `/api/products/{id}/` | Partially update a product |
| DELETE | `/api/products/{id}/` | Delete a product           |

**Admin panel:** [http://127.0.0.1:8000/admin/](http://127.0.0.1:8000/admin/)

### Product fields

| Field         | Type     | Notes                        |
|---------------|----------|-------------------------------|
| `name`        | string   | Max 250 characters            |
| `price`       | decimal  | Up to 10 digits, 2 decimals   |
| `description` | text     |                                |
| `created_at`  | datetime | Set automatically on creation |
| `updated_at`  | datetime | Updated automatically on save |

## 📁 Project Structure

```
test_project_for_server/
├── core/                # Django app (models, serializers, views)
├── config/              # Project settings
├── docker-compose.yml
├── Dockerfile
├── requirements.txt
└── manage.py
```

