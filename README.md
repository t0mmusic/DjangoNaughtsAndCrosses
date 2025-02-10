# Django Noughts and Crosses

This repository contains a multiplayer Noughts and Crosses (Tic-Tac-Toe) game built with Django and WebSockets, running in a Dockerized environment with PostgreSQL and PGAdmin.

## Features
- **Django Backend**: Handles game logic and user interactions.
- **WebSockets**: Real-time game communication using Django Channels and Daphne.
- **PostgreSQL Database**: Stores game state and player data.
- **PGAdmin**: Database management via a web interface.
- **Dockerized Setup**: Uses Docker Compose to manage services.

---

## Prerequisites
- **Docker** and **Docker Compose** installed on your system.

---

## Project Structure
```
django-noughts-crosses/
│── django/              # Contains Django project files
│   ├── backend/         # Django project settings, ASGI setup
│   ├── game/            # Game logic and WebSocket consumers
│   ├── manage.py        # Django management script
│   ├── requirements.txt # Python dependencies
│   ├── Dockerfile       # Django service Dockerfile
│── .env                 # Environment variables
│── docker-compose.yml   # Orchestration for all services
│── .gitignore           # Git ignored files
│── README.md            # Project documentation
```

---

## Running the Application

### 1. Clone the Repository
```sh
git clone <repo-url>
cd django-noughts-crosses
```

### 2. Set Up Environment Variables
Create a `.env` file in the project root:
```sh
POSTGRES_DB=noughts_crosses_db
POSTGRES_USER=postgres
POSTGRES_PASSWORD=postgres
PGADMIN_DEFAULT_EMAIL=admin@example.com
PGADMIN_DEFAULT_PASSWORD=admin
```

### 3. Build and Start the Containers
```sh
docker-compose up --build -d
```
This will:
- Start the Django app with Daphne
- Start PostgreSQL and PGAdmin
- Expose ports for the web app and database management

### 4. Access the Services
- **Django Web App**: http://localhost:8000
- **PGAdmin**: http://localhost:5050 (Login using credentials from `.env`)

---

## Stopping and Cleaning Up
To stop the containers:
```sh
docker-compose down
```
To remove all containers and volumes:
```sh
docker-compose down -v
```

---

## Future Enhancements
- User authentication
- Frontend UI for game interactions
- Persistent game state storage
- Deploy to cloud provider

---

## Contributing
Feel free to fork this repository and submit pull requests for improvements!

---

## License
This project is open-source and licensed under the MIT License.

