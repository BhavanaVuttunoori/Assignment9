# FastAPI Calculator Application - Complete Setup Guide# FastAPI Calculator Application - Complete Setup Guide# 📦 Project Setup



**Author:** Bhavana Vuttunoori   

**Project:** Assignment 9 - FastAPI Calculator with Docker**Author:** Bhavana Vuttunoori  ---
 



## 📋 Table of Contents**Project:** Assignment 9 - FastAPI Calculator with Docker# 🧩 1. Install Homebrew (Mac Only)



1. [Project Overview](#project-overview)

2. [Prerequisites](#prerequisites)

3. [Windows WSL2 Setup](#windows-wsl2-setup)---> Skip this step if you're on Windows.

4. [Docker Desktop Installation](#docker-desktop-installation)

5. [Project Setup from Scratch](#project-setup-from-scratch)

6. [Running the Application](#running-the-application)

7. [Testing the Application](#testing-the-application)## 📋 Table of ContentsHomebrew is a package manager for macOS.  

8. [Project Structure](#project-structure)

9. [Troubleshooting](#troubleshooting)You’ll use it to easily install Git, Python, Docker, etc.



---1. [Project Overview](#project-overview)



## 📖 Project Overview2. [Prerequisites](#prerequisites)**Install Homebrew:**



This is a FastAPI-based calculator application built from scratch that performs basic arithmetic operations (add, subtract, multiply, divide). The application is containerized using Docker and includes:3. [Windows WSL2 Setup](#windows-wsl2-setup)



- **FastAPI Web Application** - REST API with interactive UI4. [Docker Desktop Installation](#docker-desktop-installation)```bash

- **PostgreSQL Database** - For data persistence

- **pgAdmin** - Database management tool5. [Project Setup](#project-setup)/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"



---6. [Running the Application](#running-the-application)```



## 🔧 Prerequisites7. [Testing the Application](#testing-the-application)



### Required Software (Windows)8. [Project Structure](#project-structure)**Verify Homebrew:**



1. **Windows 10/11** (64-bit)9. [Troubleshooting](#troubleshooting)

2. **Windows Subsystem for Linux (WSL2)**

3. **Docker Desktop for Windows**```bash

4. **Python 3.10+** (for local development)

---brew --version

---

```

## 🪟 Windows WSL2 Setup

## 📖 Project Overview

### Step 1: Enable WSL2

If you see a version number, you're good to go.

Open **PowerShell as Administrator** and run:

This is a FastAPI-based calculator application that performs basic arithmetic operations (add, subtract, multiply, divide). The application is containerized using Docker and includes:

```powershell

wsl --install---

```

- **FastAPI Web Application** - REST API with interactive UI

This installs Ubuntu by default. Restart your computer when prompted.

- **PostgreSQL Database** - For data persistence# 🧩 2. Install and Configure Git

### Step 2: Set Up Ubuntu

- **pgAdmin** - Database management tool

After restart, Ubuntu will open automatically:

## Install Git

1. Create a username (e.g., `vuttunoori_bhavanawsl`)

2. Create a password---

3. Update the system:

- **MacOS (using Homebrew)**

```bash

sudo apt update && sudo apt upgrade -y## 🔧 Prerequisites

```

```bash

### Step 3: Install Essential Tools

### Required Software (Windows)brew install git

```bash

# Install pip and Python development tools```

sudo apt install -y python3-pip python3-dev python3-venv

1. **Windows 10/11** (64-bit)

# Verify installation

python3 --version2. **Windows Subsystem for Linux (WSL2)**- **Windows**

pip3 --version

```3. **Docker Desktop for Windows**



---4. **Python 3.10+** (for local development)Download and install [Git for Windows](https://git-scm.com/download/win).  



## 🐳 Docker Desktop Installation5. **Git** (optional, for version control)Accept the default options during installation.



### Step 1: Download Docker Desktop



1. Go to [Docker Desktop for Windows](https://www.docker.com/products/docker-desktop/)---**Verify Git:**

2. Download and run the installer

3. Follow the installation wizard (accept all defaults)



### Step 2: Configure Docker for WSL2## 🪟 Windows WSL2 Setup```bash



1. Open **Docker Desktop**git --version

2. Go to **Settings** → **General**

3. Ensure "Use the WSL 2 based engine" is checked### Step 1: Enable WSL2```

4. Go to **Settings** → **Resources** → **WSL Integration**

5. Enable integration with your Ubuntu distro

6. Click **Apply & Restart**

Open **PowerShell as Administrator** and run:---

### Step 3: Verify Docker Installation



Open Ubuntu (WSL2) terminal and run:

```powershell## Configure Git Globals

```bash

docker --versionwsl --install

docker compose version

``````Set your name and email so Git tracks your commits properly:



You should see version information for both commands.



---This installs Ubuntu by default. Restart your computer when prompted.```bash



## 🚀 Project Setup from Scratchgit config --global user.name "Your Name"



### Step 1: Create Project Directory### Step 2: Set Up Ubuntugit config --global user.email "your_email@example.com"



```bash```

# Create project directory

mkdir -p ~/projects/assignment9After restart, Ubuntu will open automatically:

cd ~/projects/assignment9

```Confirm the settings:



### Step 2: Create Directory Structure1. Create a username (e.g., `bhavana`)



Create the complete directory structure for the project:2. Create a password```bash



```bash3. Update the system:git config --list

# Create all directories

mkdir -p app/operations```

mkdir -p templates

mkdir -p tests/unit tests/integration tests/e2e```bash



# Create empty __init__.py files for Python packagessudo apt update && sudo apt upgrade -y---

touch app/__init__.py

touch app/operations/__init__.py```

touch tests/__init__.py

touch tests/unit/__init__.py## Generate SSH Keys and Connect to GitHub

touch tests/integration/__init__.py

touch tests/e2e/__init__.py### Step 3: Install Essential Tools

```

> Only do this once per machine.

Your project structure should now look like:

```bash

```

assignment9/# Install pip and Python development tools1. Generate a new SSH key:

├── app/

│   ├── __init__.pysudo apt install -y python3-pip python3-dev python3-venv

│   └── operations/

│       └── __init__.py```bash

├── templates/

└── tests/# Verify installationssh-keygen -t ed25519 -C "your_email@example.com"

    ├── __init__.py

    ├── unit/python3 --version```

    │   └── __init__.py

    ├── integration/pip3 --version

    │   └── __init__.py

    └── e2e/```(Press Enter at all prompts.)

        └── __init__.py

```



### Step 3: Create Configuration Files---2. Start the SSH agent:



Now create all the necessary configuration and code files:



1. **requirements.txt** - Python dependencies## 🐳 Docker Desktop Installation```bash

2. **Dockerfile** - Container configuration

3. **docker-compose.yml** - Multi-container orchestrationeval "$(ssh-agent -s)"

4. **pytest.ini** - Test configuration

5. **LICENSE** - MIT License with your name### Step 1: Download Docker Desktop```

6. **main.py** - FastAPI application

7. **app/operations/__init__.py** - Calculator operations

8. **templates/index.html** - Web interface

9. Test files in the tests/ directory1. Go to [Docker Desktop for Windows](https://www.docker.com/products/docker-desktop/)3. Add the SSH private key to the agent:



### Step 4: Configure Your Credentials2. Download and run the installer



**In docker-compose.yml**, use your personalized credentials:3. Follow the installation wizard (accept all defaults)```bash



```yamlssh-add ~/.ssh/id_ed25519

environment:

  POSTGRES_USER: bhavana_user### Step 2: Configure Docker for WSL2```

  POSTGRES_PASSWORD: bhavana_secure_pass

  POSTGRES_DB: calculator_db

  

  PGADMIN_DEFAULT_EMAIL: bhavana.vuttunoori@admin.local1. Open **Docker Desktop**4. Copy your SSH public key:

  PGADMIN_DEFAULT_PASSWORD: bhavana_admin_2025

```2. Go to **Settings** → **General**



**In LICENSE**, update with:3. Ensure "Use the WSL 2 based engine" is checked- **Mac/Linux:**

- Your name: `Bhavana Vuttunoori`

- Current year: `2025`4. Go to **Settings** → **Resources** → **WSL Integration**



### Step 5: Create Python Virtual Environment (For Local Development)5. Enable integration with your Ubuntu distro```bash



```bash6. Click **Apply & Restart**cat ~/.ssh/id_ed25519.pub | pbcopy

# Create virtual environment

python3 -m venv venv```



# Activate virtual environment### Step 3: Verify Docker Installation

source venv/bin/activate

- **Windows (Git Bash):**

# Install dependencies

pip install -r requirements.txtOpen Ubuntu (WSL2) terminal and run:

```

```bash

---

```bashcat ~/.ssh/id_ed25519.pub | clip

## 🏃 Running the Application

docker --version```

### Method 1: Using Docker (Recommended)

docker compose version

This method runs the complete stack with database and pgAdmin.

```5. Add the key to your GitHub account:

```bash

# Navigate to project directory   - Go to [GitHub SSH Settings](https://github.com/settings/keys)

cd ~/projects/assignment9

You should see version information for both commands.   - Click **New SSH Key**, paste the key, save.

# Build and start all containers

docker compose up --build -d

```

---6. Test the connection:

**What this does:**

- Builds the FastAPI application Docker image from scratch

- Starts PostgreSQL database container

- Starts pgAdmin container## 🚀 Project Setup```bash

- Starts the web application container

- All containers run in the background (`-d` flag)ssh -T git@github.com



**Access the application:**### Step 1: Create Project Directory```

- **Calculator App:** http://localhost:8000

- **API Documentation:** http://localhost:8000/docs

- **Interactive API:** http://localhost:8000/redoc

- **pgAdmin:** http://localhost:5050```bashYou should see a success message.



### Method 2: Using Python Virtual Environment (Local Development)# Create project directory



This method runs only the FastAPI application without Docker.mkdir -p ~/projects/assignment9---



```bashcd ~/projects/assignment9

# Navigate to project directory

cd ~/projects/assignment9```# 🧩 3. Clone the Repository



# Activate virtual environment

source venv/bin/activate

### Step 2: Create Project FilesNow you can safely clone the course project:

# Run the application

python main.py

```

Create all necessary files with the following structure:```bash

**Access the application:**

- **Calculator App:** http://127.0.0.1:8000git clone <repository-url>

- **API Documentation:** http://127.0.0.1:8000/docs

```cd <repository-directory>

---

assignment9/```

## 🧪 Testing the Application

├── docker-compose.yml

### Using the Web Interface

├── Dockerfile---

1. Open http://localhost:8000 in your browser

2. Enter two numbers in the input fields├── LICENSE

3. Click any operation button (Add, Subtract, Multiply, Divide)

4. View the result displayed below the buttons├── main.py# 🛠️ 4. Install Python 3.10+



### Using the API Documentation (Swagger UI)├── pytest.ini



1. Open http://localhost:8000/docs├── README.md## Install Python

2. Expand any endpoint (e.g., `/add`)

3. Click **Try it out**├── requirements.txt

4. Enter test values:

   ```json├── app/- **MacOS (Homebrew)**

   {

     "a": 10,│   └── operations/

     "b": 5

   }│       └── __init__.py```bash

   ```

5. Click **Execute**├── templates/brew install python

6. View the response

│   └── index.html```

### Running Unit Tests

└── tests/

```bash

# Activate virtual environment    ├── __init__.py- **Windows**

source venv/bin/activate

    ├── conftest.py

# Run all tests

pytest    ├── e2e/Download and install [Python for Windows](https://www.python.org/downloads/).  



# Run with coverage report    │   ├── __init__.py✅ Make sure you **check the box** `Add Python to PATH` during setup.

pytest --cov=app --cov-report=term-missing

    │   └── test_e2e.py

# Run specific test category

pytest -m unit        # Unit tests only    ├── integration/**Verify Python:**

pytest -m integration # Integration tests only

pytest -m e2e         # End-to-end tests only    │   ├── __init__.py

```

    │   └── test_fastapi_calculator.py```bash

---

    └── unit/python3 --version

## 📁 Project Structure

        ├── __init__.py```

```

assignment9/        └── test_calculator.pyor

│

├── main.py                    # FastAPI application entry point``````bash

├── requirements.txt           # Python dependencies

├── Dockerfile                 # Docker image configurationpython --version

├── docker-compose.yml         # Multi-container orchestration

├── pytest.ini                 # Pytest configuration### Step 3: Configure Credentials```

├── LICENSE                    # MIT License (Bhavana Vuttunoori, 2025)

├── README.md                  # This file

│

├── app/**Update docker-compose.yml** with your credentials:---

│   ├── __init__.py

│   └── operations/

│       └── __init__.py        # Arithmetic operations (add, subtract, multiply, divide)

│```yaml## Create and Activate a Virtual Environment

├── templates/

│   └── index.html             # Web UI for calculatorenvironment:

│

├── tests/  POSTGRES_USER: bhavana_user(Optional but recommended)

│   ├── __init__.py

│   ├── conftest.py            # Pytest fixtures  POSTGRES_PASSWORD: bhavana_secure_pass

│   ├── unit/

│   │   ├── __init__.py  POSTGRES_DB: calculator_db```bash

│   │   └── test_calculator.py # Unit tests for operations

│   ├── integration/  python3 -m venv venv

│   │   ├── __init__.py

│   │   └── test_fastapi_calculator.py  # API integration tests  PGADMIN_DEFAULT_EMAIL: bhavana.vuttunoori@admin.localsource venv/bin/activate   # Mac/Linux

│   └── e2e/

│       ├── __init__.py  PGADMIN_DEFAULT_PASSWORD: bhavana_admin_2025venv\Scripts\activate.bat  # Windows

│       └── test_e2e.py        # End-to-end browser tests

│``````

└── venv/                      # Python virtual environment (not in Docker)

```



---**Update LICENSE** with your name and current year (2025).### Install Required Packages



## 🐛 Troubleshooting



### Docker Issues### Step 4: Create Python Virtual Environment (Optional - for local development)```bash



**Problem:** `docker: command not found`pip install -r requirements.txt



**Solution:**```bash```

1. Ensure Docker Desktop is running

2. Open Docker Desktop settings# Create virtual environment

3. Enable WSL2 integration for Ubuntu

4. Restart WSL2: `wsl --shutdown` (in PowerShell), then reopen Ubuntupython3 -m venv venv---



---



**Problem:** `Conflict. The container name is already in use`# Activate virtual environment# 🐳 5. (Optional) Docker Setup



**Solution:**source venv/bin/activate

```bash

# Stop and remove all containers> Skip if Docker isn't used in this module.

docker compose down

# Install dependencies

# Remove specific container

docker rm -f <container_name>pip install -r requirements.txt## Install Docker



# Restart```

docker compose up -d

```- [Install Docker Desktop for Mac](https://www.docker.com/products/docker-desktop/)



------- [Install Docker Desktop for Windows](https://www.docker.com/products/docker-desktop/)



**Problem:** PostgreSQL container fails to start



**Solution:**## 🏃 Running the Application## Build Docker Image

```bash

# Remove old volumes and restart

docker compose down -v

docker compose up -d### Method 1: Using Docker (Recommended)```bash

```

docker build -t <image-name> .

---

This method runs the complete stack with database and pgAdmin.```

**Problem:** Volume path error in PostgreSQL



**Solution:**

Ensure your `docker-compose.yml` uses the correct volume path:```bash## Run Docker Container

```yaml

volumes:# Navigate to project directory

  - postgres_data:/var/lib/postgresql  # NOT /var/lib/postgresql/data

```cd ~/projects/assignment9```bash



---docker run -it --rm <image-name>



### Python/Pip Issues# Build and start all containers```



**Problem:** `externally-managed-environment` errordocker compose up --build -d



**Solution:**```---

Always use a virtual environment:

```bash

python3 -m venv venv

source venv/bin/activate**What this does:**# 🚀 6. Running the Project

pip install -r requirements.txt

```- Builds the FastAPI application Docker image



---- Starts PostgreSQL database container- **Without Docker**:



**Problem:** `ModuleNotFoundError: No module named 'fastapi'`- Starts pgAdmin container



**Solution:**- Starts the web application container```bash

```bash

# Ensure virtual environment is activated- All containers run in the background (`-d` flag)python main.py

source venv/bin/activate

```

# Install dependencies

pip install -r requirements.txt**Access the application:**

```

- **Calculator App:** http://localhost:8000(or update this if the main script is different.)

---

- **API Documentation:** http://localhost:8000/docs

### Port Conflicts

- **pgAdmin:** http://localhost:5050- **With Docker**:

**Problem:** Port 8000, 5432, or 5050 already in use



**Solution:**

```bash### Method 2: Using Python Virtual Environment (Local Development)```bash

# Stop running containers

docker compose downdocker run -it --rm <image-name>



# If running locally, stop the Python processThis method runs only the FastAPI application without Docker.```

# Press Ctrl+C in the terminal where it's running



# Check what's using the port (Linux)

sudo lsof -i :8000```bash---

sudo lsof -i :5432

sudo lsof -i :5050# Navigate to project directory



# Kill the process if neededcd ~/projects/assignment9# 📝 7. Submission Instructions

sudo kill -9 <PID>

```



---# Activate virtual environmentAfter finishing your work:



## 🔑 Application Credentialssource venv/bin/activate



### PostgreSQL Database```bash

- **Host:** `localhost` (or `db` inside Docker network)

- **Port:** `5432`# Run the applicationgit add .

- **Username:** `bhavana_user`

- **Password:** `bhavana_secure_pass`python main.pygit commit -m "Complete Module X"

- **Database:** `calculator_db`

```git push origin main

### pgAdmin

- **URL:** http://localhost:5050```

- **Email:** `bhavana.vuttunoori@admin.local`

- **Password:** `bhavana_admin_2025`**Access the application:**



**To connect pgAdmin to PostgreSQL:**- **Calculator App:** http://127.0.0.1:8000Then submit the GitHub repository link as instructed.

1. Login to pgAdmin with the credentials above

2. Right-click "Servers" → "Register" → "Server"- **API Documentation:** http://127.0.0.1:8000/docs

3. Name: `Calculator DB`

4. Connection tab:---

   - Host: `db` (Docker network name)

   - Port: `5432`---

   - Username: `bhavana_user`

   - Password: `bhavana_secure_pass`# 🔥 Useful Commands Cheat Sheet



---## 🧪 Testing the Application



## 📊 Docker Commands Cheat Sheet| Action                         | Command                                          |



```bash### Using the Web Interface| ------------------------------- | ------------------------------------------------ |

# Start all containers in background

docker compose up -d| Install Homebrew (Mac)          | `/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"` |



# Start with rebuild (after code changes)1. Open http://localhost:8000 in your browser| Install Git                     | `brew install git` or Git for Windows installer |

docker compose up --build -d

2. Enter two numbers in the input fields| Configure Git Global Username  | `git config --global user.name "Your Name"`      |

# Stop all containers

docker compose down3. Click any operation button (Add, Subtract, Multiply, Divide)| Configure Git Global Email     | `git config --global user.email "you@example.com"` |



# Stop and remove volumes (fresh start)4. View the result displayed below the buttons| Clone Repository                | `git clone <repo-url>`                          |

docker compose down -v

| Create Virtual Environment     | `python3 -m venv venv`                           |

# View running containers

docker ps### Using the API Documentation| Activate Virtual Environment   | `source venv/bin/activate` / `venv\Scripts\activate.bat` |



# View all containers (including stopped)| Install Python Packages        | `pip install -r requirements.txt`               |

docker ps -a

1. Open http://localhost:8000/docs| Build Docker Image              | `docker build -t <image-name> .`                |

# View logs for all services

docker compose logs2. Expand any endpoint (e.g., `/add`)| Run Docker Container            | `docker run -it --rm <image-name>`               |



# View logs for specific service3. Click **Try it out**| Push Code to GitHub             | `git add . && git commit -m "message" && git push` |

docker logs fastapi_calculator

docker logs postgres_db4. Enter test values:

docker logs pgadmin

   ```json---

# Follow logs in real-time

docker logs -f fastapi_calculator   {



# Access container shell     "a": 10,# 📋 Notes

docker exec -it fastapi_calculator bash

docker exec -it postgres_db bash     "b": 5



# Remove all stopped containers   }- Install **Homebrew** first on Mac.

docker container prune

   ```- Install and configure **Git** and **SSH** before cloning.

# Remove all unused images

docker image prune -a5. Click **Execute**- Use **Python 3.10+** and **virtual environments** for Python projects.



# View Docker disk usage6. View the response- **Docker** is optional depending on the project.

docker system df

```



---### Running Unit Tests---



## 🎯 Quick Start Summary



```bash```bash# 📎 Quick Links

# 1. Navigate to project

cd ~/projects/assignment9# Activate virtual environment



# 2. Start all services with Dockersource venv/bin/activate- [Homebrew](https://brew.sh/)

docker compose up -d

- [Git Downloads](https://git-scm.com/downloads)

# 3. Open browser and test

# Visit: http://localhost:8000# Run all tests- [Python Downloads](https://www.python.org/downloads/)



# 4. View API documentationpytest- [Docker Desktop](https://www.docker.com/products/docker-desktop/)

# Visit: http://localhost:8000/docs

- [GitHub SSH Setup Guide](https://docs.github.com/en/authentication/connecting-to-github-with-ssh)

# 5. Stop all services when done

docker compose down# Run with coverage report

```pytest --cov=app --cov-report=term-missing



---# Run specific test category

pytest -m unit        # Unit tests only

## 📊 Development Workflowpytest -m integration # Integration tests only

pytest -m e2e         # End-to-end tests only

### Making Code Changes```



```bash---

# 1. Stop running containers

docker compose down## 📁 Project Structure



# 2. Make your code changes in the project files```

assignment9/

# 3. Rebuild and restart│

docker compose up --build -d├── main.py                    # FastAPI application entry point

├── requirements.txt           # Python dependencies

# 4. View logs to check for errors├── Dockerfile                 # Docker image configuration

docker compose logs -f├── docker-compose.yml         # Multi-container orchestration

```├── pytest.ini                 # Pytest configuration

├── LICENSE                    # MIT License

### Running Tests During Development├── README.md                  # This file

│

```bash├── app/

# Activate virtual environment│   └── operations/

source venv/bin/activate│       └── __init__.py        # Arithmetic operations (add, subtract, etc.)

│

# Run tests├── templates/

pytest│   └── index.html             # Web UI for calculator

│

# Run with coverage└── tests/

pytest --cov=app --cov-report=html    ├── conftest.py            # Pytest fixtures

    ├── unit/

# Open coverage report in browser    │   └── test_calculator.py # Unit tests for operations

# File: htmlcov/index.html    ├── integration/

```    │   └── test_fastapi_calculator.py  # API integration tests

    └── e2e/

---        └── test_e2e.py        # End-to-end browser tests

```

## 📞 Support & Resources

---

### Documentation

- [FastAPI Documentation](https://fastapi.tiangolo.com/)## 🐛 Troubleshooting

- [Docker Documentation](https://docs.docker.com/)

- [PostgreSQL Documentation](https://www.postgresql.org/docs/)### Docker Issues

- [pytest Documentation](https://docs.pytest.org/)

**Problem:** `docker: command not found`

### Project Information

- **Built From Scratch:** November 20, 2025**Solution:**

- **Platform:** Windows 11 with WSL2 (Ubuntu)1. Ensure Docker Desktop is running

- **Python Version:** 3.122. Open Docker Desktop settings

- **Docker Version:** 28.5.13. Enable WSL2 integration for Ubuntu

- **Docker Compose Version:** 2.40.34. Restart WSL2: `wsl --shutdown` (in PowerShell), then reopen Ubuntu



------



## 📝 Notes**Problem:** `Conflict. The container name is already in use`



- This project was built entirely from scratch on Windows using WSL2**Solution:**

- All credentials have been personalized for Bhavana Vuttunoori```bash

- The application runs in Docker containers for consistency and portability# Stop and remove all containers

- Virtual environment is available for local development without Dockerdocker compose down

- Database configuration is included but not actively used by the calculator (for future expansion)

# Remove specific container

---docker rm -f <container_name>



**License:** MIT License  # Restart

**Copyright:** 2025 Bhavana Vuttunoori  docker compose up -d

**Built With:** FastAPI, Docker, PostgreSQL, Python 3.12```


---

**Problem:** PostgreSQL container fails to start

**Solution:**
```bash
# Remove old volumes and restart
docker compose down -v
docker compose up -d
```

---

### Python/Pip Issues

**Problem:** `externally-managed-environment` error

**Solution:**
Always use a virtual environment:
```bash
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

---

**Problem:** `ModuleNotFoundError: No module named 'fastapi'`

**Solution:**
```bash
# Ensure virtual environment is activated
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt
```

---

### Port Conflicts

**Problem:** Port 8000 or 5432 already in use

**Solution:**
```bash
# Stop running containers
docker compose down

# If running locally, stop the Python process
# Press Ctrl+C in the terminal where it's running

# Check what's using the port (Linux)
sudo lsof -i :8000
sudo lsof -i :5432
```

---

## 🔑 Application Credentials

### PostgreSQL Database
- **Username:** `bhavana_user`
- **Password:** `bhavana_secure_pass`
- **Database:** `calculator_db`
- **Port:** `5432`

### pgAdmin
- **URL:** http://localhost:5050
- **Email:** `bhavana.vuttunoori@admin.local`
- **Password:** `bhavana_admin_2025`

---

## 📊 Docker Commands Cheat Sheet

```bash
# Start all containers
docker compose up -d

# Start with rebuild
docker compose up --build -d

# Stop all containers
docker compose down

# Stop and remove volumes
docker compose down -v

# View running containers
docker ps

# View logs
docker logs <container_name>
docker compose logs

# Follow logs in real-time
docker logs -f <container_name>

# Access container shell
docker exec -it <container_name> bash

# Remove all stopped containers
docker container prune
```

---

## 🎯 Quick Start Summary

```bash
# 1. Navigate to project
cd ~/projects/assignment9

# 2. Start with Docker
docker compose up -d

# 3. Open browser
# Visit: http://localhost:8000

# 4. Stop when done
docker compose down
```

---

## 📞 Support

For issues or questions, refer to:
- [FastAPI Documentation](https://fastapi.tiangolo.com/)
- [Docker Documentation](https://docs.docker.com/)
- [PostgreSQL Documentation](https://www.postgresql.org/docs/)

---

**License:** MIT License  
**Copyright:** 2025 Bhavana Vuttunoori
