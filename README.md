# Dockerized Stack: PHP, MySQL, Redis, Node, Mailpit

## Basic PHP Setup

To get started with the PHP environment, follow these steps:

1. Copy the `.env.example` file to `.env`:

cp .env.example .env

2. Bring up the PHP service using Docker Compose:

docker compose up -d app

3. After the service is up, you should be able to access PHP configuration
   information at `localhost:8200`. This information is located in `src/public/index.php`.

## Installing Laravel

To install Laravel within this environment:

Run the following commands:

rm -rf src/public

sh fire composer create-project --prefer-dist laravel/laravel src
