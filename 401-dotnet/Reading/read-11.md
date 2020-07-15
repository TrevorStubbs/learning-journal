# Read: MVC

- [READ: Intro to MVC](https://docs.microsoft.com/en-us/aspnet/core/mvc/overview?view=aspnetcore-2.2)
- [WATCH: Videos 1, 2, 3](https://channel9.msdn.com/Series/Introduction-to-ASP.NET-Core-with-Visual-Studio-2017?l=LU6ABeE6C_8206218965)
- [SKIM: MVC Tutorial](https://docs.microsoft.com/en-us/aspnet/core/tutorials/first-mvc-app/?view=aspnetcore-3.1)

## Model View Controller
- Model-View-Controller
    - Design pattern that separates an application into 3 main groups
- Helps to achieve separation of concerns.
- user makes requests to a controller
    - the controller will talk to the model and choose what view to display
- makes it easier to code debug and test.

### Model Responsibilities
- Model represents the sate of the application. 
- Business logic should be encapsulated in the model.
    - ViewModel Types
    - The controller creates and populates these ViewModel instances from the model

### View Responsibilities
- Presenting content through the user interface.
- Use Razor view engine to embed .NET code into HTML
- minimal logic within the view. 
    - if needed then use View Component.

### Controller Responsibilities
- The components that handle user interaction, work with the model and select a view to render.
- The controller is the initial entry point.
- Should not be overly complicated.
    - push business logic out of the controller and into the domain model

## ASP.NET Core MVC
### Routing 
- Convention-based routing
> `routes.MapRoute(name: "Default", template: "{controller=Home}/{action=Index}/{id?}");`
- Attribute routing
``` C#
[Route("api/[controller]")]
public class ProductsController : Controller
{
    [HttpGet("{id}")]
    public IActionResults GetProduct(int id)
    {
        // some logic
    }
}
```

### Model binding
- converts client request data into objects.

### Model Validation
- decorating model objects with data annotation validation attributes.

### Dependency injection
- `@inject`

### Filters
- help encapsulate cross-cutting concerns.

### Areas
- Help partition large app into smaller functional groupings. 

### Web APIs
- build your own API

### Testability
- well-suited for unit testing.

### Razor View Engine
- used to dynamically generate web content on the browser.

### Strongly Typed Views
- Views can be strongly typed

### Tag Helpers
- Enable server side code to participate in creating and rendering HTML elements in Razor files.

### View Components
- package rendering logic and reuse it.

### Video Notes
- `loggerFactory.AddConsole();`
- IIS Express - 
    - production and development separation
    - wwwroot - public folder

- Add a controller  
    - Controllers>Add>Controller
    - MVC Controller Class
``` C#
using Microsoft.AspNetCore.Mvc;
using System.Text.Encodings.Web;

namespace MvcMovie.Controllers
{
    public class HelloWorldController : Controller
    {
        // 
        // GET: /HelloWorld/

        public string Index()
        {
            return "This is my default action...";
        }

        // 
        // GET: /HelloWorld/Welcome/ 

        public string Welcome()
        {
            return "This is the Welcome action method...";
        }
    }
}
```
- Add a view 
    - Add > New folder
        - Add New Item - MvcMovie - select Razor View - Index.schtml
- work with a model