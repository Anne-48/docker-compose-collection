# postgres-pgadmin

PostgreSQL + pgAdmin4<br>
Pre-configured with pgAdmin connected to Postgres server with data persistence

> **Nota:** intended for personal and local use only

## Requirements

- Docker
- Docker Compose
- Compatible with Postgres 18+

## What's included

- **postgres** - Postgres database, with healthcheck. Version `18`
- **pgadmin4** - pgAdmin web UI, auto-connected to the `postgres`, runs after postgres healthcheck. Latest version

## Default config

|                    | Value             |
| ------------------ | ----------------- |
| Postgres root user | `postgres`        |
| Postgres password  | `admin123`        |
| Postgres database  | `dbLocal`         |
| pgAdmin email      | `admin@admin.com` |
| pgAdmin password   | `admin123`        |

<br>

Modifiable variables in order (`POSTGRES_USER`, `POSTGRES_PASSWORD`, `POSTGRES_DB`, `PGADMIN_DEFAULT_EMAIL`, `PGADMIN_DEFAULT_PASSWORD`)
<br>
If you change the Postgres service settings, also check and update pgAdmin's, including the JSON block config

## Ports

| Service  | Port |
| -------- | ---- |
| Postgres | 5432 |
| pgAdmin  | 8080 |

<br>

Modifiable variables in order (`POSTGRES_PORT`, `PGADMIN_PORT`)

## Data persistence

Data is stored locally in:

- `./data/postgresql` (Postgres)
- `./data/pgadmin` (pgAdmin)

These paths are also modifiable<br>
Edit the `volumes:` section in `docker-compose.yml`

## Usage

1. Create a folder for your project and place `docker-compose.yml` inside, open the terminal from the folder<br><br>
2. Start the stack:
   ```bash
   docker compose up -d
   ```
3. Check status:
   ```bash
   docker compose ps
   ```
4. Access pgAdmin at [http://localhost:8080](http://localhost:8080) - the Postgres server is already registered<br><br>
5. Stop:
   ```bash
   docker compose down
   ```
6. Stop and wipe data:
   ```bash
   docker compose down -v
   ```

## Permissions

If you hit permission errors on the local data folders:<br>
Run this on your host machine from the same folder as `docker-compose.yml`:

```bash
sh -c "chown -R 999:999 ./data/postgresql && chown -R 5050:5050 ./data/pgadmin"
```

(`999:999` and `5050:5050` are the UID:GID the `postgres` and `pgadmin4` images on docker)

## Author

Anne S Pinheiro Lima
[LinkedIn](https://www.linkedin.com/in/anne-s-pinheiro-lima-16a607424/)
