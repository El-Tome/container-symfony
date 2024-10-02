# Symfony Docker Project

This project is a Symfony application running in a Docker environment. It includes services for Nginx, PHP, MariaDB, and phpMyAdmin.

## Prerequisites

- Docker
- Docker Compose

## Getting Started

### Clone the Repository

```sh
git clone https://github.com/El-Tome/container-symfony.git
cd container-symfony
```

### Create a `.env` File

Copy the `.env.example` file to `.env`.

### Build the Docker Containers

```sh
docker-compose up -d --build
```

## Accessing the Application
- phpMyAdmin: [http://localhost:8080](http://localhost:8080)
- Symfony App: [http://localhost:80](http://localhost:80)

##  Project Structure

- public/: Contains the Symfony application.
- nginx.conf: Nginx configuration file.
- compose.yaml: Docker Compose configuration file.

## Useful Commands

Enter in container:
```sh
docker exec -it php-symfony bash
```

Stop the containers:
```sh  
docker-compose down
```

## Other information
- symfony version: 7.1.5
- php version: 8.2
- mariadb version: 11.5

## Author
[Tom Chaumette](https://github.com/El-Tome)

