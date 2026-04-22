# Data Pipeline with Apache Airflow and Open Library API

## 📌 Overview
This project is an ETL (Extract, Transform, Load) pipeline built using Apache Airflow. It extracts book data from the Open Library API, processes and cleans the data, and prepares it for downstream usage such as storage or analysis. The pipeline demonstrates workflow orchestration, API data ingestion, and data transformation using DAGs.

---

## 🛠️ Tech Stack
- Apache Airflow
- Python
- Docker & Docker Compose
- PostgreSQL
- Open Library API

---

## ⚙️ Setup & Run Instructions

1. Clone the repository and enter the project folder:

   git clone https://github.com/MessyaCarment05/Book_ETL_Project.git  

---

2. Create environment file:

   Copy `.env.example` to `.env`, then edit:

   POSTGRES_PASSWORD=your_db_password  

---

3. Start all services:

   docker-compose up  

---

## 🌐 Access Airflow UI

4. Open in browser:

   http://localhost:8080  

5. Login credentials:
   - Username: admin  
   - Password: check file `airflow/standalone_admin_password.txt`

---

## 🔌 Airflow Connection Setup

6. Go to:
   Admin → Connections → Add New Connection  

7. Fill in the connection:

   - Connection Id: book_connection  
   - Connection Type: Postgres  
   - Host: postgres  
   - Database: airflow  
   - Login: airflow  
   - Password: from `.env` (POSTGRES_PASSWORD)  
   - Port: 5432  

8. Save the connection

---

## ▶️ Run the DAG

9. Go to DAGs tab  
10. Select your DAG  
11. Click Trigger DAG  

---

## 📊 Monitoring

12. Monitor execution using:
   - Graph View → task dependencies  
   - Grid View → task status  
   - Logs → execution details  

---

## 📂 Project Structure

project-root/

├── airflow/  
│   ├── dags/                          → Airflow DAG files  
│   ├── logs/                          → runtime logs (ignored in git)  
│   ├── airflow.cfg                    → Airflow configuration (ignored in git)  
│   ├── airflow.db                     → local SQLite database (ignored in git)  
│   ├── airflow-webserver.pid          → runtime process file (ignored in git)  
│   ├── webserver_config.py            → local webserver config (ignored in git)  
│   ├── standalone_admin_password.txt  → auto-generated login password (ignored in git)  
├── extract_and_cleaning_data.py       → scratch script for testing API / logic  
├── docker-compose.yml                 → Docker services configuration  
├── .env                               → local environment variables (NOT pushed)  
├── .env.example                       → environment template  
├── README.md                          → project documentation  
├── myenv/                             → virtual environment (NOT pushed)  

---

## 📌 Data Source
- Open Library API: https://openlibrary.org/dev/docs/api/search

---

## ⚠️ Notes
- This project runs entirely in a local Docker environment  
- API data may contain missing or null values (handled in pipeline)  
- All Airflow runtime/generated files are ignored in git  
- This project is for learning and portfolio purposes  

---

## 📄 License
This project is for educational and portfolio use only.
