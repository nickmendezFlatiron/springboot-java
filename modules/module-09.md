# <img src="https://github.com/giantmachines/spring-boot-bootcamp/blob/main/giant-machines.png" alt="Giant Machines" width="150" /><br/>React Bootcamp

## Module 9: Permanent Persistence (Local)

Welcome to the last module! To recap, you successfully set up your Java tools, learned Java fundamentals, created a Spring Boot server, added error handling, created unit tests, implemented h2 persistence, integrated a 3rd party API, and added authentication + authorization to your application. Amazing work, congratulations on your achievements!

In this module, we will want to ensure our data is persisted. Since H2 is an in-memory database, it will not persist the data when the server is terminated or restarted. For this, we will use a popular persistent relational database called Postgres. 

First, let’s install and configure Postgres on our machine. Follow the instructions here: https://postgresapp.com/. Once that is completed we can create a database called ‘library’. You can do this through SQL commands (psql) or through a Graphical User Interface (GUI) like Postico.

Now, we will need to connect our application to our newly created database. Given that our database exists only on our machine/locally, we should create a separate file called `application-local.properties` to handle local development properties. In the same directory as  `application.properties`, create a new `application-local.properties` file. 

We will be using an Object Relational Mapping (ORM) framework called Hibernate. This framework was added with our Spring Data JPA dependency. Configure the `application-local.properties` to connect with your database. Use this as a guide: https://stackabuse.com/implementing-hibernate-with-spring-boot-and-postgresql/.

We need to ensure that we are using the correct Spring Boot Profile, in our case local. We will need specify this in our Intellij configurations: https://stackoverflow.com/questions/39738901/how-do-i-activate-a-spring-boot-profile-when-running-from-intellij

Lastly, we will need to switch all of our H2 persistence to our newly created Hibernate/Postgres database.

Congratulations you finished the Spring Boot Boot Camp! You are on your way to becoming a successful engineer here at Giant Machines! 

## Wrapping Up
