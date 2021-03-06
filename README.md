# Cinema app 
Basic implementation of a cinema with all its functions. Introduced authorization and authentication. 
It implements such principles as SOLID, DI, REST. 
All incoming and outgoing data are converted to json format, also implemented global exception handler.

## Technologies
* Java 11
* MySQL
* Hibernate
* Spring (Core, WEB, Security)
* Apache Tomcat (to run app locally)
* Maven Checkstyle Plugin

## Features
The program has 2 levels of access `admin` and `user`, depending on the role you can do different actions.

#### Users and admins have access to:
`GET: /cinema-halls` - display a list of cinema halls <br>
`GET: /movies` - display a list of movies <br>
`GET: /movie-sessions/available` -  display a list of all available movie sessions by movie id and date <br>

#### Admins have access to:
`POST: /cinema-halls` — add new cinema hall <br>
`POST: /movies` — add new movie <br>
`POST: /movie-sessions` — add new movie session <br>
`PUT: /movie-sessions/{id}` — update movie session by id <br>
`DELETE: /movie-sessions/{id}` — delete movie session by id <br>
`GET: /users/by-email` — find user by email <br>

#### Users have access to: 
`GET: /orders` - display a list of user's orders <br>
`GET: /shopping-carts/by-user` - display user's shopping cart <br>
`POST: /orders/complete` - complete the current order <br>
`PUT: /shopping-carts/movie-sessions` - add movie session to the shopping cart <br> 

## Installation and running
To run this project you will need to do these steps:
 * Install MySQL and Apache Tomcat
 * Create empty database.
 * Clone this project.
 * Edit database connection information in db.properties in resources folder:<br>
   `db.driver=YOUR_DRIVER`<br>
   `db.url=YOUR_DATABASE_URL`<br>
   `db.user=YOUR_USERNAME`<br>
   `db.password=YOUR_PASSWORD`<br>
 * Add Tomcat to running configuration of your project and use "/" as your Tomcat application context.
 * There is one already registered ADMIN user with username `admin@i.ua` and password `admin123` fill free to use it, or register a new user using Postman: <br>
   `POST: /register {"email" : "email@gmail.com", "password" : "password", "repeatPassword" : "password"}` 
