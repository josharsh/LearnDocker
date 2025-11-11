# 🐳 Contribution: Docker Compose Tutorial

This tutorial explains how to use **Docker Compose** — a tool that helps you manage multi-container Docker applications easily with a single YAML file.

---

## 🚀 What is Docker Compose?

Docker Compose helps you:
- Define **multiple containers** and their relationships in one `docker-compose.yml` file.
- Start, stop, and rebuild all your services with a single command.
- Manage environment variables, networks, and volumes efficiently.

---

## 🧩 Basic `docker-compose.yml` Structure

Here’s a minimal example:

```yaml
name: project-name

services:
  web:
    image: nginx:latest
    ports:
      - "8080:80"
    volumes:
      - ./html:/usr/share/nginx/html

  app:
    build: ./app
    environment:
      - APP_ENV=local
    depends_on:
      - db

  db:
    image: mysql:8
    environment:
      MYSQL_ROOT_PASSWORD: secret
      MYSQL_DATABASE: app_db
    volumes:
      - db_data:/var/lib/mysql

volumes:
  db_data:
```

---

## 🧠 Commands You Should Know

| Command | Description |
|----------|-------------|
| `docker compose up` | Starts all services defined in the file |
| `docker compose up -d` | Starts in detached mode (background) |
| `docker compose down` | Stops and removes containers, networks, and volumes |
| `docker compose build` | Builds images for services |
| `docker compose logs` | Shows logs for all services |
| `docker compose ps` | Lists running services |

---

## ⚙️ Using Environment Variables

You can store configuration in a `.env` file:

```bash
MYSQL_ROOT_PASSWORD=secret
MYSQL_DATABASE=app_db
```

Docker Compose automatically loads this file to set environment variables.

---

## 🧹 Cleaning Up

To remove containers and networks created by Docker Compose:

```bash
docker compose down
```

To also remove volumes and images:

```bash
docker compose down --volumes --rmi all
```

---

## 💡 Pro Tips

- Use `depends_on` to control startup order of containers.
- Use named volumes for persistent data.
- Use `.env` files for secrets and configuration.
- Version control your `docker-compose.yml` with your project.

---

## ✅ Summary

Docker Compose simplifies managing multiple containers — one file, one command, full control.

You can run:
```bash
docker compose up -d
```
and have your **entire application stack** up in seconds!
