## **Airflow Postgres Connectivity on Windows Docker**

### **Overview**
This repository provides a **setup guide** and configurations to integrate **Apache Airflow** with **PostgreSQL** using **Docker on Windows**. It enables seamless database connectivity for Airflow DAGs.

### **Features**
- ✅ Run **Apache Airflow** in Docker on Windows.
- ✅ Connect Airflow to **PostgreSQL**.
- ✅ Sample **DAGs** demonstrating database interactions.
- ✅ Supports **Windows-based Docker deployments**.

### **Prerequisites**
Ensure you have the following installed:
- [Docker Desktop](https://www.docker.com/products/docker-desktop)
- [Python (>=3.8)](https://www.python.org/downloads/)
- [Apache Airflow](https://airflow.apache.org/)
- [PostgreSQL](https://www.postgresql.org/download/)

### **Setup Instructions**
#### **1. Clone the Repository**
```bash
git clone https://github.com/anantkabi/airflow_postgress_connectivity_win_docker.git
cd airflow_postgress_connectivity_win_docker
```

#### **2. Start Services with Docker Compose**
```bash
docker-compose up -d
```

#### **3. Configure Airflow Connections**
1. Open **Airflow UI** at `localhost:8080`.
2. Navigate to **Admin > Connections**.
3. Add a connection:
   - **Conn Id:** `postgres_airflow_conn`
   - **Conn Type:** `Postgres`
   - **Host:** `postgres`
   - **Schema:** `<your_database_name>`
   - **Login:** `<your_username>`
   - **Password:** `<your_password>`
   - **Port:** `5432`

#### **4. Verify Airflow DAGs**
Run:
```bash
airflow dags list
```
If your DAG is missing, check the **logs**:
```bash
cat $AIRFLOW_HOME/logs/scheduler/latest.log
```

### **Usage**
- Modify existing DAGs to include PostgreSQL tasks.
- Execute DAGs via Airflow UI or CLI:
  ```bash
  airflow dags trigger <dag_id>
  ```

### **Troubleshooting**
- If Airflow **does not detect the DAG**, restart it:
  ```bash
  airflow scheduler restart
  airflow webserver restart
  ```
- If PostgreSQL **connection fails**, ensure the container is running:
  ```bash
  docker ps | grep postgres
  ```

### **Contributing**
Feel free to open **issues** or submit **pull requests** to improve the setup.
