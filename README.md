# Fullstack application with a Microservice Architeture.

This is a fullstack application built with a microservice architecture approach using various technologies including Nest.js, Node.js, JavaScript/TypeScript, Next.js/React.js, MySQL, MongoDB, RabbitMQ, and Docker.

## Features

- Modular microservices for different application functionalities
- RESTful API design with Nest.js
- Frontend developed with Next.js and React.js
- Data persistence with MySQL and MongoDB
- Message broker for communication between services using RabbitMQ
- Containerization with Docker for easy deployment and scalability

- **Backend:**
  - [Nest.js](https://nestjs.com/)
  - [Node.js](https://nodejs.org/)
  - [JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript) / [TypeScript](https://www.typescriptlang.org/)
  - [TypeORM](https://typeorm.io/)

- **Frontend:**
  - [Next.js](https://nextjs.org/)
  - [React.js](https://reactjs.org/)

- **Databases:**
  - [MySQL](https://www.mysql.com/)
  - [MongoDB](https://www.mongodb.com/)

- **Messaging:**
  - [RabbitMQ](https://www.rabbitmq.com/)

- **Containerization:**
  - [Docker](https://www.docker.com/)

## Architecture

In this application, each service is independent and responsible for a specific funcionality and communicats with others using RabbitMQ. This type of architecture has many benefits such as scalability, maintainability, security, and separation of responsabilities.

## Installation

To run this application locally, follow these steps bellow:

1 .Clone the repository
 ```bash
 $ git clone https://github.com/Matheus-Rodrigues-Araujo/microservice-app
```
2. Install dependencies by accessing each directory and using the following command
 ```bash
 $ npm install
 ```
3. Set up environment variables

* `client`
 ```bash 

// .env.local

# Local Environment

# ADMIN SERVICE URL
NEXT_PUBLIC_ADMIN_SERVICE_URL=http://localhost:8000

# MAIN SERVICE URL
NEXT_PUBLIC_MAIN_SERVICE_URL=http://localhost:8001
```

 ```bash 

// .env.production

# Production Environment

# ADMIN SERVICE URL
NEXT_PUBLIC_ADMIN_SERVICE_URL=http://admin:8000

# MAIN SERVICE URL
NEXT_PUBLIC_MAIN_SERVICE_URL=http://main:8001
```
* `/admin`

 ```bash 

// .env.local

# Local Environment

# Synchronize
DB_SYNCHRONIZE=true

# MySQL HOST
DB_HOST=localhost

# MySQL PORT
DB_PORT=3306

# MySQL USERNAME
DB_USERNAME=

# MySQL PORT
DB_PASSWORD=

# MySQL DATABASE
DB_DATABASE=

MYSQL_DATABASE=
MYSQL_ROOT_PASSWORD=

# SERVICE URL
SERVICE1_URL=http://localhost:8000

# FRONTEND URL
FRONTEND_URL=http://localhost:3000

# RabbitMQ URL
RBQ_URL=

```

 ```bash 

// .env.production

# Production Environment


# Synchronize
DB_SYNCHRONIZE=false

# MySQL HOST
DB_HOST=db

# MySQL PORT
DB_PORT=3306

# MySQL USERNAME
DB_USERNAME=

# MySQL PORT
DB_PASSWORD=

# MySQL DATABASE
DB_DATABASE=

MYSQL_DATABASE=
MYSQL_ROOT_PASSWORD=

# SERVICE URL
SERVICE1_URL=http://service1:8000

# FRONTEND URL
FRONTEND_URL=http://localhost:3000

# RABBITMQ URL
RBQ_URL=
```

* `/main`

 ```bash 

// .env.local

# Local Environment

# MONGO URL
DB_URL=mongodb+srv://<username>:<password>@<cluster-address>/<database>

# ADMIN SERVICE URL
ADMIN_SERVICE_URL=http://localhost:8000

# FRONTEND URL
FRONTEND_URL=http://localhost:3000

# RABBITMQ URL
RBQ_URL=

# RABBITMQ QUEUE
RBQ_QUEUE=main_queue

```

 ```bash 

// .env.production

# Production Environment

# MONGO URL
DB_URL=mongodb+srv://<username>:<password>@<cluster-address>/<database>


# SERVICE URL
ADMIN_SERVICE_URL=http://admin:8000

# FRONTEND URL
FRONTEND_URL=http://localhost:3000

# RABBITMQ URL
RBQ_URL=

# RABBITMQ QUEUE
RBQ_QUEUE=

```

4. Run the application

* For `client`:
```bash 
    $ npm run dev
```

* For `admin`:
```bash 
    $ npm run start:dev
```

* For `main`:
```bash 
    $ npm run start:dev
```

* For the microservice in `main`:
```bash 
    $ npm run listen
```

## Usage
* Admin page: http://localhost:3000/admin/products
* Main page: http://localhost:3000/main/

## Using Docker

1. Build the docker images
```bash
$ docker-compose build
```

2. Start the services
```bash
$ docker-compose up
```

## Troubleshooting MySQL Connection Issues

If you encounter difficulties connecting to MySQL, please follow these steps:

1. **Check MySQL Status:**
   - Ensure that MySQL is running by checking the Task Manager on your PC. You can start it using MySQL Workbench or the command line.

2. **Terminate MySQL Process:**
   - If the issue persists, locate `mysqld.exe` in the Task Manager and terminate the process.

3. **Verify Port Availability:**
   - Ensure that the MySQL port is not being used by another application. If it is, free up the port to establish a connection.

By following these steps, you should be able to resolve common MySQL connection issues.
