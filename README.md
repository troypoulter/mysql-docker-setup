# A simple MySQL local setup using Docker

This guide will walk you through a simple process to start up a local MySQL setup in no time using Docker!

By following this guide, you will be running through Docker the following:

- [MySQL Server v8.0.23](https://hub.docker.com/_/mysql)
- [MySQL Workbench v8.0.23](https://hub.docker.com/r/linuxserver/mysql-workbench)
- [Adminer v4.8.0](https://hub.docker.com/_/adminer)

The tools `MySQL Workbench` and `Adminer` are two solid GUI options for interacting with the `MySQL Server` and is recommended to use either of them for interacting with your database!

If you'd prefer to download these or other tools directly and run them not via Docker, go ahead and simply remove their references from the `docker-compose.yml`.

## Pre-reqs

- Docker v18.06.0+ - [Docker install link](https://www.docker.com/products/docker-desktop)

## Setting it up

### Starting the services

1. Start up your favourite `cmd` tool and navigate to this folder.
2. Open up `docker-compose.yml` in your favourite text editor and update `MYSQL_ROOT_PASSWORD` with an appropiate password.
3. Run this command to start up the services.

   ```bash
   docker-compose up -d
   ```

   > This will start up the three services in the background, it may take a while at first to pull down the images.

When you want to connect to the `MySQL Server`, use the below as a reference:

- **Hostname**: mysql-db
- **Port**: 3306
- **Username**: root
- **Password**: <INSERT_PASSWORD>
- **Database**: Can leave this blank as no db exists yet.

### Using MySQL Workbench

1. Once the services are started, navigate to `http://localhost:3000/`.
2. You should see the tool running, click on the add connection button and enter the appropiate values, referring to the section above and give the connection a name such as `mysql`.
3. Click `OK` then click on that connection, enter in your password and you're good to go!

### Using Adminer

1. Once the services are started, navigate to `http://localhost:8080/`.
2. You should see the tool running, enter in the appropiate values, referring to the section above and click `Login` and you're good to go!

I hope you found this guide useful and gets you running a local MySQL setup with minimal configuration needed!

If you encounter any challenges, please raise an issue against this repository.
