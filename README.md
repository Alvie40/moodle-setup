# Moodle Setup

This repository contains the setup instructions and configuration files for deploying Moodle using Docker.

## Instructions

1. **Install Git and GitHub CLI**
   ```sh
   sudo apt update
   sudo apt install git gh
   ```

2. **Clone the repository**
   ```sh
   git clone https://github.com/alvie40/moodle-setup.git
   cd moodle-setup
   ```

3. **Build and run the Docker containers**
   ```sh
   docker-compose up --build -d
   ```

4. **Access Moodle**
   Open your browser and navigate to `http://<your-server-ip>`

## Configuration

- **Docker Compose File**: `docker-compose.yml`
- **Moodle Data Directory**: `./moodle_data`
- **MariaDB Data Directory**: `./mariadb_data`

## Environment Variables

- `ALLOW_EMPTY_PASSWORD=yes`
- `MARIADB_USER=bn_moodle`
- `MARIADB_DATABASE=bitnami_moodle`
- `MOODLE_DATABASE_USER=bn_moodle`
- `MOODLE_DATABASE_NAME=bitnami_moodle`

