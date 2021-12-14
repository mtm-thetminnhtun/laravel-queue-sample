# Laravel Queue Sample

This is a laravel queue sample project.

[Tutorial](https://github.com/thetminnhtun-scm/laravel-queue-sample/wiki/Mail-sending-using-queue-by-database-driver)

## Requirement

- PHP 8.0 or higher
- Laravel 8.0 or higher
- Database
## Installation

Clone the repo locally:

```
git clone https://github.com/thetminnhtun-scm/laravel-queue-sample.git

cd laravel-queue-sample
```

Install PHP dependencies:

```
composer install
```

Setup configuration:

```
cp .env.example .env
```

Generate application key:

```
php artisan key:generate
```

Create database and configure in `.env` file

For Example:

```
DB_CONNECTION=mysql
DB_HOST=localhost
DB_PORT=3306
DB_DATABASE=laravel_queue_sample
DB_USERNAME=root
DB_PASSWORD=
```

Setup mail in `.env` file

```
MAIL_MAILER=smtp
MAIL_HOST=mailhog
MAIL_PORT=1025
MAIL_USERNAME=null
MAIL_PASSWORD=null
MAIL_ENCRYPTION=null
MAIL_FROM_ADDRESS=null
MAIL_FROM_NAME="${APP_NAME}"
```

If you don't need to send actually. Just change `smtp` to `log` in `MAIL_MAILER`.

```
MAIL_MAILER=log
```

Run database migrations:

```
php artisan migrate
```

Run the dev server:

```
php artisan serve
```

Development Server (http://localhost:8000) will start.

## Usage

Run queue worker to start queue.
```
php artisan queue:work
```

Go route http://localhost:8000/mail/sent to sent a mail.

Check mail in your inbox. If you used mail driver `log`, check in `laravel.log`. You will see sent mail. If you don't see, check `queue:work` command working well or not.

