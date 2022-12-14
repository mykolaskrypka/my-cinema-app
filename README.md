# Cinema App
***
### Functionality:
The application you are considering has the basic functionality required by the cinema service.
Operation with the application begins with registration using an email and a password (the User role is automatically assigned, and your own shopping cart is created). After which you have the opportunity to:
- get a list of movies from the DB and information about them (GET-request, endpoint: "/movies");
- view the list of cinema-halls with a description of each and the number of seats (GET-request, endpoint: "/cinema-halls");
- get available sessions by the movieId of the desired movie for a certain date (GET-request, endpoint: "/movies-sessions/available");
- add a ticket for the selected session to the cart (POST-request, endpoint: "/shopping-card/movies-sessions", the request body must contain a variable with the name "movieSessionId" and its value)
- if there are tickets in the cart, the order is confirmed by sending a Post-request to the "/orders/complete" endpoint, after which the order is created and the cart is cleared.

<br>A user with the role of `ADMIN` is created not through registration, but with the help of the Datainitializer class, where the data is registered when the program is launched.
<br>You can check the functionality of the application manually using your browser - this applies to GET-requests.
For testing POST, PUT, DELETE requests, there are a number of applications, among which I chose POSTMAN:
example of a POST-request to add a movie-session to the shopping-cart:
- endpoint: `"shopping-cart/movie-sessions"`
- request body: `{"movieSessionId":1}`
***
### Structure
The general structure of the application is divided into tiers, each of which has its own responsibility:
- The DAO tier is intended for direct addition, deletion and updating of data in the database.
- Service - this tier is intended for data manipulation and implementation of the logic of our program.
- Controller - interaction with the user. this tier is intended for direct processing of requests from the client and return of results.
Instead of models, controllers use dto's, which are (de)serialized using Jackson ObjectMapper to JSON-format.
***
### Technologies used:
- Spring (modules like: ORM, Web MVC, Bean, Core, Context, Security) 
- Jackson
- Hibernate
- MySQL, MySQL Workbench
- Tomcat
- To encode the password is used BCryptPasswordEncoder 
***
### Getting started:
Before you begin, make sure you have all the below installed:
- IntelliJ IDEA Ultimate
- Tomcat
- MySQl (as DB), MySQL Workbench

Next steps:
Fork and clone this project.
<br>Set up the configuration for Tomcat.
<br>To connect to database in your application you need change configuration information in the file from /src/main/resources/db.properties to the ones you specified when installing MySQL
Finally you can start the application.
