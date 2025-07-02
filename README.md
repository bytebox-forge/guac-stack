# Guacamole Docker Stack

This repository contains a Portainer-ready Docker Compose stack for deploying Apache Guacamole, Guacd, and PostgreSQL for remote desktop gateway access in a homelab environment.

## Features
- Apache Guacamole (latest stable)
- Guacd (latest stable)
- PostgreSQL backend
- Persistent named volumes for database and config
- Health checks and service dependencies
- User-defined bridge network (`docker-core`)

## Usage

1. **Clone this repository:**
   ```sh
   git clone https://github.com/YOUR_USERNAME/guac-stack.git
   cd guac-stack
   ```
2. **Import `docker-compose.yml` into Portainer** as a stack, or deploy via CLI:
   ```sh
   docker compose up -d
   ```
3. **Access Guacamole:**
   - URL: `http://<your-server-ip>:8080/guacamole/`
   - Default login: `guacadmin` / `guacadmin` (change immediately after first login)

## Volumes
- `guac-db-data`: PostgreSQL data (persistent)
- `guac-config`: Guacamole config/extensions (persistent)

## Security Notes
- Expose port 8080 only to trusted networks.
- Use a reverse proxy (Nginx, Traefik) with HTTPS for secure access.
- Change all default passwords.
- Regularly update images.
- Restrict network access to database and guacd services.

## License
MIT
