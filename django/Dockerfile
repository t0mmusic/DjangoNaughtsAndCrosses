# Use official Python image
FROM python:3.11

# Set working directory
WORKDIR /app

# Install dependencies
COPY ./requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copy Django project
COPY . .

# Expose ports for web app and WebSockets
EXPOSE 8000

# Run migrations and start server
CMD ["daphne", "-b", "0.0.0.0", "-p", "8000", "backend.asgi:application"]
