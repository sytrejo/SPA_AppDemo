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

Answer:
    The assets folder in an Angular CLI application is used to store static files such as images, fonts, and other resources that are used by your application. 

    When you build your application, the contents of the assets folder are copied to the dist folder along with the complired JavaScript and CSS files. This makes it easy to reference these files in your application using relative paths. 

    You can organize the contents of the assets folder into subdirectories to keep your project organized. For example, you might create an images subdirectory to store all of your image files, and a fonts subdirectory to store all of your font files. 

    To reference a file in the assets folder from your application, you can use a relative path like this: 

    <img src="assets/images/logo.png" alt="Logo">

    This will load the logo.png file from the images subdirecotry of the assets folder. 


5. Which route property do we use for lazily loading a module?

Answer:
    To lazily load a module in an Angular application, you can use the loadChildren property of a route. 

    The loadChildren property specifies the path to the module that should be lazily loaded. For example, if you have a customers module that you want to lazily load, you can define a route like this:

        {
        path: 'customers',
        loadChildren: () => import('./customers/customers.module').then(m => m.CustomersModule)
        }
    
    In this example, the loadchildren property specifies the path to the customers module and uses the import() function to load it asynchronously, the then() method is used to return the CustomersModule from the loaded module. 

    When the user navigates to the customers route, the CustomersModule is loaded lazily, which can improve the performcance of your application by reducing the initial bundle size. 

6. Which Angular CLI command we use for installing Scully?

Answer:
    To install Scully in an Angular CLI project, you can use the following command 
        ng add @scullyio/init
    This command will install the necessary dependencies and configure your project to use Scully.

    After the installation is complete, you can use the scully command to generate static files for your application. For example, you can run the following command to generate the static files for your application. For example, you can run the following command to generate the static files
        npm run scully


7. Which service do we use for fetching Scully routes?

Answer:
    To fetch Scully routes in an Angular application, you can use the ScullyRoutesServices.

    The ScullyRoutesService is a built-in service in Scully that provides a way to fetch the list of routes that have been pre-rendered by Scully. 

    To use the ScullyRoutesSerivice, you need to import it from the @scullyio/ng-lib module and inject it into your component or service. Then, you can use the getAll() method of the service to fetch the list of pre-rendered routes. For example:

    import { Component } from '@angular/core';
    import { ScullyRoutesService } from '@scullyio/ng-lib';

    @Component({
    selector: 'app-root',
    template: `
        <ul>
        <li *ngFor="let route of routes">
            <a [routerLink]="route.route">{{ route.title }}</a>
        </li>
        </ul>
    `
    })
    export class AppComponent {
    routes = [];

    constructor(private scully: ScullyRoutesService) {}

    ngOnInit() {
        this.scully.getAll().subscribe(routes => {
        this.routes = routes;
        });
    }
    }

    In this example, the AppComponent fetches the list of pre-rendered routes using the ScullyRoutesService and displays them in a list. You can customize the display of the routes based on your application's needs

8. What is the property binding?

Answer:
    Property binding is a way to set the value of an HTML element's property or attribute in an Angular application. 

    In Angular, you can use property binding to set the value of a property or attribute using the square bracket syntax. For example, to set the src attribute of an img element, you can use the following code:

    <img [src]="imageUrl" alt="Image">

    In this example, imageURL is a property of the component that contains the URL of the image. The property binding sets the value of the src attribute to the value of the imageURL property. 

    Property binding can also be used to set the value of a property of a directive. For example, to set the ngClass directive's class property, you can use the following code: 

    <div [ngClass]="{ 'highlight': isHighlighted }">Content</div>

    In this example, isHighlighted is a property of the component that determines whether the highlight class should be applied to the div element. The property binding sets the value of the class property of the ngClass directive to an object that maps the highlight class to the value of the isHiglighted property.


9. Which Angular directive do we use for iterating over an array in HTML?

    Answer:

    To iterate over an array in HTML in an Angular application, you can use the ngFor directive.

    The ngFor directive is a structural directive that repeats a portion of the HTML for each item in an array. For example, to display a list of items from an array, you can use the following code:

    <ul>
    <li *ngFor="let item of items">{{ item }}</li>
    </ul>

    In this example, items is an array of items that you want to display in a list. The ngFor directive repeats the li element for each item in the array and sets the content of the li element to the value of the current item. 

    You can also use the ngFor directive with an object to iterate over its properties. For example, to display a list of key-value pairs from an object, you can use the following code:

    <ul>
    <li *ngFor="let key of Object.keys(obj)">
        {{ key }}: {{ obj[key] }}
    </li>
    </ul>

    In this example, obj is an object that you want to display as a list of key-value pairs. The ngFor directive iterates over the keys of the object using the Object.keys() function and sets the content of the li element to the key and value of each property. 


10. What is the difference between a standard Angular application and a Scully one?

Answer:

    The main difference between a standard Angular application and a scully one is that Scully generates static HTML files for the application's routes at build time, while a standard Angular application generates dynamic HTML content at runtime. 

    In a standard Angular application, the server sends the compiled JavaScript and CSS files to the browser, and the browser renders the HTML content dynamically based on the application's logic. This means that the server needs to run the Angular application and generate the HTML content for each request. 

    In contrast, a Scully application generates static HTML files for each route of the application during the build process. When a user requests a page, the server serves the pre-generated static HTML file instead of running the Angular application. This can improve the performance and SEO of the application by reducing the load on the server and improving the page load times. 

    Another difference between a standard Angular application and a Scully one is that Scully provides additional tools and libraries for generating and optimizing static content. For example, Scully provides plugins for generating sitemaps, optimizing images, and pre-rendering dynamic content. 

    
