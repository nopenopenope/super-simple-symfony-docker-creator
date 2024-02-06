# Super Simple Symfony Docker Creator

This is a simple script to create a Symfony project with Docker. It will create a new directory with the project name
and create a Dockerfile and docker-compose.yml file. The goal of this project is to ease the process it takes to create
new Symfony projects with Docker for customers.

## Installation

To install this script, you can run the following command:

```bash
curl -O https://raw.githubusercontent.com/nopenopenope/symfony-docker-creator/master/sssdc.sh
chmod +x sssdc.sh
mv sssdc.sh /usr/local/bin/symfony-docker-creator
```

## Usage

After you have copied the script to a bin location of your choice, you have to restart your terminal (just re-open it).
After that, you can run the following command to create a new Symfony project with Docker:

To create an instance with MariaDB (latest), Nginx (latest), PHP 8.2-fpm and port 5555, you can run the following
command:

```bash
symfony-docker-creator --webserver nginx:1.25.3-alpine --php php:8.3-fpm --port 5555
```

To create an instance with MySQL (latest), Apache (latest), PHP 7.4-fpm and port 5555, you can run the following
command:

```bash
symfony-docker-creator --webserver nginx:1.25.3-alpine --php php:8.3-fpm --database mysql:latest
```

## Options

- `--webserver <webserver>`
    - Specifies the web server to use. Replace `<webserver>` with the name of the web server (e.g., nginx, apache).

- `--php <version>`
    - Sets the PHP version to use. Replace `<version>` with the desired PHP version number (e.g., 7.4, 8.0).

- `--port <port_http>`
    - Defines the HTTP port to use. Replace `<port_http>` with the port number for HTTP traffic (e.g., 80).

- `--port-https <port_https>`
    - Defines the HTTPS port to use. Replace `<port_https>` with the port number for HTTPS traffic (e.g., 443).

- `--database <database>`
    - Specifies the database to use. Replace `<database>` with the name of your database (e.g., mysql, postgresql).

- `--domain <domain>`
    - Sets the domain name for the server. Replace `<domain>` with your domain name (e.g., example.com).

- `--symfony <version>`
    - Specifies the Symfony version to use. Replace `<version>` with the desired Symfony version (e.g., 4.4, 5.2).

- `--xdebug`
    - Enables Xdebug for PHP debugging. No additional value is needed.

- `--force`
    - Forces the script to run, potentially overriding any safety checks. No additional value is needed.

**Note**: You have to adapt your `/etc/hosts` file manually to the point of your domain.

## Supported Webservers

Currently, only NGINX and Apache are supported. Nginx has automatic SSL certificate generation onboard.

## Contribution

I'd love to review your PRs for this handy script. If you would like to introduce logic for Caddy, FrankenPHP or
similar, feel free to go ahead and implement it. I'll gladly review and merge your PR.
