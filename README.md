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

## Connecting to a Test VM via Guacamole

This Dockerized test setup runs Apache Guacamole, a web-based remote desktop gateway. It allows you to securely access an Ubuntu virtual machine (with SSH) directly from your browser. No additional client software is needed — just a browser.

You can use it to:

- Remotely log into the Ubuntu VM
- Test SSH access to other systems (e.g., localhost, external servers)
- Manage connections via a clean web interface

### Steps to Add a New SSH Connection

1. Go to `Settings` → `Connections` → `New Connection`
2. Fill in the following:

#### For the test Ubuntu VM:

- **Name**: `ubuntu-lab-test` (or any name)
- **Location**: `Root`
- **Protocol**: `SSH`

**Parameters:**

- **Network**
  - **Hostname**: `ubuntu-lab`
  - **Port**: `22`
  - **Connection Timeout**: `30`

- **Authentication**
  - **Username**: `root`
  - **Password**: `root`

Click **Save**.

3. Return to the **Home** screen → Click the connection to test SSH login.

---

### To Test Other Systems or VMs:

Use the following values:

- **Name**: `<any name>`
- **Location**: `Root`
- **Protocol**: `SSH`

**Parameters:**

- **Network**
  - **Hostname**: `<public-ip of the machine to connect>`
  - **Port**: `22`
  - **Connection Timeout**: `30`

- **Authentication**
  - **Username**: `<username of the machine>`
  - **Password**: `root`
  - **OR Private Key**: (Paste private SSH key or `.pem` content)

Click **Save** and test the connection from the **Home** screen.

---

## Maintainers

Ong DevOps Team

---

## Note: 
This is just a sample Guacamole for connecting VMs

---

## License

This project is maintained by the Ong DevOps Team. See repository for license details.
