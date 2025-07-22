# Dockerized Guacamole

This repository sets up [Apache Guacamole](https://guacamole.apache.org/) using Docker Compose with PostgreSQL as the backend.

---

## Prerequisites

- Docker
- Docker Compose
- Git

---

## Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/Ong-DevOps-Team/Dockerized-guacamole.git
cd Dockerized-guacamole
```

---

### 2. Start All Containers

Run the following command to spin up the containers:

```bash
docker compose up -d
```

This will start:

- `guacamole`: The Apache Guacamole web application
- `guacd`: The Guacamole proxy daemon
- `guacamole_postgres`: PostgreSQL database for Guacamole

---

## Access Guacamole

Once everything is running, access Guacamole in your browser:

```
http://localhost:8080/guacamole/
```

Default credentials:

- Username: `guacadmin`
- Password: `guacadmin`

> It is recommended to change the default password after your first login.

---



## Maintainers

Ong DevOps Team

---

## License

This project is maintained by the Ong DevOps Team. See repository for license details.
