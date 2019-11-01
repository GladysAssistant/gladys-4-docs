---
name: setup-env
title: Dev Environnement
permalink: "/en/development"
lang: en
category: Development
---

You'll find here instructions to setup a dev env for Gladys 4.

## Server

The server is a Node.js app.

### Install system dependencies

You'll need:

- Node.js >= 10
- sqlite3
- openssl
- openzwave + libopenzwave1.5-dev
- python

A good help can be to look at [CircleCI config file](https://github.com/GladysAssistant/Gladys/blob/master/.circleci/config.yml).

### Clone Gladys Git repo

```
git clone https://github.com/GladysAssistant/Gladys gladys && cd gladys
```

### Install NPM dependencies

```
cd server
```

```
npm install
```

### Start DB migration

```
npm run db-migrate:dev
```

### Start the server

```
npm start
```

The server should be accessible at http://localhost:1443.

## Frontend

At the root of the git repo, do:

```
cd front
```

### Install NPM dependencies

```
npm install
```

### Start the frontend

```
npm start
```

The frontend should be accessible at http://localhost:1444.
