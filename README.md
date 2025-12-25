# Airflow
Apache Airflow

# INSTALLATION

python3.12 -m venv airflow_venv

source airflow_venv/bin/activate

# Set AIRFLOW_HOME
This is where Airflow stores configs and DAGs

export AIRFLOW_HOME=~/airflow

# INSTALL APACHE AIRFLOW
AIRFLOW_VERSION=3.1.3

PYTHON_VERSION="$(python -c 'import sys; print(f"{sys.version_info.major}.{sys.version_info.minor}")')"

CONSTRAINT_URL="https://raw.githubusercontent.com/apache/airflow/constraints-${AIRFLOW_VERSION}/constraints-${PYTHON_VERSION}.txt"

pip install "apache-airflow==${AIRFLOW_VERSION}" --constraint "${CONSTRAINT_URL}"



-- Airflow does not have default credentials for the web UI
# DB Migration
airflow db migrate
# Create User
airflow users create \
    --username krishna \
    --firstname Krishna \
    --lastname Tamada \
    --role Admin \
    --email admin@example.com

--NOTE
In recent Airflow versions, user management is done via the web UI or the standalone command, not the old airflow users create CLI.

# run standalone
airflow standalone


# Start Server
airflow api-server
