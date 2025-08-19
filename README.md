# Dockerized PHP Application

This project is a dockerized PHP application using Nginx as a web server, PHP-FPM to execute PHP code, and MariaDB as the database. The entire environment is managed by Docker Compose.

## Services

The `docker-compose.yml` file defines the following services:

*   **`web`**: An Nginx container that acts as a web server and reverse proxy. It routes requests to the PHP containers and serves static files.
*   **`php_1`, `php_2`, `php_3`, `php_4`**: Four PHP-FPM containers that execute the application's PHP code. Nginx load balances requests across these four containers.
*   **`db_bestdistributor`**: A MariaDB container for the application's database.
*   **`phpmyadmin`**: A container running phpMyAdmin, providing a web-based interface for managing the MariaDB database.

## Getting Started

### Prerequisites

*   [Docker](https://docs.docker.com/get-docker/)
*   [Docker Compose](https://docs.docker.com/compose/install/)

### Configuration

1.  **Environment Variables**: The configuration for the database is stored in the `.env` file. You can modify this file to change the database credentials.

    ```bash
    # Main DB (Best Distributor)
    DB_HOST=db_masterkoi
    DB_DATABASE=accounting_db
    DB_USER=user
    DB_PASSWORD=password
    DB_ROOT_PASSWORD=rootpassword
    ```

### Running the Application

1.  **Clone the repository**:
    ```bash
    git clone https://github.com/DayanLeksonoPutro/bestdistributor_docker.git
    cd bestdistributor_docker
    ```

2.  **Start the services**:
    ```bash
    docker-compose up -d
    ```

## Accessing the Application

*   **Web Application**: Once the containers are running, you can access the web application at [http://localhost:8080](http://localhost:8080).
*   **phpMyAdmin**: You can access phpMyAdmin at [http://localhost:8081](http://localhost:8081) (Note: you will need to add a port mapping for phpmyadmin in the docker-compose file to access it, for example `ports: - 8081:80`).
