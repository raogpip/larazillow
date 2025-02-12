# Larazillow

Larazillow is a real estate listing platform built with **Laravel** and **Vue.js** using **Inertia.js**. It allows users to browse property listings, register and log in, sort listings, receive notifications, and upload images.

## Features
- **User authentication** (registration & login)
- **Browse real estate listings** with sorting options
- **Image uploads** for listings
- **Notifications system**
- **MariaDB database** running in Docker

## Technologies Used
- **Laravel** 
- **Vue.js + Inertia.js** 
- **MariaDB** (Dockerized) 
- **Laravel Breeze** (for authentication)

## Installation

### Prerequisites
- Docker & Docker Compose
- PHP 8+
- Composer
- Node.js & npm

### Setup
1. Clone the repository:
   ```sh
   git clone https://github.com/raogpip/larazillow.git
   cd larazillow
   ```

2. Install dependencies:
   ```sh
   composer install
   npm install
   ```

3. Copy environment file and configure database:
   ```sh
   cp .env.example .env
   ```
   Edit `.env` file and set database credentials.

4. Run database migrations:
   ```sh
   php artisan migrate --seed
   ```

5. Start the development server:
   ```sh
   php artisan serve
   ```
   In another terminal, start Vite for front-end:
   ```sh
   npm run dev
   ```

6. If using Docker for MariaDB, start the container:
   ```sh
   docker-compose up -d
   ```

## Usage
- Register or log in to browse property listings.
- Sort listings using the available filters.
- Receive notifications about new listings.
- Upload images when adding properties.

## Credits
This project was created as a part of [Master Laravel 11 and Vue 3 - Build SPA Application](https://www.udemy.com/course/master-laravel-6-with-vuejs-fullstack-development/) course.

