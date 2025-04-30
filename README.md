# Docker Test Application

A simple web application demonstrating Docker containerization with Node.js, Express, and MongoDB.

## Project Overview

This project is a basic user registration system built with:
- Node.js and Express for the backend server
- MongoDB for data storage
- Docker for containerization
- Simple HTML/CSS frontend

## Prerequisites

- Docker and Docker Compose
- Node.js (if running locally without Docker)
- MongoDB (if running locally without Docker)

## Project Structure

```
.
├── public/                 # Static files
│   ├── index.html         # Frontend user interface
│   └── style.css          # Styling
├── Dockerfile             # Node.js application container configuration
├── mongodb.yaml          # Docker Compose configuration for MongoDB
├── package.json          # Node.js dependencies
├── package-lock.json     # Locked versions of dependencies
└── server.js             # Express server implementation
```

## Features

- User registration form
- MongoDB integration for data storage
- Containerized application setup
- MongoDB Express admin interface

## Configuration

The application uses the following default configuration:
- Server Port: 5050
- MongoDB URL: mongodb://admin:qwerty@localhost:27017
- MongoDB Express Port: 8081

## Getting Started

1. Clone the repository
2. Start the MongoDB container:
   ```bash
   docker-compose -f mongodb.yaml up -d
   ```
3. Build and run the application container:
   ```bash
   docker build -t testapp .
   docker run -p 5050:5050 testapp
   ```

## API Endpoints

- `GET /getUsers` - Retrieve all users
- `POST /addUser` - Add a new user

## Environment Variables

MongoDB container:
- `MONGO_INITDB_ROOT_USERNAME`: admin
- `MONGO_INITDB_ROOT_PASSWORD`: qwerty

Application container:
- `MONGO_DB_USERNAME`: admin
- `MONGO_DB_PWD`: qwerty

## Accessing the Application

- Web Application: http://localhost:5050
- MongoDB Express Admin Interface: http://localhost:8081

## Note

This is a test application for demonstrating Docker containerization. It's recommended to change the default credentials and properly secure the application before using in a production environment.
