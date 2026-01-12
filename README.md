# Laravel + React + MySQL Docker Project

This repository contains a **Dockerized full-stack project** with:

- **Laravel backend** (`backend-app`)
- **React frontend** (`frontend-app`)
- **MySQL database** (`laravel_db_data`)
- **PHPMyAdmin** for database management

---

## Folder Structure

root_folder/
├── backend-app/
├── frontend-app/
├── laravel_db_data/
└── compose.yml

---

## Prerequisites

Before running the project, make sure you have:

- **Docker** and **Docker Compose** installed
- **Git** installed
- Optional: Node.js & npm locally if you want to run frontend outside Docker

---

## 1️⃣ Clone the Repository

```bash
git clone <your-repo-url>
cd root_folder
```

---

## 2️⃣ Configure Environment Files

- Laravel backend .env.example → copy to .env

- Example backend .env database settings matches docker-compose.yml

```bash
DB_CONNECTION=mysql
DB_HOST=db
DB_PORT=3306
DB_DATABASE=laravel_db
DB_USERNAME=laravel
DB_PASSWORD="saqib123@@"
```

- Example frontend .env API URL

REACT_APP_API_URL=http://backend:8000


## 3️⃣ Start the Containers

- From the root_folder run this command

```bash
docker compose up -d --build
```

This will:

Build and start backend on http://localhost:8000

Build and start frontend on http://localhost:3000

Start MySQL database on port 3307 (host) → 3306 (container)

Start PHPMyAdmin on http://localhost:8080


## 4️⃣ Stop Containers

- To stop all containers run this command

```bash
docker compose down
```

## 5️⃣ Rebuild Containers

- If you change Dockerfile or environment variables run this command

```bash
docker compose up -d --build
```

This README.md now covers everything for a new user to clone the repo and run Laravel + React + MySQL Docker setup with PHPMyAdmin.