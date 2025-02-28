# Laravel Setup
Laravel development environment with Docker, optimized for quick project startup.

## Prerequisites
- Docker and Docker Compose installed
- Composer
- Node.js and Yarn

## Project Structure
```
.
├── docker/
│   ├── nginx/
│   └── php/
├── laravel/
├── docker-compose.yml
└── .env
```

## Installation

### 1. Create Laravel Project
```bash
composer create-project laravel/laravel
```

### 2. Configure Environment
Copy .env.example to .env and configure the variables:
```bash
APP_NAME=test    # Base name for containers
```

### 3. Start Containers
```bash
docker-compose up -d
```

### 4. Install Frontend Dependencies
```bash
yarn install
yarn run dev
```

## Docker Containers
- **APP**: PHP-FPM (${APP_NAME:-test}-app)
- **Nginx**: Web Server (${APP_NAME:-test}-nginx)
- **MySQL**: Database (${APP_NAME:-test}-db)
- **phpMyAdmin**: DB Manager (${APP_NAME:-test}-phpmyadmin)

## Useful Commands
```bash
# Start containers
docker-compose up -d

# Stop containers
docker-compose down

# View container logs
docker-compose logs

# Access container shell
docker exec -it ${APP_NAME:-test}-app bash
```

## Contributing
Feel free to contribute with improvements through Pull Requests.
