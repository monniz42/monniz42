# Setup Guide

To set up the project locally, you would typically follow these steps:

1.  **Clone the repository**.
2.  **Install PHP dependencies**: Run `composer install` in the `product/application` directory.
3.  **Install Node.js dependencies**: Run `npm install` in the `product/application` directory.
4.  **Create a `.env` file**: Copy `.env.example` to `.env` and configure the database and other settings.
5.  **Generate an application key**: Run `php artisan key:generate`.
6.  **Run database migrations**: Run `php artisan migrate`.
7.  **Run database seeders (optional)**: Run `php artisan db:seed`.
8.  **Compile frontend assets**: Run `npm run dev` or `npm run build`.
9.  **Serve the application**: Run `php artisan serve`.
