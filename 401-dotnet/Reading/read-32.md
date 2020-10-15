# Read: Class 32 - View Components

- [Intro to View Components](https://docs.microsoft.com/en-us/aspnet/core/mvc/views/view-components?view=aspnetcore-2.1)
- [View Components](https://mariusschulz.com/blog/view-components-in-asp-net-core-mvc)

## View Components in ASP.NET Core
- Components are similar to partial views. 
    - No Model binding.
- A view competent:
    - Renders a chunk rather than a whole response
    - Includes the same separation-of-concerns and testability benefit found between a controller and view.
    - Can have parameters and business logic.
    - Is typically invoked from a layout page.
- View components are intended anywhere you have reusable rendering logic that's too complicated for a partial view. For example:
    - Dynamic navigation menus
    - Tag cloud (db queries)
    - Login panel
    - Shopping cart
    - Recently published articles
    - Sidebar content on a typical blog
    - a login panel that would be rendered on every page and show either the links to logout or login.

### Creating a View Component
- A View Component class can be created by:
    - Deriving from the ViewComponent base class
    - Using the [ViewComponent] attribute or deriving from a class with the [ViewComponent] attribute.
    - Creating a class where the name ends with the suffix `ViewComponent`
- View components dont take part of the controller lifecycle.

### View Component methods
- `InvokeAsync` which returns `Task<IViewComponentResult>`

- A view component never directly handles a request.

### View discovery path
- /Views/{Controller Name}/Components/{View Component Name}/{View Name}
- /Views/Shared/Components/{View Component Name}/{View Name}
- /Pages/Shared/Components/{View Component Name}/{View Name}

### Invoking a component
``` HTML
@await Component.InvokeAsync("Name of view component", {Anonymous Type Containing Parameters})
```
- like:
``` HTML
@await Component.InvokeAsync("PriorityList", new { maxPriority = 4, isDone = true })
```

### Tag Helper
- `@addTagHelper *, MyWebApp`

### From a controller
``` CSharp
public IActionResult IndexVC()
{
    return ViewComponent("PriorityList", new { maxPriority = 3, isDone = false });
}
```

## View Components in ASP.NET
- Define a ViewComponent class
- in CSHTML
    - @Component.Invoke("[NameOfComponent]")
- can call `@Navigation.ViewModel` in cshtml
- View model can have "Dependency Injection"
