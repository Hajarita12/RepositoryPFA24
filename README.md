# Integrated AHP-TOPSIS and Fuzzy AHP TOPSIS Solution for Multi-Criteria Decision Making

![WhatsApp Image 2024-05-19 à 16 44 40_c5e9563f](https://github.com/Hajarita12/RepositoryPFA24/assets/120518556/b9319c5b-9b18-4faf-9512-058a1b2c063f)

This platform will enable multi-criteria comparison of different project alternatives based on well-established methods such as the Analytic Hierarchy Process (AHP), the Technique for Order of Preference by Similarity to Ideal Solution (TOPSIS), as well as their Fuzzy variants: the Fuzzy Analytic Hierarchy Process (FAHP) and the Fuzzy Technique for Order of Preference by Similarity to Ideal Solution (FTOPSIS).

## Table of Contents


- [Software architecture](#Software-architecture)
- [Docker Image](#Docker-Image)
- [Frontend](#frontend)
- [Backend](#backend)
- [Getting Started](#getting-started)
- [Video Demonstration](#Video-Demonstration)
- [Contributing](#contributing)


## Software architecture
![angular-8-springboot-crud-app](https://github.com/Hajarita12/RepositoryPFA24/assets/120518556/f94a1c60-6b9c-41f3-ad81-99e9e525ac19)

The application architecture uses Angular for the frontend and Spring for the backend, with communication via an HTTP client.
## Docker Image
```sh


version: '3'
services:
  mysql:
    image: mysql:5.7
    ports:
      - "3308:3308"
    environment:
      MYSQL_DATABASE: testt
      MYSQL_ROOT_PASSWORD: root

  backend:
    build:
      context: ./pfa2021 # Utilisez le répertoire actuel où se trouve le Dockerfile du backend
      dockerfile: Dockerfile # Assurez-vous que le Dockerfile est dans le même répertoire que docker-compose.yml
    ports:
      - "8000:8000"
    environment:
      SPRING_DATASOURCE_URL: jdbc:mysql://mysql:3306/testt
      SPRING_DATASOURCE_USERNAME: root
      SPRING_DATASOURCE_PASSWORD: root
    depends_on:
      mysql:
        condition: service_started

  frontend:
    build:
      context: ./argon-design-system-angular-master # Utilise le répertoire actuel où se trouve le Dockerfile du frontend
      dockerfile: DockerFile
    ports:
      - "80:80"
    depends_on:
      backend:
        condition: service_started

  phpmyadmin:
    image: phpmyadmin/phpmyadmin
    ports:
      - "8081:80"
    environment:
      PMA_HOST: mysql
      MYSQL_ROOT_PASSWORD: root
      PMA_PORT: 3306

```
## Frontend

### Technologies Used

- Angular
- HTML
- CSS
- TS


## Backend

### Technologies Used

- Spring Boot
- MySQL

## Backend Project Structure

The backend code follows a modular and organized structure, leveraging the power of Spring Boot for building a robust and scalable application.

### 1. com.example.application

- *Main Application Class:* Application.java serves as the entry point for the Spring Boot application. It includes the main method to start the application.

### 2. com.example.controller

- *Controller Classes:* The controller package contains classes responsible for handling incoming HTTP requests. Each controller class is dedicated to a specific feature or entity, exposing RESTful endpoints. These classes interact with the services to process requests and return appropriate responses.


### 3. com.example.model

- *Entity Classes:* The model package includes classes representing data entities in the application. These classes are annotated with JPA annotations, defining the structure of the database tables. Each entity typically corresponds to a table in the MySQL database.

### 4. com.example.repository

- *Repository Interfaces:* The repository package contains interfaces that extend Spring Data JPA repositories. These interfaces provide methods for basic CRUD operations and are used by services to interact with the database.


### Dependencies

1. *Spring Data JPA:*
   - Purpose: Simplifies data access using JPA in Spring Boot.
2. MySQL Connector/J:
Purpose: JDBC driver for connecting to a MySQL database.


xml
```sh
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-data-jpa</artifactId>
</dependency>
<dependency>
    <groupId>mysql</groupId>
    <artifactId>mysql-connector-java</artifactId>
    <scope>runtime</scope>
</dependency>

```

## Getting Started

Certainly! Here are step-by-step instructions to set up and run your project locally:

### Prerequisites:

1. *Git:*
   - Make sure you have Git installed. If not, download and install it from [git-scm.com](https://git-scm.com/).

2. *XAMPP:*
   - Install XAMPP from [apachefriends.org](https://www.apachefriends.org/).
   - Start the Apache and MySQL servers in XAMPP.
   - Ensure MySQL is using port 3306.

3. *Node Version Manager (NVM):*
   - Install NVM from [github.com/nvm-sh/nvm](https://github.com/nvm-sh/nvm).
   - Use NVM to install Node.js version 14.11.0: nvm install 14.11.0.

### Backend Setup:

1. *Clone the Project:*
   bash
   git clone <repository_url>
   cd <project_folder>
   

2. *Install Backend Dependencies:*
   - Open a terminal in the backend project folder.
   - Run the following commands:
     bash
     mvn clean install
     

3. *Run Backend:*
   - Start your XAMPP Apache and MySQL servers.
   - Run the Spring Boot application. The database and entities will be created automatically.
   - Verify that the backend is running by visiting [http://localhost:8000](http://localhost:8000) in your browser.

### Frontend Setup:

1. *Install Node.js and Angular:*
   - Open a new terminal for the frontend project.
   - Ensure NVM is using Node.js version 14.11.0: nvm use 14.11.0.
   - Install Angular CLI globally: npm install -g @angular/cli.

2. *Install Frontend Dependencies:*
   - Run the following commands in the frontend project folder:
     bash
     npm install
     

   - If you encounter errors during installation, use the following command:
     bash
     npm install --save --legacy-peer-deps
     

3. *Run Frontend:*
   - After installing dependencies, start the Angular development server:
     bash
     ng serve
     

   - Access the frontend at [http://localhost:4200](http://localhost:4200) in your browser.

Now, your full-stack project should be up and running locally. If you encounter any issues during setup, check the console logs for error messages and ensure that all dependencies and prerequisites are correctly installed.

# Video Demonstration

Click the link below to watch a demonstration video:



https://github.com/Hajarita12/RepositoryPFA24/assets/120518556/60b7d1c8-a5bd-47bd-aeaf-68fadc36bb47



## Utilisation 

### Authentification :
- *Pour s'authentifier en tant que décideur  :*
  - Email : kaoutarelazizi0607@gmail.com
  - Mot de passe : kawtar
- *Pour s'authentifier en tant que expert :*
  - Email : hajarmachmoum546@gmail.com
  - Mot de passe : hajar
- *Pour s'authentifier en tant que deuxième expert :*
  - Email : Roaeldhimni@gmail.com
  - Mot de passe : roa





# Contributing

We welcome contributions from everyone, and we appreciate your help to make this project even better! If you would like to contribute, please follow these guidelines:

## Contributors
- Roa Eldhimni ([GitHub](https://github.com/roaeldhimni))
- Kawtar El azizi ([GitHub](https://github.com/kawtare12/))
- Machmoum Hajar ([GitHub](https://github.com/Hajarita12))
- Mohamed Lachgar ([Researchgate](https://www.researchgate.net/profile/Mohamed-Lachgar))
