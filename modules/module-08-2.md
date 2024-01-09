# <img src="https://github.com/giantmachines/spring-boot-bootcamp/blob/main/giant-machines.png" alt="Giant Machines" width="150" /><br/>React Bootcamp

## Module 8.5: Authorization

In many applications, we have user roles that dictate what users can do. For example, our library app should have an admin that can add and delete books in the database but should not allow a user to do so. The way we can accomplish this is to add roles to all our users and grant permission. This feature is called authorization. In this module, we will add authorization to our application.

Let’s keep our roles simple. We will have a role of an admin and a role of a user. To get started, we will need to keep track of which users have admin vs user roles. In the User model, we can add a boolean ‘is_admin’ or. for an advanced implementation, we could create a field called role with an enumerator of ‘admin’ or ‘user’.

Now that the user has a role, we will need to modify our services to check the user role before allowing a user to create, update or delete a book. We can simply look up the user each time in the database and verify that the user is an admin. For an advanced approach, we can add a @PreAuthorize annotation that requires admin roles on specific endpoints. The @PreAuthorize annotation would verify the user role via the JWT so you would have to create an admin group in your identity provider (Auth0 or okta). Then, you would decode JWT with the JWTAuthorizationFileter to process the group the user belongs to. For this approach you can use this as a guide: https://www.baeldung.com/spring-security-method-security

Lastly, let’s implement error handling if the user is unauthorized to make a request. What HTTP status code should be returned from the server?

[Next Module](module-08-2.md)
