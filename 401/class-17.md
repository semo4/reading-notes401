# Spring Authorization
![images](https://i.morioh.com/200527/bc9baa29.jpg)

- This guide shows you how to build a sample app doing various things with «social login» using OAuth 2.0 and Spring Boot.
The samples are all single-page apps using Spring Boot and Spring Security on the back end. But, the changes needed to convert to a different JavaScript framework or to use server-side rendering would be minimal.

- There are several samples building on each other, adding new features at each step:

    1. **simple**: a very basic static app with just a home page and unconditional login via Spring Boot’s OAuth 2.0 configuration properties (if you visit the home page, you will be automatically redirected to GitHub).

    2. **click**: adds an explicit link that the user has to click to login.

    3. **logout**: adds a logout link as well for authenticated users.

    4. **two-providers**: adds a second login provider so the user can choose on the home page which one to use.

    5. **custom-error**: adds an error message for unauthenticated users, and a custom authentication based on GitHub’s API

- Each app can be imported into an IDE. They all come up with a home page on http://localhost:8080 .

## Single Sign On With GitHub
- Creating a New Project
- Add a Home Page

## Securing the Application with GitHub and Spring Security
- To make the application secure, you can simply add Spring Security as a dependency.

- Next, you need to configure your app to use GitHub as the authentication provider. To achieve this, do the following:

#### Add a New GitHub App
- Select «New OAuth App» and then the «Register a new OAuth application» page is presented. The OAuth redirect URI is the path in the application that the end-user’s user-agent is redirected back to after they have authenticated with GitHub and have granted access to the application on the Authorize application page.

#### Configure application.yml
#### Boot Up the Application
- With that change, you can run your app again and visit the home page at http://localhost:8080. Now, instead of the home page, you should be redirected to login with GitHub. If you stay logged in to GitHub, you won’t have to re-authenticate with this local app, even if you open it in a fresh browser with no cookies and no cached data.
It’s safe to grant access to this sample since only the app running locally can use the tokens and the scope it asks for is limited.


## Add a Logout Button
- we modify the click app we built by adding a button that allows the user to log out of the app.

## Adding a Logout Endpoint
- The /logout endpoint requires us to POST to it, and to protect the user from Cross Site Request Forgery , it requires a token to be included in the request. The value of the token is linked to the current session, which is what provides the protection, so we need a way to get that data into our JavaScript app.

## Login with GitHub
- you’ll modify the logout app you built already, adding a sticker page so that the end-user can choose between multiple sets of credentials.

#### Initial setup
- To use Google’s OAuth 2.0 authentication system for login, you must set up a project in the Google API Console to obtain OAuth 2.0 credentials.

#### Setting the redirect URI
- you’ll need to supply a redirect URI, as you did for GitHub earlier.

#### Adding the Client Registration
- Then, you need to configure the client to point Google. Because Spring Security is built with multiple clients in mind.

#### How to Add a Local User Database
- Many applications need to hold data about their users locally, even if authentication is delegated to an external provider. We don’t show the code here, but it is easy to do in two steps.

1. Choose a backend for your database, and set up some repositories (using Spring Data, say) for a custom User object that suits your needs and can be populated, fully or partially, from external authentication.

2. Implement and expose OAuth2UserService to call the Authorization Server as well as your database. Your implementation can delegate to the default implementation, which will do the heavy lifting of calling the Authorization Server. Your implementation should return something that extends your custom User object and implements OAuth2User.

## Adding an Error Page for Unauthenticated Users
- you’ll modify the two-providers app you built earlier to give some feedback to users that cannot authenticate. At the same time you’ll extend the authentication logic to include a rule that only allows users if they belong to a specific GitHub organization.