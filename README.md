# minimal-php-v1

## Overview

A minimal PHP development environment using Docker containers. This project provides a simple setup for PHP web application development with Nginx as the web server and MySQL as the database.

## Tech Stack

- PHP 8.x (custom build)
- Nginx 1.26-alpine
- MySQL 8.4
- Docker & Docker Compose

## Setup

1. Clone this repository
2. Ensure Docker and Docker Compose are installed on your system
3. Configure environment variables in [.env](.env) if needed
4. Start the containers using the commands in the Usage section below

## Usage

```bash

docker compose config
docker compose up -d

```

Access the application at [http://localhost:8080](http://localhost:8080)

### Stop containers

```bash
docker compose down
```

### View logs

```bash
docker compose logs -f
```

## Directory Structure

```
.
├── README.md                  # This file
├── docker-compose.yml         # Docker Compose configuration
├── .env                       # Environment variables
├── nginx/                     # Nginx configuration
│   └── default.conf          # Nginx server configuration
├── php/                       # PHP container build files
│   ├── Dockerfile            # PHP image definition
│   └── php.ini               # PHP configuration
└── src/                       # Application source code
    └── public/               # Public web root
        └── index.php         # Application entry point
```

## License

This repository is for personal/private use only.
