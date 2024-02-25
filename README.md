# Docker Stack: PHP, MySQL, Redis + Node, Mailpit

## Basic PHP Setup

To get started with the PHP environment, follow these steps:

Copy the `.env.example` file to `.env`:

    cp .env.example .env

Bring up the PHP service using Docker Compose:

    docker compose up -d app

After the service is up, you should be able to access PHP configuration
information at `localhost:8200`. This information is located in `src/public/index.php`.

## Allow changes to public folder

To prevent Git from tracking changes to a specific subfolder, such as src/public, you can utilize the git update-index command with the --assume-unchanged option. This command tells Git to treat the specified files or directories as if they are unchanged, effectively ignoring any modifications made within them.

Execute the following command to instruct Git to ignore changes within the src/public directory:

    git update-index --assume-unchanged src/public/*

## Installing Laravel

To install Laravel within this environment:

Run the following commands:

    # composer requires a clean folder
    rm -rf src/public

    # use bash script to access container
    sh fire composer create-project --prefer-dist laravel/laravel .

## Install (Laravel) Filament

    sh fire composer require filament/filament

    php artisan migrate
    php artisan filament:install --panels
    php artisan filament:user
