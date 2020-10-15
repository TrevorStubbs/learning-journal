# Readings: Razor Pages

- [Razor Pages](https://docs.microsoft.com/en-us/aspnet/core/razor-pages/?view=aspnetcore-2.2&tabs=visual-studio)
- [Intro to Razor Pages (~60min)](https://www.youtube.com/watch?v=yyBijyCI5Sk)
- [Razor Pages](https://gunnarpeipman.com/aspnet-core-razor-pages/)
- [Getting started with Razor Pages](https://docs.microsoft.com/en-us/aspnet/core/tutorials/razor-pages/razor-pages-start?view=aspnetcore-2.1&tabs=visual-studio)
- [Razor Pages vs MVC](https://jonhilton.net/razor-pages-or-mvc-a-quick-comparison/)


## Razor Pages
- in startup 
``` CSharp
public class Startup
{
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddDbContext<AppDbContext>(options =>
                    options.UseInMemoryDatabase("name"));
        // Includes support for Razor Pages and controllers.
        services.AddMvc();
    }

    public void Configure(IApplicationBuilder app)
    {
        app.UseMvc();
    }
}
```

- Razor pages uses the `@page` diretive. 
    - it handles changes directly withough going through a controller.
        - `@page` must be the first Razor directive on a page.

### Write a basic form
- Data Model

``` csharp
using System.ComponentModel.DataAnnotations;

namespace RazorPagesContacts.Data
{
    public class Customer
    {
        public int Id { get; set; }

        [Required, StringLength(100)]
        public string Name { get; set; }
    }
}
```
- Db Context
``` csharp
using Microsoft.EntityFrameworkCore;

namespace RazorPagesContacts.Data
{
    public class AppDbContext : DbContext
    {
        public AppDbContext(DbContextOptions options)
            : base(options)
        {
        }

        public DbSet<Customer> Customers { get; set; }
    }
}
```
- cshtml file that has the form
``` html
@page
@model RazorPagesContacts.Pages.CreateModel
@addTagHelper *, Microsoft.AspNetCore.Mvc.TagHelpers

<html>
<body>
    <p>
        Enter your name.
    </p>
    <div asp-validation-summary="All"></div>
    <form method="POST">
        <div>Name: <input asp-for="Customer.Name" /></div>
        <input type="submit" />
    </form>
</body>
</html>
```
- This is a model but it has an `IActionResults` method
``` csharp
using System.Threading.Tasks;
using Microsoft.AspNetCore.Mvc;
using Microsoft.AspNetCore.Mvc.RazorPages;
using RazorPagesContacts.Data;

namespace RazorPagesContacts.Pages
{
    public class CreateModel : PageModel // Pages Inherit from the PageModel class
    {
        private readonly AppDbContext _db;

        public CreateModel(AppDbContext db)
        {
            _db = db;
        }

        [BindProperty]
        public Customer Customer { get; set; }
        
        // this looks like a controller method but it's a model
        public async Task<IActionResult> OnPostAsync()
        {
            if (!ModelState.IsValid)
            {
                return Page();
            }

            _db.Customers.Add(Customer);
            await _db.SaveChangesAsync();
            return RedirectToPage("/Index");
        }
    }
}
```
- By convention, the `PageModel` class is called `<PageName>Model`
- The `PageModel` class allows separation of the *logic* of a page from its *presentation*. Allows for:
    - Dependency Injections
    - Unit Testing
- `RedirectToPage()` - Razor Pages helper method that directs the app to the indicated page.
- [BindProperty] - Binding to properties can reduce tha mount of code you have to write.
- Razor Pages bind properties only with non-GET verbs, by default.
- can add a route constraints `@page "{id:int}"`
    - can make the constraint optional with `"{id:int?}"`.

- CRUD for Pages
    - `asp-page-handler`
        - Method signature `On[Verb]Async`
    - The `OnPostDeleteAsync` method:
        - Accepts the id from the query string. If the Index.cshtml page directive contained routing constraint "{id:int?}", id would come from route data. 
        - Queries the database for the customer contact with FindAsync.
        - If the customer contact is found, they're removed from the list of customer contacts. The database is updated.
        - Calls RedirectToPage to redirect to the root Index page (/Index).
### Handle HEAD requests with an OnGet handler fallback
- 'HEAD' requests allow you to retrieve the headers for a specific resource. - Don't require a response body.
- Razor Pages falls back to calling the OnGet handler if no OnHead handler is defined. - Allows for backward compatibility

### Using Layouts, partials, templates and tag helpers
- Add a layout page 'Pages/Shared/_Layout.cshtml'
    - build out your html but for the main add `@RenderBody()`
- in 'Pages/_ViewStart.cshtml`
``` csharp
@{
    Layout = "_Layout";
}
```
- Pages are meant to rely on folder hierarchy, not path conventions.

### ViewData attribute
- Data can be passed to a page with `ViewDataAttribute`.
``` csharp
[ViewData]
public string Title { get; } = "About";
```
``` CSHTML
<h1>@Model.Title</h1>

<title>@ViewData["Title"] - WebApplication</title>
```

### DataTemp
- The properties with this attribute has it's data stored until it's read.
``` CSharp
[TempData]
public string Message { get; set; }
```
### Custom Routes
### Configuration and settings
- Startup.cs
``` csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddMvc()
        .AddRazorPagesOptions(options =>
        {
            options.RootDirectory = "/MyPages";
            options.Conventions.AuthorizeFolder("/MyPages/Admin");
        });
}
```
### Specify that Razor Pages are at the content root
``` csharp
services.AddMvc()
    .AddRazorPagesOptions(options =>
    {
        ...
    })
    .WithRazorPagesAtContentRoot();
```
### Specify that Razor Pages are at a custom root directory
``` csharp
services.AddMvc()
    .AddRazorPagesOptions(options =>
    {
        ...
    })
    .WithRazorPagesRoot("/path/to/razor/pages");
```
### Razor Pages with .ASP.NET Core 2

