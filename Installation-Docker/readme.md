
# Installation Guide for Harbor with Docker

## Table of Contents
1. [Introduction](#introduction)
2. [Prerequisites](#prerequisites)
3. [Installation Steps](#installation-steps)
4. [Testing the Installation](#testing-the-installation)
5. [Troubleshooting](#troubleshooting)
6. [Useful Commands](#useful-commands)
7. [Additional Resources](#additional-resources)

## Introduction
Harbor is an open-source cloud-native registry that stores, signs, and scans container images for vulnerabilities. This guide walks you through the process of installing Harbor using Docker.

## Prerequisites
Before proceeding with the installation, ensure you have the following prerequisites:

- A machine running Linux or Windows (with WSL2).
- **Docker** version 19.03 or higher.
- **Docker Compose** version 1.18 or higher.
- Root or sudo access to the machine.

## Installation Steps

Make sure Docker is installed on your system. You can verify this by running:

```bash
docker --version
```

If Docker is not installed, refer to the official [Docker installation guide](https://docs.docker.com/engine/install/) for your operating system.

Check if Docker Compose is installed:

```bash
docker-compose --version
```

If not installed, follow the official [Docker Compose installation guide](https://docs.docker.com/compose/install/).

Download the latest version of Harbor from the official GitHub repository:

```bash
git clone https://github.com/goharbor/harbor.git
cd harbor
```

Inside the `harbor` directory, you’ll find a script that simplifies the installation process. Make the script executable:

```bash
chmod +x install.sh
```

Run the script to begin the installation:

```bash
./install.sh
```

Before running Harbor, configure the `harbor.yml` file. You can use the default settings, but it's recommended to set a password for the admin user:

```yaml
hostname: your.harbor.domain
harbor_admin_password: YourSecurePassword
```

Once configured, use Docker Compose to bring up the Harbor containers:

```bash
docker-compose up -d
```

Harbor will start as a set of Docker containers. You can check the running containers using:

```bash
docker ps
```

## Testing the Installation
Once Harbor is running, open a browser and visit the Harbor interface at:

```
http://your.harbor.domain
```

Log in using the default credentials:
- **Username**: `admin`
- **Password**: (The one set in the `harbor.yml` configuration file).

You should see the Harbor dashboard.

## Troubleshooting
If you encounter issues during installation or when running Harbor, check the following:

- Ensure all containers are running using `docker ps`.
- Check the Docker logs for errors: 

```bash
docker-compose logs
```

- Ensure that ports `80`, `443`, and `4443` are open and not blocked by a firewall.

## Useful Commands
- **Stop Harbor**:

  ```bash
  docker-compose down
  ```

- **Restart Harbor**:

  ```bash
  docker-compose restart
  ```

- **View logs**:

  ```bash
  docker-compose logs -f
  ```

## Additional Resources
- [Harbor Documentation](https://goharbor.io/docs/)
- [Docker Documentation](https://docs.docker.com/)
- [Docker Compose Documentation](https://docs.docker.com/compose/)
