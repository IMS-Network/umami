umami
=====

Umami is a fast, simple, and privacy-focused alternative to Google Analytics.

Getting started
---------------

For a detailed guide on getting started with Umami, please refer to the [official documentation](https://umami.is/docs/).

Installing from source
----------------------

To install Umami from source, you will need a server with Node.js version 12 or newer and a database.\
Umami supports MySQL and PostgreSQL databases. Follow these steps to install Umami from source:

### Requirements

- A server with Node.js version 12 or newer
- A database. Umami supports MySQL and PostgreSQL databases.

### Install Yarn

```
Copy codenpm install -g yarn


```

### Get the source code and install packages

```
bashCopy codegit clone https://github.com/umami-software/umami.git

cd umami

yarn install


```

### Configure umami

Create an `.env` file with the following

```
makefileCopy codeDATABASE_URL=connection-url


```

The connection url is in the following format:

```
bashCopy codepostgresql://username:mypassword@localhost:5432/mydb

mysql://username:mypassword@localhost:3306/mydb


```

### Build the application

```
bashCopy codeyarn build


```

The build step will also create tables in your database if you are installing for the first time. It will also create a login account with username **admin** and password **umami**.

### Start the application

```
bashCopy codeyarn start


```

By default, this will launch the application on `http://localhost:3000`. You will need to either [proxy](https://docs.nginx.com/nginx/admin-guide/web-server/reverse-proxy/) requests from your web server or change the [port](https://nextjs.org/docs/api-reference/cli#production) to serve the application directly.

Installing with Docker
----------------------

To install Umami with Docker, you can either build the container and start up a PostgreSQL or MySQL database, or pull just the Umami Docker image with PostgreSQL or MySQL support. Follow these steps to install Umami with Docker:

### Build and start the container with PostgreSQL or MySQL

```
bashCopy codedocker compose up


```

### Pull just the Umami Docker image with PostgreSQL support:

```
bashCopy codedocker pull docker.umami.dev/umami-software/umami:postgresql-latest


```

### Pull just the Umami Docker image with MySQL support:

```
bashCopy codedocker pull docker.umami.dev/umami-software/umami:mysql-latest


```

Getting updates
---------------

To get the latest features, simply do a pull, install any new dependencies, and rebuild:

```
bashCopy codegit pull

yarn install

yarn build


```

To update the Docker image, simply pull the new images and rebuild:

```
bashCopy codedocker compose pull

docker compose up --force-recreate


```

License
-------

Umami is licensed under the [MIT License](LICENSE).

