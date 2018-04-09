# ECS Fargate Tutorial

Hello, and welcome to the fun and easy introduction to Amazon's Fargate platform in Elastic Container Service. In this tutorial, we will walk you through how to leverage Amazon's powerful container platform to encode thousands of images in only minutes. This project is built using the powerful [Laravel](https://laravel.com/) PHP web framework, which makes it easy to spin up a complex web app with queues and remote storage. 

### Prerequisites

For this tutorial, you are going to need the following:

- An AWS Account
- [Docker](https://www.docker.com/)
- (Optional) [AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/installing.html)

### Setup
- TODO

### Instructions
- TODO

---

## Development

### Setup Database
```bash
docker-compose up -d db
mysql -h 0.0.0.0 -u root -pVBrootFTW\! < docker/db/setup_db.sql
php artisan migrate
```

### Setup PHPStorm
1. Build the docker image in _docker/ide_:
    ```bash
    cd docker/ide
    docker build -t phpstorm .
    ```
1. Configure PHPStorm to use the docker image as the interpreter:
  1. Go to **Settings > Languages & Frameworks > PHP**.
  1. Click on "..." next to "CLI Interpreter".
  1. Add a Docker CLI Interpreter, set the image name to the one you built, and set the debugger extension to "/usr/local/lib/php/extensions/no-debug-non-zts-20160303/xdebug.so".
  1. (Docker for Mac) Add "-e DB_HOST=host.docker.internal" to the "Docker container" configuration.
1. Configure PHPStorm to use the phpunit.xml file for tests:
  1. Go to **Settings > Languages & Frameworks > PHP > Test Frameworks**.
  1. Click the "+" to add a "PHPUnit by Remote Interpreter" configuration.
  1. Set the "CLI Interpreter" to the one configured above.
  1. Set "Default configuration file" to "/opt/project/phpunit.xml".

## TODO
- [ ] TODO: Use Cloudformation to set up S3+RDS+ECS?
