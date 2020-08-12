# Read: Layouts

- [View Layouts](https://docs.microsoft.com/en-us/aspnet/core/mvc/views/layout?view=aspnetcore-2.1)
- [Partial Views](https://docs.microsoft.com/en-us/aspnet/core/mvc/views/partial?view=aspnetcore-2.1)
- [View Models](https://docs.microsoft.com/en-us/aspnet/core/mvc/views/overview?view=aspnetcore-2.2)
- [Tag Helpers](https://docs.microsoft.com/en-us/aspnet/core/mvc/views/tag-helpers/intro?view=aspnetcore-2.1)
- [Tag Helpers with Forms](https://docs.microsoft.com/en-us/aspnet/core/mvc/views/working-with-forms?view=aspnetcore-2.1)

## View Layouts
- Most web apps have a common layout that provides the user with a consistent experience as they navigate from page to page.
- By convnetion the layout page in ASP.NET is named _Layout.cshtml.   
    - and it lives in the Shared folder
- Sample Layout page:
``` html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>@ViewData["Title"] - WebApplication1</title>

    <environment include="Development">
        <link rel="stylesheet" href="~/lib/bootstrap/dist/css/bootstrap.css" />
        <link rel="stylesheet" href="~/css/site.css" />
    </environment>
    <environment exclude="Development">
        <link rel="stylesheet" href="https://ajax.aspnetcdn.com/ajax/bootstrap/3.3.7/css/bootstrap.min.css"
              asp-fallback-href="~/lib/bootstrap/dist/css/bootstrap.min.css"
              asp-fallback-test-class="sr-only" asp-fallback-test-property="position" asp-fallback-test-value="absolute" />
        <link rel="stylesheet" href="~/css/site.min.css" asp-append-version="true" />
    </environment>
</head>
<body>
    <nav class="navbar navbar-inverse navbar-fixed-top">
        <div class="container">
            <div class="navbar-header">
                <button type="button" class="navbar-toggle" data-toggle="collapse" data-target=".navbar-collapse">
                    <span class="sr-only">Toggle navigation</span>
                    <span class="icon-bar"></span>
                    <span class="icon-bar"></span>
                    <span class="icon-bar"></span>
                </button>
                <a asp-page="/Index" class="navbar-brand">WebApplication1</a>
            </div>
            <div class="navbar-collapse collapse">
                <ul class="nav navbar-nav">
                    <li><a asp-page="/Index">Home</a></li>
                    <li><a asp-page="/About">About</a></li>
                    <li><a asp-page="/Contact">Contact</a></li>
                </ul>
            </div>
        </div>
    </nav>

    <partial name="_CookieConsentPartial" />

    <div class="container body-content">
        @RenderBody()
        <hr />
        <footer>
            <p>&copy; 2018 - WebApplication1</p>
        </footer>
    </div>

    <environment include="Development">
        <script src="~/lib/jquery/dist/jquery.js"></script>
        <script src="~/lib/bootstrap/dist/js/bootstrap.js"></script>
        <script src="~/js/site.js" asp-append-version="true"></script>
    </environment>
    <environment exclude="Development">
        <script src="https://ajax.aspnetcdn.com/ajax/jquery/jquery-3.3.1.min.js"
                asp-fallback-src="~/lib/jquery/dist/jquery.min.js"
                asp-fallback-test="window.jQuery"
                crossorigin="anonymous"
                integrity="sha384-tsQFqpEReu7ZLhBV2VZlAu7zcOV+rXbYlF2cqB8txI/8aZajjp4Bqd+V6D5IgvKT">
        </script>
        <script src="https://ajax.aspnetcdn.com/ajax/bootstrap/3.3.7/bootstrap.min.js"
                asp-fallback-src="~/lib/bootstrap/dist/js/bootstrap.min.js"
                asp-fallback-test="window.jQuery && window.jQuery.fn && window.jQuery.fn.modal"
                crossorigin="anonymous"
                integrity="sha384-Tc5IQib027qvyjSMfHjOMaLkfuWVxZxUPnCJA7l2mCWNIpG9mGCD8wGNIcPD7Txa">
        </script>
        <script src="~/js/site.min.js" asp-append-version="true"></script>
    </environment>

    @RenderSection("Scripts", required: false)
</body>
</html>
```
- Take note of the `@RenderBody()` tag.
    - this is where another page will get inserted.


### Specifying a Layout
``` html
@{
    Layout = "_Layout";
}
```
- When a partial name is provided. the Razor view engine searches for the layout file using its standard discovery process.

### Sections
- A layout can optionally reference 1 or more sections by calling `RenderSection`
``` html
<script type="text/javascript" src="~/scripts/global.js"></script>

@RenderSection("Scripts", required: false)
```

## Partial Views
- Partial Vies are an effective way to:
    - Break up large html files into smaller components
    - Reduce duplicate code in html files 

### Declare Parital Views
- use _ to start a partail name

``` csharp
public IActionResult OnGetPartial() =>
    new PartialViewResult
    {
        ViewName = "_AuthorPartialRP",
        ViewData = ViewData,
    };
```

- use partal tag
``` html
<partial name="~/Pages/Folder/_PartialName.cshtml" />
<partial name="/Pages/Folder/_PartialName.cshtml" />
```
- can use @await for asynchronous

### Partial view discovery order
- When a partial view is referenced by name without a file extension, the following locations are searched in the stated order:

#### Razor Pages

1. Currently executing page's folder
1. Directory graph above the page's folder
1. /Shared
1. /Pages/Shared
1. /Views/Shared

#### MVC

1. /Areas/<Area-Name>/Views/<Controller-Name>
1. /Areas/<Area-Name>/Views/Shared
1. /Views/Shared
1. /Pages/Shared


## View Models
``` html
@{
    ViewData["Title"] = "About";
}
<h2>@ViewData["Title"].</h2>
<h3>@ViewData["Message"]</h3>

<p>Use this area to provide additional information.</p>
```
- in the controller
``` csharp
public IActionResult About()
{
    ViewData["Message"] = "Your application description page.";

    return View();
}
```

### View Discovery
1. Views/[ControllerName]/[ViewName].cshtml
1. Views/Shared/[ViewName].cshtml

- Helper Example
``` 
@using AuthoringTagHelpers
@addTagHelper *, Microsoft.AspNetCore.Mvc.TagHelpers
@addTagHelper *, AuthoringTagHelpers
```
- helps with IntelliSense in cshtml



## Tag Helpers
- Enable server-side code to participate in creating and rendering HTML in Razor files.

## Tag Helpers with Forms
|Attribute |	Description|
| --- | --- |
asp-controller |	The name of the controller.
asp-action |	The name of the action method.
asp-area |	The name of the area.
asp-page |	The name of the Razor page.
asp-page-handler |	The name of the Razor page handler.
asp-route |	The name of the route.
asp-route-{value} |	A single URL route value. For example, asp-route-id="1234".
asp-all-route-data |	All route values.
asp-fragment |	The URL fragment.