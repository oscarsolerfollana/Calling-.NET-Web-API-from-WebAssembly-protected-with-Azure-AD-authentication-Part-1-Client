# Calling .NET Web API from WebAssembly, protected with Azure AD authentication -Part 1- (Client)

I'd like to share an easy solution to connect a Blazor client to a .NET Web API, and how to configure Azure AD authentication.


## Project creation

First of all, we will create a WebAssembly project template and we will compile and run the project in order to discover what port is using our IIS Express to run the project in localhost.

## Azure Active Directory configuration

Inside Azure Portal, we go to Azure Active Directory, App registrations,and here we are creating two applications: One for the client and one for the API.

### Client app

We create a new registration. We write a name, we configure the app as a Single-tenant. Once created, we go the app, we click on **Expose an API**, we add a scope and we fill the fields as follows:
<br/><br/>
![alt text](https://github.com/oscarsolerfollana/Calling-.NET-Web-API-from-WebAssembly-protected-with-Azure-AD-authentication-Part-1-Client/blob/main/ReadmeContent/exposeAPI.PNG?raw=true)
<br/><br/>
Then we click Add scope.

### API app

One more time, we create a new app registration. After writing a name for our app, and configuring the app as a Single-tenant, we add a Single-page application type Redirect URI, with the next value: ```https://localhost:[port]/authentication/login-callback```, where the [port] will be the port on which is running the WebAssembly application.
We click on API permissions -> Add a permission -> My APIs, we click on our API registered app name, we select API.Access and we click on Add permissions.
<br/><br/>
![alt text](https://github.com/oscarsolerfollana/Calling-.NET-Web-API-from-WebAssembly-protected-with-Azure-AD-authentication-Part-1-Client/blob/main/ReadmeContent/permissions.PNG?raw=true)
<br/><br/>
Then we click on **Grant admin consent for...** to grant permissions.




## Project configuration

We will add the nuget **Microsoft.Authentication.WebAssembly.Msal** to the project.

(Under construction...)
