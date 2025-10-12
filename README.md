# Apache Airflow DAG Scripts & Examples

![Apache Airflow](https://img.shields.io/badge/Apache%20Airflow-017CEE?style=for-the-badge&logo=apache-airflow&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=for-the-badge&logo=prometheus&logoColor=white)

A comprehensive collection of **Apache Airflow DAG examples** covering beginner to advanced use cases, including operators, sensors, XCom, webhooks, ETL pipelines, and complete monitoring setup with Prometheus and Grafana.

## 📋 Table of Contents

- [Project Overview](#-project-overview)
- [Repository Structure](#-repository-structure)
- [DAG Examples](#-dag-examples)
- [Monitoring Setup](#-monitoring-setup)
- [Getting Started](#-getting-started)
- [Learning Path](#-learning-path)
- [Prerequisites](#-prerequisites)
- [Contributing](#-contributing)

## 🎯 Project Overview

This repository provides **production-ready Airflow examples** that demonstrate:

- **Basic to Advanced Operators** (Bash, Python, Sensors)
- **Workflow Orchestration** patterns and best practices
- **Inter-task Communication** with XCom
- **Error Handling** and retry mechanisms
- **External Integrations** (Databases, Webhooks, APIs)
- **Real-world ETL Pipelines** with modern tools
- **Complete Monitoring** with Prometheus & Grafana

## 📁 Repository Structure

```
Airflow-Dag-Scripts/
├── 📂 Example_01_Bash_Operator/           # Basic bash operations
├── 📂 Example_02_Python_Operator/         # Python task execution
├── 📂 Example_03_Branching_and_Dummy/     # Conditional workflows
├── 📂 Example_04_XCom_and_Kwargs/         # Inter-task communication
├── 📂 Example_05_Master_and_Child_Xcom/   # Complex XCom patterns
├── 📂 Example_06_Capture_LongRunningDags/ # Performance monitoring
├── 📂 Example_07_Database_Connection/     # Database integrations
├── 📂 Example_08_Sensors/                 # File and time sensors
├── 📂 Example_09_Webhook_Notifications/   # Teams webhook integration
├── 📂 Example_10_NYC_Taxi_Pipeline/       # Real-world data pipeline
├── 📂 Example_11_Advanced_ETL_DuckDB_Pipeline/ # Modern ETL with DuckDB
├── 📂 Example_12_Dynamic_DAG_Factory/     # Dynamic DAG generation
├── 📂 monitoring/                         # Complete monitoring stack
└── 📄 README.md                          # This file
```

---

## 🔧 DAG Examples

### **Beginner Level**

| Example | Concept | Description | Features |
|---------|---------|-------------|----------|
| [**01_Bash_Operator**](./Example_01_Bash_Operator/) | **Basic Operations** | Execute bash commands in Airflow | `BashOperator`, Task dependencies, Templating |
| [**02_Python_Operator**](./Example_02_Python_Operator/) | **Python Tasks** | Run Python functions as tasks | `PythonOperator`, Function parameters, Return values |
| [**03_Branching_and_Dummy**](./Example_03_Branching_and_Dummy/) | **Conditional Logic** | Implement conditional workflows | `BranchPythonOperator`, `DummyOperator`, Decision trees |

### **Intermediate Level**

| Example | Concept | Description | Features |
|---------|---------|-------------|----------|
| [**04_XCom_and_Kwargs**](./Example_04_XCom_and_Kwargs/) | **Data Passing** | Share data between tasks | `XCom`, Task context, `**kwargs` |
| [**05_Master_and_Child_Xcom**](./Example_05_Master_and_Child_Xcom/) | **Complex XCom** | Advanced inter-task communication | Master-child patterns, Data serialization |
| [**06_Capture_LongRunningDags**](./Example_06_Capture_LongRunningDags/) | **Performance** | Monitor and analyze DAG performance | Long-running task detection, Performance metrics |
| [**07_Database_Connection**](./Example_07_Database_Connection/) | **Database Integration** | Connect to SQL databases | `SqlOperator`, Connection management, Data extraction |
| [**08_Sensors**](./Example_08_Sensors/) | **Event Detection** | Wait for files and time conditions | `FileSensor`, `TimeSensor`, Event-driven workflows |

### **Advanced Level**

| Example | Concept | Description | Features |
|---------|---------|-------------|----------|
| [**09_Webhook_Notifications**](./Example_09_Webhook_Notifications/) | **External Integration** | Microsoft Teams notifications | Webhook integration, Alert systems, Error notifications |
| [**10_NYC_Taxi_Pipeline**](./Example_10_NYC_Taxi_Pipeline/) | **Real-world ETL** | Complete data pipeline example | Data ingestion, Transformation, Loading patterns |
| [**11_Advanced_ETL_DuckDB_Pipeline**](./Example_11_Advanced_ETL_DuckDB_Pipeline/) | **Modern ETL** | Advanced pipeline with DuckDB | Modern data stack, Analytics-ready data, Performance optimization |
| [**12_Dynamic_DAG_Factory**](./Example_12_Dynamic_DAG_Factory/) | **Dynamic DAGs** | Generate DAGs programmatically | DAG factory patterns, Configuration-driven workflows |

---

## 📊 Monitoring Setup

**Location**: [`monitoring/`](./monitoring/)

Complete observability stack for Airflow with:

### **Components**
- 🔍 **Prometheus**: Metrics collection and storage
- 📊 **Grafana**: Visualization and dashboards
- 📈 **StatsD Exporter**: Airflow metrics forwarding
- 🐳 **Docker Compose**: Easy deployment

### **Features**
- ✅ **Real-time Metrics**: DAG runs, task duration, success rates
- ✅ **Custom Dashboards**: Pre-built Airflow dashboard
- ✅ **Alerting**: Configurable alerts for failures
- ✅ **Historical Analysis**: Long-term performance trends

### **Quick Setup**
```bash
cd monitoring
docker-compose up -d
```

**Access Points:**
- 📊 **Grafana**: http://localhost:3000 (admin/admin)
- 🔍 **Prometheus**: http://localhost:9090
- 📈 **Metrics**: http://localhost:9102/metrics

---

## 🚀 Getting Started

### **1. Install Apache Airflow**

Create virtual environment and install Airflow:

```bash
# Create virtual environment
python -m venv airflow-env
source airflow-env/bin/activate  # On Windows: airflow-env\Scripts\activate

# Upgrade pip
pip install --upgrade pip

# Install Airflow
pip install "apache-airflow==2.7.3"

# For database support (optional)
pip install "apache-airflow[postgres,mysql]==2.7.3"
```

### **2. Initialize Airflow**

```bash
# Initialize database
airflow db init

# Create admin user
airflow users create \
    --username admin \
    --firstname Admin \
    --lastname User \
    --role Admin \
    --email admin@example.com \
    --password admin
```

### **3. Start Airflow**

**Quick Start (Development):**
```bash
airflow standalone
```

**Production Setup:**
```bash
# Terminal 1: Start webserver
airflow webserver --port 8080

# Terminal 2: Start scheduler
airflow scheduler
```

**Access:** http://localhost:8080 (admin/admin)

### **4. Deploy DAG Examples**

```bash
# Copy DAG files to Airflow dags folder
cp Example_*/code.py ~/airflow/dags/

# Or set custom DAGs folder
export AIRFLOW__CORE__DAGS_FOLDER=/path/to/this/repo
```

### **5. Enable Monitoring (Optional)**

```bash
# Start monitoring stack
cd monitoring
docker-compose up -d

# Configure Airflow metrics in ~/airflow/airflow.cfg
[metrics]
statsd_on = True
statsd_host = localhost
statsd_port = 8125
statsd_prefix = airflow

# Restart Airflow
```

---

## 📚 Learning Path

### **Fundamentals**
1. **Basic Operators**: [Examples 01-02](./Example_01_Bash_Operator/)
2. **Task Dependencies**: Understanding DAG structure
3. **Airflow UI**: Navigation and monitoring

### **Intermediate Concepts**
1. **Conditional Logic**: [Example 03](./Example_03_Branching_and_Dummy/)
2. **Data Passing**: [Examples 04-05](./Example_04_XCom_and_Kwargs/)
3. **External Systems**: [Examples 07-08](./Example_07_Database_Connection/)

### **Advanced Patterns**
1. **Real-world Pipelines**: [Examples 10-11](./Example_10_NYC_Taxi_Pipeline/)
2. **Dynamic DAGs**: [Example 12](./Example_12_Dynamic_DAG_Factory/)
3. **Monitoring**: [Complete setup](./monitoring/)

### **Production Readiness**
1. **Error Handling**: Retry strategies and alerts
2. **Performance**: [Example 06](./Example_06_Capture_LongRunningDags/)
3. **Integration**: [Example 09](./Example_09_Webhook_Notifications/)

---

## 🛠️ Useful Airflow CLI Commands

### **DAG Management**
```bash
# List all DAGs
airflow dags list

# Trigger DAG manually
airflow dags trigger <dag_id>

# Pause/Unpause DAG
airflow dags pause <dag_id>
airflow dags unpause <dag_id>

# Show DAG structure
airflow dags show <dag_id>
```

### **Task Operations**
```bash
# List tasks in DAG
airflow tasks list <dag_id>

# Test single task
airflow tasks test <dag_id> <task_id> <execution_date>

# Clear task instances
airflow tasks clear <dag_id> --start-date <YYYY-MM-DD>
```

### **Troubleshooting**
```bash
# Re-serialize DAGs
airflow dags reserialize

# Check DAG parsing errors
airflow dags list-import-errors

# View logs
airflow tasks logs <dag_id> <task_id> <execution_date>
```

---

## 🔧 Prerequisites

### **Software Requirements**
- **Python 3.8+** (3.9+ recommended)
- **pip** package manager
- **Docker** (for monitoring stack)
- **Git** for version control

### **Optional Dependencies**
```bash
# Database drivers
pip install psycopg2-binary  # PostgreSQL
pip install mysqlclient      # MySQL

# Additional operators
pip install apache-airflow-providers-postgres
pip install apache-airflow-providers-http
pip install apache-airflow-providers-ftp
```

### **System Requirements**
- **RAM**: 4GB minimum, 8GB recommended
- **Storage**: 10GB for examples and logs
- **Network**: Internet access for package downloads

---

## 💡 Real-World Use Cases

### **Data Engineering**
- 🏭 **ETL Pipelines**: Extract, transform, load data workflows
- 📊 **Data Quality**: Automated data validation and cleansing
- 🔄 **Data Sync**: Keeping systems in sync with scheduled updates

### **DevOps & Automation**
- 🚀 **CI/CD Integration**: Automated deployment workflows
- 📱 **System Monitoring**: Health checks and automated responses
- 🗂️ **File Processing**: Automated file ingestion and processing

### **Business Intelligence**
- 📈 **Report Generation**: Scheduled business report creation
- 🎯 **KPI Calculation**: Automated metric computation
- 📧 **Alert Systems**: Automated business alerts and notifications

---

## 🤝 Contributing

This is an educational repository focused on Airflow learning. Contributions welcome:

- 💡 **New Examples**: Add more DAG patterns or use cases
- 🐛 **Bug Fixes**: Improve existing examples or documentation
- 📚 **Documentation**: Enhance explanations or add tutorials
- 🔧 **Optimizations**: Performance improvements or best practices

For major changes, please open an issue first to discuss your ideas.

---

## 🔗 Useful Links

- [Apache Airflow Documentation](https://airflow.apache.org/docs/)
- [Airflow Best Practices](https://airflow.apache.org/docs/apache-airflow/stable/best-practices.html)
- [Airflow Operators](https://airflow.apache.org/docs/apache-airflow/stable/howto/operator/)
- [Airflow Providers](https://airflow.apache.org/docs/apache-airflow-providers/)
- [Prometheus Metrics](https://prometheus.io/docs/introduction/overview/)

---

**Happy Orchestrating! 🚀**

*This repository provides a comprehensive journey through Apache Airflow workflow orchestration. Use these examples to build production-ready data pipelines and automation workflows!*

## 🚀 Getting Started

### 1. Install Apache Airflow

We recommend using a virtual environment.

```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
pip install --upgrade pip
pip install apache-airflow
```

Or, for a specific Airflow version:

```bash
pip install "apache-airflow==2.7.3"
```

> For MySQL/Postgres support, add the relevant extras, e.g.:
> `pip install "apache-airflow[mysql]==2.7.3"`

### 2. Initialize Airflow

```bash
airflow db init
```

### 3. Start Airflow (Standalone)

For quick testing, use:

```bash
airflow standalone
```

This will start the webserver and scheduler, and create an admin user (shown in the output).

- Web UI: http://localhost:8080
- Default user: `admin` / password shown in terminal

### 4. Add Example DAGs

Copy or symlink the example DAG `.py` files into your Airflow `dags/` folder (default: `~/airflow/dags/`).

```bash
cp Example_*/code.py ~/airflow/dags/
```

Or set the `AIRFLOW__CORE__DAGS_FOLDER` environment variable to point to this repo.

### 5. Start/Stop Airflow Services (Advanced)

To run components separately:

```bash
airflow webserver --port 8080
airflow scheduler
```

## 🛠️ Useful Airflow CLI Commands

- List all DAGs:
  ```bash
  airflow dags list
  ```
- List all tasks in a DAG:
  ```bash
  airflow tasks list <dag_id>
  ```
- Trigger a DAG run manually:
  ```bash
  airflow dags trigger <dag_id>
  ```
- Pause/Unpause a DAG:
  ```bash
  airflow dags pause <dag_id>
  airflow dags unpause <dag_id>
  ```
- Show DAG structure as ASCII:
  ```bash
  airflow dags show <dag_id>
  ```
- Test a task (does not affect DB state):
  ```bash
  airflow tasks test <dag_id> <task_id> <execution_date>
  ```
- Re-serialize all DAGs (useful for troubleshooting DAG parsing issues):
  ```bash
  airflow dags reserialize
  ```
- Clear task instances:
  ```bash
  airflow tasks clear <dag_id> --start-date <YYYY-MM-DD> --end-date <YYYY-MM-DD>
  ```

## 📊 Monitoring Stack (Optional)

To enable metrics and dashboards:

1. Go to the `monitoring/` directory:

    ```bash
    cd monitoring
    ```

2. Start Prometheus, Grafana, and StatsD exporter:

    ```bash
    docker-compose up -d
    ```

3. Enable Airflow metrics in `airflow.cfg`:

    ```
    [metrics]
    statsd_on = True
    statsd_host = localhost
    statsd_port = 8125
    statsd_prefix = airflow
    ```

4. Restart Airflow.

- Grafana: http://localhost:3000 (admin/admin)
- Prometheus: http://localhost:9090

## 🧹 Cleanup

To stop Airflow:

```bash
# If using standalone
pkill -f airflow

# Or stop webserver/scheduler individually
airflow webserver --stop
airflow scheduler --stop
```

To stop monitoring stack:

```bash
cd monitoring
docker-compose down -v
```

---

For more details, see the comments in each DAG file.
