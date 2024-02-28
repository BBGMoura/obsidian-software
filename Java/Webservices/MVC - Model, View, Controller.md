Design patterns is a way of organising things which developer should follow to make a big and complex application in a simple, repeatable form. MVC allows for scalable applications with loose coupling.

![[MVC.png]]

## Controller
- Handles request flow
- should not have lots of business logic - it navigates the request to the right layer
- receives data from model and sends to view
## Model
- Receives the request from controller and handles the data logic
- communicates with database
- performs validation
- handles data logic
- sends data back to controller
## View
- Handles how to show the data which is received from the controller
- dynamically renders the data
- returns data to controller

**Model and view never interact. Controller interacts with both.**

- [p] This is good as each layer has their **own role**. It has a single principle. Which makes it better for complexity and scalability. Regardless of complexity!

Note: in modern applications, there are no views as we are not using monolithic applications. This is because we have an application who knows how to present our response using HTML, JavaScript, Vuew.js, React.js and etc.

![[Modern MVC.png]]