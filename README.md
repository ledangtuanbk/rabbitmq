# RabbitMQ Development Environment

This repository provides a pre-configured, Docker-based local development environment for [RabbitMQ](https://www.rabbitmq.com/). It uses `docker-compose` to spin up a RabbitMQ instance complete with the Management UI.

## Prerequisites

- [Docker](https://docs.docker.com/get-docker/)
- [Docker Compose](https://docs.docker.com/compose/install/)

## Getting Started

1. Start the RabbitMQ container in the background:

   ```bash
   docker compose up -d
   ```

2. To stop the container without losing data:

   ```bash
   docker compose stop
   ```

3. To tear down the container and remove associated volumes (this will delete your queues and data):

   ```bash
   docker compose down -v
   ```

## Connectivity & Ports

Once the container is running, RabbitMQ exposes the following ports:

- **`5672` (AMQP):** The primary protocol port where your applications will connect.
- **`15672` (Management UI):** The HTTP port for the web-based management dashboard.

## Credentials

The default credentials for both the AMQP connection and the Management UI are:

- **Username:** `guest`
- **Password:** `guest`

## Accessing the Management UI

You can access the RabbitMQ Management UI by navigating to [http://localhost:15672](http://localhost:15672) in your browser and logging in with the default credentials.

## Persistence

The `docker-compose.yml` is configured with a named volume (`rabbitmq_data`) mapped to `/var/lib/rabbitmq` inside the container. This ensures that your exchanges, queues, messages, and user configurations persist across container restarts.