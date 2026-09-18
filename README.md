# docker-compose-stacks

Ready-to-use docker-compose stacks, pre-configured with data persistence

> **Nota:** intended for personal and local use only

## Requirements

- [Docker](https://docs.docker.com/get-docker/)
- Docker Compose (included in Docker Desktop or via the `docker compose` plugin)

## Available stacks

| Stack                                  | Description                                  |
| -------------------------------------- | -------------------------------------------- |
| [postgres-pgadmin](./postgres-pgadmin) | PostgreSQL + pgAdmin4, with data persistence |

## Usage

1. Go into the stack's folder:
   ```bash
   cd stack-name
   ```
2. Start the containers:
   ```bash
   docker compose up -d
   ```
3. Check status:
   ```bash
   docker compose ps
   ```
4. Stop:
   ```bash
   docker compose down
   ```
5. Stop and wipe data (volumes):
   ```bash
   docker compose down -v
   ```

## Structure

```
compose-stacks/
├── README.md
├── postgres-pgadmin/
│   ├── docker-compose.yml
│   └── README.md
└── (future stacks...)
```

Each stack has its own folder with `docker-compose.yml` and a stack-specific README covering ports, variables, and volumes

## Author

Anne S. Pinheiro Lima
[LinkedIn](https://www.linkedin.com/in/anne-s-pinheiro-lima-16a607424/)
