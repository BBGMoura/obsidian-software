To understand Spring Security, three important concepts need to be understood:
- Authentication
- Authorisation 
- Servlet Filters

### 1. Authentication

You need your users to authenticate, to verify who the use claims to be. Typically done with username and password.

### 2. Authorisation

Most applications have the concept of permissions (or roles). A user might have access to the public-facing frontend of your website but the admin can access the admin area.

Both users need to login, but authentication doesn't say anything about their permission. Hence, you need to check permission of the user, i.e authorise the user.

### 3. Servlet Filters

Why use Servlet Filters?

Basically any Spring Web application is just one servlet: Spring's Dispatcher Servlet, that redirects incoming HTTP requests to your @Controllers or @RestControllers.

There is no security hardcoded into that DispatcherServlet. Optimally, the authentication and authorisation should be done before a request hits your @Controller.

To do this, you put **filters** in front of servlets. ![[Filter.png]]

#### FilterChains

There are several filters, with different purposes which make up a FilterChain. For example, an incoming HTTP request would go through:

- LoginMethodFilter
- AuthenticationFilter
- AuthorizationFilter

Before hitting the servlet.

This concept is called FilterChain. With this, you can handle every authentication or authorisation problem there is in your application, without needing to change your actual application implementation (Controllers). 

