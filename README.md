# FNF Strapi Backend

Installation of Strapi console and API service on your machine.


## Requirements

Node.js >= 10.x installed on your machine
NPM >= 6.x installed on your machine
PostgreSQL installed on your machine


# Getting started

Either checkout this repo or build from scratch.



## Quickstart - checkout from repo

Check out this repo on to you local machine.

Update the /config/database.js

```
module.exports = ({ env }) => ({
  defaultConnection: 'default',
  connections: {
    default: {
      connector: 'bookshelf',
      settings: {
        client: 'postgres',
        host: env('DATABASE_HOST', '127.0.0.1'),
        port: env.int('DATABASE_PORT', 5432),
        database: env('DATABASE_NAME', 'dbname'),
        username: env('DATABASE_USERNAME', 'db_user'),
        password: env('DATABASE_PASSWORD', 'password'),
        ssl: env.bool('DATABASE_SSL', false),
      },
      options: {}
    },
  },
});

```


Running Strapi:
You can start by doing....
```


  cd /Users/u/development/project/projectname
  npm run develop
```


---
## Building from scratch

Using instructions, here from Strapi site 

https://strapi.io/documentation/developer-docs/latest/guides/databases.html#mongodb-installation


Run:
```
npx create-strapi-app strapi-backend
```

Select Postgres as you main database. Accept the default options for all others.



```

Your application was created at /Users/u/development/project/projectname.

Available commands in your project:

  npm run develop
  Start Strapi in watch mode.

  npm run start
  Start Strapi without watch mode.

  npm run build
  Build Strapi admin panel.

  npm run strapi
  Display all available commands.

You can start by doing:

  cd /Users/u/development/project/projectname
  npm run develop
```


---
# PostgreSQL database

Set up your local database:

```
psql postgres

CREATE DATABASE dbname;

CREATE ROLE db_user WITH LOGIN PASSWORD 'password' CREATEDB;

GRANT ALL PRIVILEGES ON DATABASE dbname TO db_user;


```
