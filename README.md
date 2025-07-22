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

### 3. Initialize the PostgreSQL Database Schema

You need to initialize the Guacamole schema in the PostgreSQL database by executing the schema SQL file.

#### Step 1: Copy the schema SQL file into the PostgreSQL container

```bash
docker cp full-schema.sql guacamole_postgres:/tmp/full-schema.sql
```

#### Step 2: Enter the PostgreSQL container

```bash
docker exec -it guacamole_postgres bash
```

#### Step 3: Run the SQL schema inside the container

```bash
psql -U guacamole_user -d guacamole_db -f /tmp/full-schema.sql
```

---

### 4. Restart the Guacamole Container

Restart the Guacamole container so it picks up the initialized database:

```bash
docker restart guacamole
```

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
