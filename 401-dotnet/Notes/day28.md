# Day 28

- @using Microsoft.AspNetCore.Identity;
- @using CerealECommerce.Models;
- `@inject SignInManager<Customer> SignInManager`

``` csharp
@{
    Layout="_Home";
}
```

``` html
@if(SignInManager.IsSignedIn(User))
{
    <span> Welcome @User.Claims.First(x => x.Type == "FullName").Value!</span>
    <form asp-page="/Account/Logout" method="Post"> <button type="submit>Logout</button></form>
}
else
{
    <a asp-page="/Account/Login">Login</a>
    <a asp-page="/Account/Register">Register</a>
}
```

``` csharp
private SignInManager<Customer> _signInManager;

public LogoutModel(SignInManager<Customer> signIn)
{
    _signInManager = signIn;
}

public async Task<IActionResult> OnPost()
{
    await _signInManager.SignOutAsync();

    return RedirectToAction("Index", "Home");
}
```