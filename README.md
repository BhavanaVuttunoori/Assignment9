# FastAPI Calculator Application - Complete Setup Guide#  Project Setup



**Author:** Bhavana Vuttunoori  ---

**Date:** November 20, 2025  

**Project:** Assignment 9 - FastAPI Calculator with Docker#  1. Install Homebrew (Mac Only)



---> Skip this step if you're on Windows.



## Table of ContentsHomebrew is a package manager for macOS.  

You’ll use it to easily install Git, Python, Docker, etc.

1. [Project Overview](#project-overview)

2. [Prerequisites](#prerequisites)**Install Homebrew:**

3. [Windows WSL2 Setup](#windows-wsl2-setup)

4. [Docker Desktop Installation](#docker-desktop-installation)```bash

5. [Project Setup from Scratch](#project-setup-from-scratch)/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

6. [Running the Application](#running-the-application)```

7. [Testing the Application](#testing-the-application)

8. [Project Structure](#project-structure)**Verify Homebrew:**

9. [Troubleshooting](#troubleshooting)

```bash

---brew --version

```

## Project Overview

If you see a version number, you're good to go.

This is a FastAPI-based calculator application built from scratch that performs basic arithmetic operations (add, subtract, multiply, divide). The application is containerized using Docker and includes:

---

- **FastAPI Web Application** - REST API with interactive UI

- **PostgreSQL Database** - For data persistence#  2. Install and Configure Git

- **pgAdmin** - Database management tool

## Install Git

---

- **MacOS (using Homebrew)**

## Prerequisites

```bash

### Required Software (Windows)brew install git

```

1. **Windows 10/11** (64-bit)

2. **Windows Subsystem for Linux (WSL2)**- **Windows**

3. **Docker Desktop for Windows**

4. **Python 3.10+** (for local development)Download and install [Git for Windows](https://git-scm.com/download/win).  

Accept the default options during installation.

---

**Verify Git:**

## Windows WSL2 Setup

```bash

### Step 1: Enable WSL2git --version

```

Open **PowerShell as Administrator** and run:

---

```powershell

wsl --install## Configure Git Globals

```

Set your name and email so Git tracks your commits properly:

This installs Ubuntu by default. Restart your computer when prompted.

```bash

### Step 2: Set Up Ubuntugit config --global user.name "Your Name"

git config --global user.email "your_email@example.com"

After restart, Ubuntu will open automatically:```



1. Create a username (e.g., `vuttunoori_bhavanawsl`)Confirm the settings:

2. Create a password

3. Update the system:```bash

git config --list

```bash```

sudo apt update && sudo apt upgrade -y

```---



### Step 3: Install Essential Tools## Generate SSH Keys and Connect to GitHub



```bash> Only do this once per machine.

# Install pip and Python development tools

sudo apt install -y python3-pip python3-dev python3-venv1. Generate a new SSH key:



# Verify installation```bash

python3 --versionssh-keygen -t ed25519 -C "your_email@example.com"

pip3 --version```

```

(Press Enter at all prompts.)

---

2. Start the SSH agent:

## Docker Desktop Installation

```bash

### Step 1: Download Docker Desktopeval "$(ssh-agent -s)"

```

1. Go to [Docker Desktop for Windows](https://www.docker.com/products/docker-desktop/)

2. Download and run the installer3. Add the SSH private key to the agent:

3. Follow the installation wizard (accept all defaults)

```bash

### Step 2: Configure Docker for WSL2ssh-add ~/.ssh/id_ed25519

```

1. Open **Docker Desktop**

2. Go to **Settings** → **General**4. Copy your SSH public key:

3. Ensure "Use the WSL 2 based engine" is checked

4. Go to **Settings** → **Resources** → **WSL Integration**- **Mac/Linux:**

5. Enable integration with your Ubuntu distro

6. Click **Apply & Restart**```bash

cat ~/.ssh/id_ed25519.pub | pbcopy

### Step 3: Verify Docker Installation```



Open Ubuntu (WSL2) terminal and run:- **Windows (Git Bash):**



```bash```bash

docker --versioncat ~/.ssh/id_ed25519.pub | clip

docker compose version```

```

5. Add the key to your GitHub account:

You should see version information for both commands.   - Go to [GitHub SSH Settings](https://github.com/settings/keys)

   - Click **New SSH Key**, paste the key, save.

---

6. Test the connection:

## Project Setup from Scratch

```bash

### Step 1: Create Project Directoryssh -T git@github.com

```

```bash

# Create project directoryYou should see a success message.

mkdir -p ~/projects/assignment9

cd ~/projects/assignment9---

```

#  3. Clone the Repository

### Step 2: Create Directory Structure

Now you can safely clone the course project:

Create the complete directory structure for the project:

```bash

```bashgit clone <repository-url>

# Create all directoriescd <repository-directory>

mkdir -p app/operations```

mkdir -p templates

mkdir -p tests/unit tests/integration tests/e2e---



# Create empty __init__.py files for Python packages#  4. Install Python 3.10+

touch app/__init__.py

touch app/operations/__init__.py## Install Python

touch tests/__init__.py

touch tests/unit/__init__.py- **MacOS (Homebrew)**

touch tests/integration/__init__.py

touch tests/e2e/__init__.py```bash

```brew install python

```

Your project structure should now look like:

- **Windows**

```

assignment9/Download and install [Python for Windows](https://www.python.org/downloads/).  

├── app/ Make sure you **check the box** `Add Python to PATH` during setup.

│   ├── __init__.py

│   └── operations/**Verify Python:**

│       └── __init__.py

├── templates/```bash

└── tests/python3 --version

    ├── __init__.py```

    ├── unit/or

    │   └── __init__.py```bash

    ├── integration/python --version

    │   └── __init__.py```

    └── e2e/

        └── __init__.py---

```

## Create and Activate a Virtual Environment

### Step 3: Create Configuration Files

(Optional but recommended)

Now create all the necessary configuration and code files:

```bash

1. **requirements.txt** - Python dependenciespython3 -m venv venv

2. **Dockerfile** - Container configurationsource venv/bin/activate   # Mac/Linux

3. **docker-compose.yml** - Multi-container orchestrationvenv\Scripts\activate.bat  # Windows

4. **pytest.ini** - Test configuration```

5. **LICENSE** - MIT License with your name

6. **main.py** - FastAPI application### Install Required Packages

7. **app/operations/__init__.py** - Calculator operations

8. **templates/index.html** - Web interface```bash

9. Test files in the tests/ directorypip install -r requirements.txt

```

### Step 4: Configure Your Credentials

---

**In docker-compose.yml**, use your personalized credentials:

#  5. (Optional) Docker Setup

```yaml

environment:> Skip if Docker isn't used in this module.

  POSTGRES_USER: bhavana_user

  POSTGRES_PASSWORD: bhavana_secure_pass## Install Docker

  POSTGRES_DB: calculator_db

  - [Install Docker Desktop for Mac](https://www.docker.com/products/docker-desktop/)

  PGADMIN_DEFAULT_EMAIL: bhavana.vuttunoori@admin.local- [Install Docker Desktop for Windows](https://www.docker.com/products/docker-desktop/)

  PGADMIN_DEFAULT_PASSWORD: bhavana_admin_2025

```## Build Docker Image



**In LICENSE**, update with:```bash

- Your name: `Bhavana Vuttunoori`docker build -t <image-name> .

- Current year: `2025````



### Step 5: Create Python Virtual Environment (For Local Development)## Run Docker Container



```bash```bash

# Create virtual environmentdocker run -it --rm <image-name>

python3 -m venv venv```



# Activate virtual environment---

source venv/bin/activate

#  6. Running the Project

# Install dependencies

pip install -r requirements.txt- **Without Docker**:

```

```bash

---python main.py

```

## Running the Application

(or update this if the main script is different.)

### Method 1: Using Docker (Recommended)

- **With Docker**:

This method runs the complete stack with database and pgAdmin.

```bash

```bashdocker run -it --rm <image-name>

# Navigate to project directory```

cd ~/projects/assignment9

---

# Build and start all containers

docker compose up --build -d#  7. Submission Instructions

```

After finishing your work:

**What this does:**

- Builds the FastAPI application Docker image from scratch```bash

- Starts PostgreSQL database containergit add .

- Starts pgAdmin containergit commit -m "Complete Module X"

- Starts the web application containergit push origin main

- All containers run in the background (`-d` flag)```



**Access the application:**Then submit the GitHub repository link as instructed.

- **Calculator App:** http://localhost:8000

- **API Documentation:** http://localhost:8000/docs---

- **Interactive API:** http://localhost:8000/redoc

- **pgAdmin:** http://localhost:5050#  Useful Commands Cheat Sheet



### Method 2: Using Python Virtual Environment (Local Development)| Action                         | Command                                          |

| ------------------------------- | ------------------------------------------------ |

This method runs only the FastAPI application without Docker.| Install Homebrew (Mac)          | `/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"` |

| Install Git                     | `brew install git` or Git for Windows installer |

```bash| Configure Git Global Username  | `git config --global user.name "Your Name"`      |

# Navigate to project directory| Configure Git Global Email     | `git config --global user.email "you@example.com"` |

cd ~/projects/assignment9| Clone Repository                | `git clone <repo-url>`                          |

| Create Virtual Environment     | `python3 -m venv venv`                           |

# Activate virtual environment| Activate Virtual Environment   | `source venv/bin/activate` / `venv\Scripts\activate.bat` |

source venv/bin/activate| Install Python Packages        | `pip install -r requirements.txt`               |

| Build Docker Image              | `docker build -t <image-name> .`                |

# Run the application| Run Docker Container            | `docker run -it --rm <image-name>`               |

python main.py| Push Code to GitHub             | `git add . && git commit -m "message" && git push` |

```

---

**Access the application:**

- **Calculator App:** http://127.0.0.1:8000#  Notes

- **API Documentation:** http://127.0.0.1:8000/docs

- Install **Homebrew** first on Mac.

---- Install and configure **Git** and **SSH** before cloning.

- Use **Python 3.10+** and **virtual environments** for Python projects.

## Testing the Application- **Docker** is optional depending on the project.



### Using the Web Interface---



1. Open http://localhost:8000 in your browser#  Quick Links

2. Enter two numbers in the input fields

3. Click any operation button (Add, Subtract, Multiply, Divide)- [Homebrew](https://brew.sh/)

4. View the result displayed below the buttons- [Git Downloads](https://git-scm.com/downloads)

- [Python Downloads](https://www.python.org/downloads/)

### Using the API Documentation (Swagger UI)- [Docker Desktop](https://www.docker.com/products/docker-desktop/)

- [GitHub SSH Setup Guide](https://docs.github.com/en/authentication/connecting-to-github-with-ssh)

1. Open http://localhost:8000/docs
2. Expand any endpoint (e.g., `/add`)
3. Click **Try it out**
4. Enter test values:
   ```json
   {
     "a": 10,
     "b": 5
   }
   ```
5. Click **Execute**
6. View the response

### Running Unit Tests

```bash
# Activate virtual environment
source venv/bin/activate

# Run all tests
pytest

# Run with coverage report
pytest --cov=app --cov-report=term-missing

# Run specific test category
pytest -m unit        # Unit tests only
pytest -m integration # Integration tests only
pytest -m e2e         # End-to-end tests only
```

---

## Project Structure

```
assignment9/
│
├── main.py                    # FastAPI application entry point
├── requirements.txt           # Python dependencies
├── Dockerfile                 # Docker image configuration
├── docker-compose.yml         # Multi-container orchestration
├── pytest.ini                 # Pytest configuration
├── LICENSE                    # MIT License (Bhavana Vuttunoori, 2025)
├── README.md                  # This file
│
├── app/
│   ├── __init__.py
│   └── operations/
│       └── __init__.py        # Arithmetic operations (add, subtract, multiply, divide)
│
├── templates/
│   └── index.html             # Web UI for calculator
│
├── tests/
│   ├── __init__.py
│   ├── conftest.py            # Pytest fixtures
│   ├── unit/
│   │   ├── __init__.py
│   │   └── test_calculator.py # Unit tests for operations
│   ├── integration/
│   │   ├── __init__.py
│   │   └── test_fastapi_calculator.py  # API integration tests
│   └── e2e/
│       ├── __init__.py
│       └── test_e2e.py        # End-to-end browser tests
│
└── venv/                      # Python virtual environment (not in Docker)
```

---

## Troubleshooting

### Docker Issues

**Problem:** `docker: command not found`

**Solution:**
1. Ensure Docker Desktop is running
2. Open Docker Desktop settings
3. Enable WSL2 integration for Ubuntu
4. Restart WSL2: `wsl --shutdown` (in PowerShell), then reopen Ubuntu

---

**Problem:** `Conflict. The container name is already in use`

**Solution:**
```bash
# Stop and remove all containers
docker compose down

# Remove specific container
docker rm -f <container_name>

# Restart
docker compose up -d
```

---

**Problem:** PostgreSQL container fails to start

**Solution:**
```bash
# Remove old volumes and restart
docker compose down -v
docker compose up -d
```

---

**Problem:** Volume path error in PostgreSQL

**Solution:**
Ensure your `docker-compose.yml` uses the correct volume path:
```yaml
volumes:
  - postgres_data:/var/lib/postgresql  # NOT /var/lib/postgresql/data
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

**Problem:** Port 8000, 5432, or 5050 already in use

**Solution:**
```bash
# Stop running containers
docker compose down

# If running locally, stop the Python process
# Press Ctrl+C in the terminal where it's running

# Check what's using the port (Linux)
sudo lsof -i :8000
sudo lsof -i :5432
sudo lsof -i :5050

# Kill the process if needed
sudo kill -9 <PID>
```

---

## Application Credentials

### PostgreSQL Database
- **Host:** `localhost` (or `db` inside Docker network)
- **Port:** `5432`
- **Username:** `bhavana_user`
- **Password:** `bhavana_secure_pass`
- **Database:** `calculator_db`

### pgAdmin
- **URL:** http://localhost:5050
- **Email:** `bhavana.vuttunoori@admin.local`
- **Password:** `bhavana_admin_2025`

**To connect pgAdmin to PostgreSQL:**
1. Login to pgAdmin with the credentials above
2. Right-click "Servers" → "Register" → "Server"
3. Name: `Calculator DB`
4. Connection tab:
   - Host: `db` (Docker network name)
   - Port: `5432`
   - Username: `bhavana_user`
   - Password: `bhavana_secure_pass`

---

## Docker Commands Cheat Sheet

```bash
# Start all containers in background
docker compose up -d

# Start with rebuild (after code changes)
docker compose up --build -d

# Stop all containers
docker compose down

# Stop and remove volumes (fresh start)
docker compose down -v

# View running containers
docker ps

# View all containers (including stopped)
docker ps -a

# View logs for all services
docker compose logs

# View logs for specific service
docker logs fastapi_calculator
docker logs postgres_db
docker logs pgadmin

# Follow logs in real-time
docker logs -f fastapi_calculator

# Access container shell
docker exec -it fastapi_calculator bash
docker exec -it postgres_db bash

# Remove all stopped containers
docker container prune

# Remove all unused images
docker image prune -a

# View Docker disk usage
docker system df
```

---

## Quick Start Summary

```bash
# 1. Navigate to project
cd ~/projects/assignment9

# 2. Start all services with Docker
docker compose up -d

# 3. Open browser and test
# Visit: http://localhost:8000

# 4. View API documentation
# Visit: http://localhost:8000/docs

# 5. Stop all services when done
docker compose down
```

---

## Development Workflow

### Making Code Changes

```bash
# 1. Stop running containers
docker compose down

# 2. Make your code changes in the project files

# 3. Rebuild and restart
docker compose up --build -d

# 4. View logs to check for errors
docker compose logs -f
```

### Running Tests During Development

```bash
# Activate virtual environment
source venv/bin/activate

# Run tests
pytest

# Run with coverage
pytest --cov=app --cov-report=html

# Open coverage report in browser
# File: htmlcov/index.html
```

---

## Support & Resources

### Documentation
- [FastAPI Documentation](https://fastapi.tiangolo.com/)
- [Docker Documentation](https://docs.docker.com/)
- [PostgreSQL Documentation](https://www.postgresql.org/docs/)
- [pytest Documentation](https://docs.pytest.org/)

### Project Information
- **Built From Scratch:** November 20, 2025
- **Platform:** Windows 11 with WSL2 (Ubuntu)
- **Python Version:** 3.12
- **Docker Version:** 28.5.1
- **Docker Compose Version:** 2.40.3

---

## Notes

- This project was built entirely from scratch on Windows using WSL2
- All credentials have been personalized for Bhavana Vuttunoori
- The application runs in Docker containers for consistency and portability
- Virtual environment is available for local development without Docker
- Database configuration is included but not actively used by the calculator (for future expansion)

---

**License:** MIT License  
**Copyright:** 2025 Bhavana Vuttunoori  
**Built With:** FastAPI, Docker, PostgreSQL, Python 3.12
