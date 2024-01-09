# <img src="https://github.com/giantmachines/spring-boot-bootcamp/blob/main/giant-machines.png" alt="Giant Machines" width="150" /><br/>React Bootcamp

## Module 4: Error Handling

Congrats on creating your first Spring Boot application! In this module we’ll be learning about ResponseEntity, Dependency Injection, and a consistent pattern for handling errors.

The Spring Boot ResponseEntity serves as a pattern for handling all RESTful responses. In order to keep our application consistent throughout we leverage this class. Create a ResponseUtility class inside the /utils folder, which will create the ResponseEntities for our entire application. Start off with buildOkResponse and buildCreatedResponse. [TODO]

Next we want to refactor our controllers to decouple the CRUD logic for our books. Create a  BookService class inside the /service folder which will include all CRUD logic. You’ll need the @Service annotation for this. [TODO: add short blurb for what this service is doing and how it related to DI]

Finally lets add in the global exception handlings for Spring Boot. You’ll want to implement a general Error class (ApiError) which will be used as a base for all errors within the application. To implement this throughout, extend the ResponseEntityExceptionHandler class. Extend for bad requests and not found requests. [Hint: Read into @ControllerAdvice or @RestControllerAdvice and the Spring Boot “Advice” concept]  Add the necessary ResponseEntity builders in the ResponseUtility file.

[Next Module](module-04-2.md)
