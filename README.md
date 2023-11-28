# Database Management Setup Script 

## Overview

The DBM setup script is a Python script designed to facilitate database management tasks, including user and schema creation, extension installation, and checking PostgreSQL statistics. This document provides instructions on how to set up and use the script.

## Prerequisites

Before using the script, ensure the following prerequisites are met:

- Python 3.10 is installed on your system.
- PostgreSQL is installed and running.
- The necessary PostgreSQL client library (libpq) is installed.

## Setup

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/yourusername/dbm2.git
   cd dbm2
2. Create a Virtual Environment:

   ```
   make venv
   ```


3. Edit the `.env`` in the project directory and add the following environment variables with your PostgreSQL connection details:
   ```
   DBHOST=your_database_host
   PORT=your_database_port
   DBNAME=your_database_name
   DBUSER=your_database_user
   PASSWORD=your_database_password
   ```

4. Run the Script:
   * This command activates the virtual environment, installs/upgrades dependencies, and executes the `dbm_setup.py` script.
   ```
   make run
   ```

### Review Output:
The script will output information about the progress of tasks, such as user creation, schema creation, and PostgreSQL statistics checks.

#### Testing the script
You can test the script on a docker container to see how this works before running on your database.

To run a Postgres Docker container for testing, runt he docker command below from repo root directory:
```
docker run -d --name postgres-container -p 5432:5432 \              
  -e POSTGRES_PASSWORD=postpass \
  -v $(pwd)/postgresql.conf:/etc/postgresql/postgresql.conf \
  postgres -c 'config_file=/etc/postgresql/postgresql.conf'
```

![Alt text](<./img/Screen Recording 2023-11-28 at 10.11.06 AM.gif>)

### Check PostgreSQL Statistics:
After running the script, review the console output to ensure that PostgreSQL connections, activity, and statistics are reported correctly.
