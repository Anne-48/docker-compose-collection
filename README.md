# docker-compose-stacks

Ready-to-use docker-compose stacks, pre-configured with data persistence

> **Nota:** intended for personal and local use only

## Requirements

- [Docker](https://docs.docker.com/get-docker/)
- [Docker Compose](https://docs.docker.com/compose/install/) (included in Docker Desktop or via the `docker compose` plugin)

## Available stacks

| Stack                                      | Description                                  |
| ------------------------------------------ | -------------------------------------------- |
| [postgres-pgadmin](./postgres-pgadmin)     | PostgreSQL + pgAdmin4, with data persistence |
| [mariadb-phpmyadmin](./mariadb-phpmyadmin) | MariaDB + phpMyAdmin, with data persistence  |

## Structure

```
compose-stacks/
├── README.md
├── postgres-pgadmin/
│   ├── docker-compose.yml
│   └── README.md
├── mariadb-phpmyadmin/
│   ├── docker-compose.yml
│   └── README.md
└── (future stacks...)
```

Each stack has its own folder with `docker-compose.yml` <br>
And a stack-specific README covering ports, variables, and volumes

## Author

Anne S. Pinheiro Lima
[LinkedIn](https://www.linkedin.com/in/anne-s-pinheiro-lima-16a607424/)
