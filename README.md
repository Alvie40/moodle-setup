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

README.md
markdown
Copy code
# Moodle Setup

This repository contains the setup instructions and configuration files for deploying Moodle using Docker.

## Part I: Initial Setup

1. **Install Docker and Docker Compose**
   ```sh
   sudo apt update
   sudo apt install docker.io docker-compose
Clone the repository
sh
Copy code
git clone https://github.com/alvie40/moodle-setup.git
cd moodle-setup
Part II: Docker Configuration and Permissions
Step 1: Add User to Docker Group
To avoid needing to use sudo for every Docker command, add your user to the Docker group:

sh
Copy code
sudo usermod -aG docker $USER
Note: After running this command, you need to log out and log back in for the changes to take effect.

Step 2: Start Docker Service
Ensure that the Docker service is running:

sh
Copy code
sudo systemctl start docker
sudo systemctl enable docker
Step 3: Build and Run Docker Containers
You can now build and run the Docker containers. If you still encounter permission issues, use sudo to run the command:

sh
Copy code
sudo docker-compose up --build -d
Verify Container Logs
If you need to check the logs for the containers to ensure they are running correctly, use the following commands:

sh
Copy code
docker logs moodle_moodle_1
docker logs moodle_mariadb_1
Part III: Access Moodle
Open your browser and navigate to http://<your-server-ip>. You should see the Moodle setup page.

Configuration
Docker Compose File: docker-compose.yml
Moodle Data Directory: ./moodle_data
MariaDB Data Directory: ./mariadb_data
Environment Variables
ALLOW_EMPTY_PASSWORD=yes
MARIADB_USER=bn_moodle
MARIADB_DATABASE=bitnami_moodle
MOODLE_DATABASE_USER=bn_moodle
MOODLE_DATABASE_NAME=bitnami_moodle
Persisting Data
To ensure your data persists between container restarts, the following volumes are defined in the docker-compose.yml file:

moodle_data:/bitnami/moodle
moodledata_data:/bitnami/moodledata
mariadb_data:/bitnami/mariadb
Troubleshooting
If you encounter any issues, ensure that you have the correct permissions and that the Docker service is running. You can also check the logs for more information on any errors.
