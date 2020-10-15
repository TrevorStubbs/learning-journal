# Readings: Policies

1. [Policies](https://docs.microsoft.com/en-us/aspnet/core/security/authorization/policies?view=aspnetcore-2.1)
1. [Custom Policy Providers](https://docs.microsoft.com/en-us/aspnet/core/security/authorization/iauthorizationpolicyprovider?view=aspnetcore-2.1)

## Policies
- in Startup
``` csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddMvc().SetCompatibilityVersion(CompatibilityVersion.Version_2_2);

    services.AddAuthorization(options =>
    {
        options.AddPolicy("AtLeast21", policy =>
            policy.Requirements.Add(new MinimumAgeRequirement(21)));
    });
}
```
- other implementation
``` csharp
public void ConfigureServices(IServiceCollection services)
{
    // Add all of your handlers to DI.
    services.AddSingleton<IAuthorizationHandler, MyHandler1>();
    // MyHandler2, ...

    services.AddSingleton<IAuthorizationHandler, MyHandlerN>();

    // Configure your policies
    services.AddAuthorization(options =>
          options.AddPolicy("Something",
          policy => policy.RequireClaim("Permission", "CanViewPage", "CanViewAnything")));


    services.AddMvc().SetCompatibilityVersion(CompatibilityVersion.Version_2_2);
}
```
- Implements IAuthorization

- at the top of controllers [Authorize] or [Authorize(Policy = "[PolicyName]")]
    - can be using in razor pages as well

- Handler returns no value so its good to use `context.Succeed(IAuthorizationRequirement requirement)`


## Custom Policy Providers
- Use of IAuthorizationPolicyProvider
- `GetPolicyAsync` returns an authorization policy for a given name
- `GetDefaultPolicyAsync` returns the default authorization policy.
- `GetFallbackPolicyAsync` returns the fallback authorization policy.