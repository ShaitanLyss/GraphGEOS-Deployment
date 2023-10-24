# GEOS UI Deployment

This repository manages the deployment of the GEOS UI project.

## Pre-requisites
- Docker

## Deployment
1. Clone this repository
2. Copy the `.env.example` file to `.env` and fill in the values
3. Run `docker compose -f ./docker-compose.preprod.yml up --build` to start the deployment
4. Run `docker exec geos-ui-dev-backend-1 alembic upgrade head` to run the database migrations

The first time it will take a long time to build the images. Subsequent deployments will be faster.


## Development
- Autogenerate migrations 
    - `docker exec geos-ui-dev-backend-1 alembic revision --autogenerate -m "Migration message"`
    - The generated migration is a helper, it's important to review it and make sure it's correct

## Accessing the application
The application will be available at http://localhost.

## Customizing the application
You can set settings like language or night mode by hovering the upper right area of the screen.
