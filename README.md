# Laravel Blog Starter Kit

This is [Laravel](https://laravel.com) blog starter kit project with [Filament](https://filamentphp.com) admin panel.

The goal of this repository is to showcase good [Laravel](https://laravel.com) development practices with a simple application.

## Features

*TODO*

[//]: # (- :fire: Burn after reading &#40;the note is destroyed after the first reading&#41;)
[//]: # (- :lock: Password protection)
[//]: # (- :clipboard: Copy note to clipboard in a click)
[//]: # (- :stopwatch: Expiration times, including a "forever" and "burn after reading" option)
[//]: # (- :hatched_chick: Admin panel built on [Filament]&#40;https://filamentphp.com&#41;)

## Roadmap

The following features will be implemented soon:

- API for integration with third parties https://github.com/gomzyakov/laravel-blog/issues/4
- File upload support (image, media and PDF preview)

## Requesting features

Open a [new issue](https://github.com/gomzyakov/laravel-blog/issues/new) to request a feature (or if you find a bug).

## How to run blog locally? 

Clone the project:

```bash
git clone git@github.com:gomzyakov/laravel-blog.git
```

I believe you already have Docker installed. If not, just do it on [Mac](https://docs.docker.com/desktop/install/mac-install/), [Windows](https://docs.docker.com/desktop/install/windows-install/) or [Linux](https://docs.docker.com/desktop/install/linux-install/).

Build the `laravel-blog` image with the following command:

```bash
docker compose build --no-cache
```

>This command might take a few minutes to complete.

When the build is finished, you can run the environment in background mode with:

```bash
docker compose up -d
```

We’ll now run `composer install` to install the application dependencies:

```bash
docker compose exec app composer install
```

Copy the environment settings:

```bash
docker compose exec app cp .env.local .env
```

Set encryption key with the `artisan` Laravel command-line tool:

```bash
docker compose exec app ./artisan key:generate --ansi
```

Migrate DB & seed fake data:

```bash
docker compose exec app ./artisan migrate:fresh --seed
```

And add Filament admin user:

```bash
docker compose exec app ./artisan make:filament-user
```

And open http://127.0.0.1:8000 in your favorite browser. Happy using Laravel Blog!

## How to get inside the container?

Access to the Docker container:

```bash
docker exec -ti laravel-blog-app bash
```

## License

This is open-sourced software licensed under the [MIT License](https://github.com/gomzyakov/php-code-style/blob/main/LICENSE).


[![GitHub release](https://img.shields.io/github/release/gomzyakov/laravel-blog.svg)](https://github.com/gomzyakov/laravel-blog/releases/latest)
[![license](https://img.shields.io/badge/License-MIT-green.svg)](https://github.com/gomzyakov/laravel-blog/blob/development/LICENSE)
[![codecov](https://codecov.io/gh/gomzyakov/laravel-blog/branch/main/graph/badge.svg?token=4CYTVMVUYV)](https://codecov.io/gh/gomzyakov/laravel-blog)
