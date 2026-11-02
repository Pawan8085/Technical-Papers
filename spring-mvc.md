
# Spring MVC

## What is Spring MVC?

- Spring MVC is a web framework provided by Spring to build web applications.
- It follows the **Model-View-Controller (MVC)** design pattern.
- It separates application logic, data, and user interface.

## Model, View, and Controller

### Model
- Holds the application data.
- Passes data between the controller and the view.

### View
- Represents the user interface.
- Displays data to the user.
- Examples: HTML, JSP, Thymeleaf templates.

### Controller
- Handles incoming HTTP requests.
- Calls the required business logic.
- Returns a view name or response data.

##  DispatcherServlet

- DispatcherServlet is the front controller of Spring MVC.
- It receives incoming HTTP requests.
- It forwards requests to the appropriate controller.
- It coordinates the request processing flow.

##  ViewResolver

- ViewResolver is responsible for finding the actual view based on the view name returned by the controller.
- It maps a logical view name to a view template.

Example:

```java
return "home";
```

The ViewResolver finds the corresponding `home` view, such as `home.jsp` or a Thymeleaf template.

## Spring MVC Flow Diagram

```text
        Client / Browser
               |
               | HTTP Request
               v
       DispatcherServlet
               |
               v
       HandlerMapping
               |
               v
          Controller
               |
               v
        Service Layer
               |
               v
        Repository Layer
               |
               v
           Database
               |
               v
          Controller
               |
               | Model + View Name
               v
          ViewResolver
               |
               v
             View
               |
               | HTML Response
               v
        DispatcherServlet
               |
               v
        Client / Browser
```

### Flow Explanation

1. The client sends an HTTP request.
2. DispatcherServlet receives the request.
3. HandlerMapping identifies the appropriate controller.
4. The controller processes the request and calls the required service.
5. The service interacts with the repository to access data.
6. The controller returns the model and view name.
7. ViewResolver finds the corresponding view.
8. The view is rendered and the response is sent back to the client.
