# Entorno local con Docker (PostgreSQL + RabbitMQ)

Este repositorio incluye un `docker-compose.yml` para levantar los servicios de
infraestructura (PostgreSQL y RabbitMQ) en Docker, mientras ejecutas la app
localmente en IntelliJ IDEA.

## Requisitos

- Docker Desktop o Docker Engine con Docker Compose.
- IntelliJ IDEA (Community o Ultimate) para iniciar la app localmente.

## Levantar servicios con Docker

```bash
docker compose up -d
```

Servicios disponibles:

- **PostgreSQL**: `localhost:5432`
  - Base de datos: `osdepym`
  - Usuario: `osdepym`
  - Password: `osdepym`
- **RabbitMQ**: `localhost:5672`
  - Usuario: `osdepym`
  - Password: `osdepym`
- **RabbitMQ Management UI**: `http://localhost:15672`

## Ejecutar la app desde IntelliJ

1. Abre el proyecto en IntelliJ IDEA.
2. Crea o edita la configuración de ejecución para que use las variables de
   entorno (o configuración equivalente) que apunten a los servicios de Docker.
3. Asegúrate de que la app use `localhost` para conectarse a PostgreSQL y
   RabbitMQ.

Ejemplo de variables de entorno (ajústalas según tu app):

```bash
DB_HOST=localhost
DB_PORT=5432
DB_NAME=osdepym
DB_USER=osdepym
DB_PASSWORD=osdepym

RABBITMQ_HOST=localhost
RABBITMQ_PORT=5672
RABBITMQ_USER=osdepym
RABBITMQ_PASSWORD=osdepym
```

## Detener servicios

```bash
docker compose down
```
