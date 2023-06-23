# Laravel Oracle Database Connection

This guide provides step-by-step instructions on how to establish a connection between your existing Laravel PHP project and an Oracle database.

## Prerequisites

- Oracle Instant Client installed on your server or development environment.
- PHP environment with the `oci8` extension enabled.
- Composer dependency manager installed.

## Installation

1. **Oracle Instant Client**:

   Install the Oracle Instant Client on your server or development environment. This client provides the necessary libraries and tools to connect to an Oracle database.

2. **PHP Configuration**:

   Ensure that your PHP installation has the necessary extensions and configurations to work with Oracle databases. Follow the instructions specific to your PHP version and operating system to enable the `oci8` extension in your `php.ini` file.

3. **Laravel Configuration**:

   1. Open your Laravel project and locate the `config/database.php` file.
   2. In the `connections` array, add a new connection entry for Oracle:

      ```php
      'oracle' => [
          'driver'         => 'oracle',
          'host'           => env('DB_HOST', 'localhost'),
          'port'           => env('DB_PORT', '1521'),
          'database'       => env('DB_DATABASE', 'your_oracle_sid'),
          'username'       => env('DB_USERNAME', 'your_username'),
          'password'       => env('DB_PASSWORD', 'your_password'),
          'charset'        => 'utf8',
          'prefix'         => '',
          'prefix_schema'  => '',
          'server_version' => env('DB_SERVER_VERSION', '11g'),
      ],
      ```

      Update the `'host'`, `'port'`, `'database'`, `'username'`, and `'password'` values with the appropriate details for your Oracle database.

4. **Environment Variables**:

   In the `.env` file of your Laravel project, update the `DB_CONNECTION` variable to use the Oracle connection:


5. **Database Drivers**:

Install the required Oracle database drivers for Laravel using Composer:

```bash
composer require yajra/laravel-oci8
php artisan migrate
