---

````markdown
# Apache Airflow + PostgreSQL Integration (Windows Docker)

This repository demonstrates how to set up **Apache Airflow** using **Docker on Windows**, and run a DAG that connects to a **PostgreSQL** database to insert data.

> ✅ Ideal for developers and data engineers looking to experiment with Airflow and Postgres in a local development Docker environment.

---

## 🚀 Project Overview

This demo includes:

- Apache Airflow (2.7+) running via Docker Compose
- PostgreSQL database container
- A custom DAG that:
  - Connects to the PostgreSQL instance
  - Inserts sample data into a table

---

## 🛠️ Prerequisites

- [Docker Desktop for Windows](https://www.docker.com/products/docker-desktop)
- Git

---

## 🧱 Folder Structure

```bash
.
├── dags/
│   └── insert_postgres_data.py      # Sample DAG to insert data into PostgreSQL
├── docker-compose.yaml              # Docker Compose setup for Airflow + Postgres
├── .env                             # Environment variables (Airflow UID/GID)
└── README.md
````

---

## 🧪 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/anantkabi/airflow_postgress_connectivity_win_docker.git
cd airflow_postgress_connectivity_win_docker
```
### 2. Setup docker-compose.yaml file and ensure right dependencies are listed

### 3. Initialize Airflow 

```bash
docker-compose up airflow-init
```

### 3. Start All Services

```bash
docker-compose up
```

### 4. Access the Airflow UI

Open your browser and go to:
🔗 [http://localhost:8080](http://localhost:8080)

* Username: `airflow`
* Password: `airflow`

### 5. Ensure a connection named `postgres_airflow_conn` is configured in the Airflow UI under **Admin > Connections**.

---

## 🗃️ PostgreSQL Details. 

* Host: `postgres`
* Port: `5432`
* Username: `airflow`
* Password: `airflow`
* Database: `airflow`

you can access the database via DBeaver which provide native connections to Postgres running locally
---

## 📅 Sample DAG – `postgres_connecter.py`

This DAG:

* Creates a sample table (if it doesn’t exist)
* Inserts a test record into the table

You can trigger it manually via the Airflow UI.

---

## 🧹 Stopping the Environment

```bash
docker-compose down
```

To remove all volumes and start fresh:

```bash
docker-compose down --volumes --remove-orphans
```

---

## 📌 Notes

* This setup is tested on **Windows 10/11** using **Docker Desktop (WSL2)**.
* Volume mappings are designed for Windows paths.
* Compatible with other platforms with minor tweaks.

---

## 📬 Feedback or Contributions?

Feel free to open issues or submit pull requests.
Created with 💻 by [Anant Kabi](https://github.com/anantkabi)

```

---

Let me know if you'd like a version with screenshots, badges, or setup instructions for Mac/Linux.
```
