# <img src="https://github.com/giantmachines/spring-boot-bootcamp/blob/main/giant-machines.png" alt="Giant Machines" width="150" /><br/>React Bootcamp

## Module 4.5: Unit Testing

When doing Agile development, we are merging code often and integrating other engineers' work. As a result, this can lead to some instability in our application. We as engineers need to do our best to prevent these issues from arising and to catch them before they go out into the real world. We ensure quality products through a QA process and testing: integration, end-to-end, unit, etc. In this module we will learn how to do unit testing. A unit test helps ensure individual units of code are working as expected. For example a service method, a component, etc. In this module we will create a unit test for our BookService.

The Spring Boot Initializer should have generated an example test that we can add onto. In the test > java > com > example > demo (or the project name), open the DemoApplicationTests file.
We can add a single unit test here that validates the create() method (or the name of the method that you used to create a book) of your ‘BookService’. You can test using ‘mvn test’  in the command line. Follow our Giant Machines github as a guideline: https://github.com/giantmachines/playbook/blob/main/platform/testing.md

[Next Module](module-05.md)
