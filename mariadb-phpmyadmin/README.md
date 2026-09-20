# mariadb-phpmyadmin

MariaDB + phpMyAdmin with data persistence

> **Nota:** intended for personal and local use only

## Requirements

- Docker
- Docker Compose
- Compatible with MariaDB 11+

## What's included

- **mariadb** - MariaDB database, with healthcheck. Version `11`
- **phpmyadmin** - phpMyAdmin web UI, runs after mariadb healthcheck. Latest version

## Default config

|                       | Value      |
| --------------------- | ---------- |
| MariaDB root password | `admin123` |
| MariaDB database      | `dbLocal`  |

<br>
Modifiable variables (`MARIADB_ROOT_PASSWORD`, `MARIADB_DATABASE`)
 
## Ports
 
| Service    | Port |
| ---------- | ---- |
| MariaDB    | 3306 |
| phpMyAdmin | 8081 |
 
<br>
Modifiable variables in order (`MARIADB_PORT`, `PHPMYADMIN_PORT`)
 
## Data persistence
 
Data is stored locally in:
 
- `./data/mariadb` (MariaDB)
This path is also modifiable<br>
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
4. Access phpMyAdmin at [http://localhost:8081](http://localhost:8081) <br>Log in with the root user (always named `root`) and the password set in `MARIADB_ROOT_PASSWORD`<br><br>
5. Stop:
```bash
   docker compose down
```
6. Stop and wipe data:
```bash
   docker compose down -v
```
 
## Permissions
 
If you hit permission errors on the local data folder:<br>
Run this on your host machine from the same folder as `docker-compose.yml`:
 
```bash
sh -c "chown -R 999:999 ./data/mariadb"
```
 
(`999:999` is the UID:GID the `mysql` user runs as inside the `mariadb` image on docker)
 
## Author
 
Anne S Pinheiro Lima
[LinkedIn](https://www.linkedin.com/in/anne-s-pinheiro-lima-16a607424/)
