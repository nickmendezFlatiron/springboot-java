# <img src="https://github.com/giantmachines/spring-boot-bootcamp/blob/main/giant-machines.png" alt="Giant Machines" width="150" /><br/>React Bootcamp

## Module 5: H2 Persistence

At Giant Machines, we often use a relational database to store and manage data. In this module, we will integrate an in-memory relational database called H2. 

To setup our H2 database, we need to add our configurations. We need to add the spring.datasource.url, spring.datasource.driverClassName, spring.datasource.username, spring.datasource.password, and spring.jpa.database-platform properties in our `application.properties`. For more information about these properties visit: https://docs.spring.io/spring-boot/docs/current/reference/html/appendix-application-properties.html#spring.datasource.url

Next, we will add `@Entity` to our Book model. The `@Entity` is a Java Persistence API (JPA) annotation that indicates a class/Model is correlated with a table in the database. For details here: https://www.baeldung.com/jpa-entities

We will need to create a repository interface that allows us to fetch data from our database. The interface is abstract and the actual implementation is handled for us by Spring Boot. In the java > com directory we will create a new package called `repository`. Inside our repository package we will create an interface called `BookRepository`. Add the `@Repository` annotation to the interface to denote that this is a repository. Also, have the interface extend from `CrudRepository` so that we have access to all the JPA repository methods. We can add the methods that we need to communicate with our database here. For example, if we need to fetch all books, we would add the JPA method called `findAll()` that takes in the query parameters as arguments. You will need to implement all the CRUD functionality for our library app (get all books, get book by id, create a book, etc.) Follow this for query options: https://www.baeldung.com/spring-data-jpa-query
For more guidance/step by step implementation visit here: https://spring.io/blog/2011/02/10/getting-started-with-spring-data-jpa

Now that we have our repository methods implemented, we will need to integrate it with our services. Let’s go into our BookService and update our data persistence to use the newly created BookRepository methods. 

One concept to be aware of is the Optional<T> container object. For certain repository calls such as findById, the data might not exist and would return null. This could inevitably cause an unchecked (or unexpected) NullPointerException. To combat this the Optional<T> was introduced in Java 8. Put simply, an Optional is a container that could either contain the data we want or null. The pattern to use for Optionals is to call the method `.findById() and chain `.orElseThrow()` at the end. 

For example, bookRepository.findById(bookId).orElseThrow(() -> new EntityNotFoundException(“Book not found”)). What we are doing here is first calling the findById method. If that repository call is successful and contains data, we will return the data. Otherwise, if the container is null we will throw a checked exception. A checked expectation is simply a scenario that we are expecting could happen outside of the immediate control of the application. In our case, we are expecting that there is a possibility where findById() does not return anything because a book with that id may not exist in our database. Given that this is outside of our programmatic control, it needs to be handled with a checked expectation which is generally related to resource errors. On the other hand, an unchecked exception is not checked by the Java compiler and is not forced to be handled. Unchecked exceptions usually signify a programming error. For more information about checked vs unchecked exceptions: https://howtodoinjava.com/java/exception-handling/checked-vs-unchecked-exceptions-in-java/
More information about optionals: https://codeflex.co/java-optional-no-more-nullpointerexception/

Lastly, we are going to update our unit tests using a framework called Mockito. We want to ensure our H2 repository call is integrating correctly with our service. However, we are not interested in testing the H2 repository call itself. Testing the H2 repository call would be more of an integration test, which we are not interested in right now. Instead, we mock the repository call and so that our unit test focuses on the service functionality. For example, given there are 2 books in the mock database, we would expect a ‘getAllBooks()’ function to return an array of 2 books. Follow this tutorial on how to integrate Mockito into our unit tests: https://www.vogella.com/tutorials/Mockito/article.html

[Next Module](module-06.md)