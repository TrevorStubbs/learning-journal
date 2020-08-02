# Day 17

# RESTful
- **RE**presentational - json
- **S**tate
- **T**ransfer

## Verbs
- Get -> /Students
- Get -> /Students/id
- Put -> /Students/id
- Post -> /Students
- Delete -> /Students/id

## XML

## Identity
- Authentication 
    - auth/n
- Authorization
    - auth/z

- Identity API
    - application
    - programming
    - interface

you can decrypt something that is encrypted
it is very hard to unhash
salting adding to a password.
    each user has a different salt

## Add ID
- `install-package Microsoft.AspNetCore.Identity.EntityFrameworkCore`
- Make new model [ApplicationUser]
- in startup under `services.AddDbContext` method
``` CSharp
services.AddIdentity<ApplicationUser, IdentityRole>()
        .AddEntityFrameworkStores<AsyncInnDbContext>()
        .AddDefaultTokenProviders();
```
- in OnModelCreating in DbContext
``` CSharp
base.OnModelCreating(modelBuilder);
```
- in dbcontext add `IdentityDbContext<[NewModelName]>`
- add-migration update-database
- Make an empty API controller
    - [AccountController]
```CSharp
// api/account/register
[HttpPost,Route("register")]
public async Task<IActionResult> Register(RegisterDTO register)
{
    // do something to put this into the database
    ApplicationUser user = new ApplicationUser()
    {
        Email = register.Email,
        UserName = register.Email,
        FirstName = register.FirstName,
        LastName = register.LastName
    };

    //create the user
    var result = await _userManager.CreateAsync(user, register.Password);

    if (result.Succeeded)
    {
        // sign the user in if it was successful.
        await _signInManager.SignInAsync(user, false);

        return Ok();

    }
    return BadRequest("Invalid Registration");     
}
```
- Postman example
``` JSON
{
    "email":  "example@example.com",
    "firstName": "Josie",
    "lastName": "Cat",
    "password": "@Test123"
}
```
- For Logging in
``` CSharp
// api/account/Login
[HttpPost, Route("Login")]
public async Task<IActionResult> Login(LoginDTO login)
{
    var result = await _signInManager.PasswordSignInAsync(login.Email, login.Password, false, false);

    if (result.Succeeded)
    {
        // log the user in
        return Ok("logged in");
    }
    return BadRequest("Invalid Attempt");
}
```


1. Create an Application User Model `ApplicationUser : IdentityUser`
1. Update your DbContext to derive from `IdentityDbContext`
1. Update your database to integrate in the Identity database tables
1. Register Identity into your Startup file services.AddIdentity....
1. Create an Account Controller and add both Register and Login actions
1. Confirm that you can register a user successfully in the database
1. Confirm that you can login with the credentials of an existing user