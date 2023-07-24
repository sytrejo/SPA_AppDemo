# SPA_AppDemo

1. Which library do we use for routing in an Angular application?

Answer:
    - You can use the Angular Router Library to handle routing in an Angular application. It is a powerful tool that allows you to define routes, navigate between views, and pass data between views, and pass data between components.


2. How do we add routing capabilities in an HTML anchor element?

Answer:
    - To add routing capabilities to an HTML anchor element in an Angular application, you can use the routerLink directive.
    
    For example, if you want to create a link to the home route, you can add the following code to your HTML file:

    <a routerLink="/">Home</a>

    This will generate a link that navigates to the home route when clicked. You can replace the / with the path of the route you want to navigate to. 


3. Which Angular pipe do we use for date formatting?

Answer:

    You can use the DatePipe for date formatting in an ANgular application. The DatePipe is a built-in pipe in Angular that provides a way to format dates according to the locale rules.  To use the DatePipe, you need to import it from the @angular/common module and add it to the providers array of your module. Then, you can use it in your component's template like this:

    <p>Today is {{ today | date }}</p>

    In this example, today is a Date object and the date pipe formats it according to the default local rules. You can also pass a format string to the pipe to customize the date format. 


4. What is the purpose of the assets folder in an Angular CLI application?



5. Which route property do we use for lazily loading a module?



6. Which Angular CLI command we use for installing Scully?


7. Which service do we use for fetching Scully routes?


8. What is the property binding?


9. Which Angular directive do we use for iterating over an array in HTML?


10. What is the difference between a standard Angular application and a Scully one?
