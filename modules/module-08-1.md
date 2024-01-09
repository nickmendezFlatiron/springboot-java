# <img src="https://github.com/giantmachines/spring-boot-bootcamp/blob/main/giant-machines.png" alt="Giant Machines" width="150" /><br/>React Bootcamp

## Module 8: Authentication

In this module, you will learn about authentication and the tools we use to authenticate a user. Authentication is the process of determining whether a user is truely who they say they are. We usually accomplish this with a username and a password. Once a user is authenticated, we can allow access to data that is private to that user such as financial information, emails, etc. In this modern day and age, there are plenty of hackers and risks involved with managing authentication ourselves. Thus, we rely on 3rd party identity providers to manage authentication and authorization such as Okta, Auth0, etc.

To get a better understanding of how these identity providers are accomplishing secure authentication, you can read about authentication and authorization flows here: https://auth0.com/docs/flows. These flows describe how an identity provider authenticates a user and sends an access token to authorize a user to make API requests on our server.

The key piece of authentication is the access token or JSON Web Tokens (JWT). The JWT is a secure way of transmitting information between parties as a JSON object. More information can be found here: https://medium.com/myplanet-musings/what-is-a-json-web-token-2193f383e963

For this module, you will follow along this tutorial in implementing authorization on your application: https://auth0.com/blog/spring-boot-authorization-tutorial-secure-an-api-java/

[Next Module](module-08-2.md)
