# Nepse Portfolio Project

This project is a Django-based backend with a PostgreSQL database, containerized using Docker and orchestrated with Docker Compose.

## Prerequisites
- Docker Desktop (Windows/Mac) or Docker Engine (Linux)
- Docker Compose

## Project Structure
```
├── backend/           # Django backend code
│   ├── manage.py
│   ├── requirements.txt
│   └── ...
├── frontend/          # (Optional) Frontend code
├── docker-compose.yml # Docker Compose configuration
```

## Quick Start

1. **Clone the repository**
   ```bash
   git clone <your-repo-url>
   cd nepse-portfolio
   ```

2. **Build and start the containers**
   ```bash
   docker-compose up --build
   ```
   This will build the Django backend image and start both the backend and PostgreSQL containers.

3. **Access the application**
   - Backend: http://localhost:8000
   - PostgreSQL: Exposed internally to the backend container

4. **Stop the containers**
   ```bash
   docker-compose down
   ```

## Environment Variables
- Database settings are configured in `docker-compose.yml` under the `db` service.
- Update `backend/nepse_portfolio/settings.py` to use these environment variables for database connection.

## Useful Commands
- Run migrations:
  ```bash
  docker-compose run web python manage.py migrate
  ```
- Create a superuser:
  ```bash
  docker-compose run web python manage.py createsuperuser
  ```
- View logs:
  ```bash
  docker-compose logs
  ```

## Notes
- The `backend/venv` and `db.sqlite3` are excluded from Docker builds via `.dockerignore`.
- The backend code is mounted as a volume for live code reloading during development.

---

Feel free to update this README with more details as your project evolves.
