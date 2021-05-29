# Cognito

## Getting started
- The Amplify Auth category provides an interface for authenticating a user
- The Amplify CLI helps us to create and configure the auth category with an authentication provider

## Goal
- To setup and configure your application with Amplify Auth and go through a simple api to check the current auth session

## Prerequisites
- it work with Android SDK API level 16 with Amplify libraries integrated

## Configure Auth Category
- execute  this line to provisioning auth resources
    - `amplify add auth`
- after that enter the following:
    - ? Do you want to use the default authentication and security configuration?
        - `Default configuration`
    - ? How do you want users to be able to sign in?
        - `Username`
    - ? Do you want to configure advanced settings?
        - `No, I am done.`
    
- then push change to cloud
    - `amplify push`

## Install Amplify Libraries
- to install library write the following
    - `implementation 'com.amplifyframework:aws-auth-cognito:1.17.4'`

## Initialize Amplify Auth
- Add the Auth plugin before calling Amplify.configure
    - Amplify.addPlugin(new AWSCognitoAuthPlugin());
    - Amplify.configure(getApplicationContext());

## Check the current auth session
- We can now check the current auth session.
    - `Amplify.Auth.fetchAuthSession(`
    `result -> Log.i("AmplifyQuickstart", result.toString()),`
    `error -> Log.e("AmplifyQuickstart", error.toString())`
    `);`

- for more details visit [Cognito](https://docs.amplify.aws/lib/auth/getting-started/q/platform/android)