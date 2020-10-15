# Read: Code First Migrations

- [MVC with EF Get Started](https://docs.microsoft.com/en-us/aspnet/core/data/ef-mvc/intro?view=aspnetcore-3.1)
    - If you have time, read the preceding articles under this category as well.
- [Entity Framework Core](https://docs.microsoft.com/en-us/ef/core/)
- [User Secrets](https://codefellows.github.io/code-401-dotnet-guide/Resources/UserSecrets.html)

---

## MVC with EF
### Entity Framework
- Can serve as a object-relational mapper (O/RM).
    - Allows developers to work with a db using .NET objects.
#### The Model
- A model is made up of the entity classes and a context object that represents a session with the db. 
    - A model can be generated from an existing db. (EF Migrations)
#### Querying
- use LINQ
#### Saving Data
- [DBContext](https://docs.microsoft.com/en-us/dotnet/api/system.data.entity.dbcontext?view=entity-framework-6.2.0) base class has methods for saving

## User Secrets
- User secrets is a secure way of storing private user information. (API keys, client secrets and connection strings.)
    - CSharp version of ENV?
### Enabling user secrets
1. Right click on your project
1. Select “Manage User Secrets”

- in `appsetting.json`
``` JSON
{
  "myBingAPIKey": "{VALUE}",
  "textAPIKey": "{VALUE}",
  "ConnectionStrings": {
    "AzureConnection": "{CONNECTION STRING HERE}"
}
```

- This will not get pushed up to the project repo
    - if using standard local environment it's `%APPDATA%\microsoft\UserSecrets\<userSecretsId>\secrets.json.`

- Open `.csproj` 
- verify that `<UserSecretsId>ID goes here</UserSecretsId>` exists
- add `<DotNetCliToolReference Include="Microsoft.Extensions.SecretManager.Tools" Version="2.0.0" />`

### Accessing User Secrets withing the controller
- in the startup controller add:
``` CSharp
public IConfiguration Configuration { get; }

public Startup(IConfiguration configuration)
{
    var builder = new ConfigurationBuilder().AddEnvironmentVariables(); // <-- Don't forget this
    builder.AddUserSecrets<Startup>();
    Configuration = builder.Build();
}
```
- Add: `using Microsoft.Extensions.Configuration;` to the controller

- In the controller constructor
``` Csharp
private readonly ImagesContext _context;
private readonly IConfiguration Configuration;

public ImageController(ImagesContext context, IConfiguration configuration)
{
    _context = context;
    Configuration = configuration;
}
```

- the secrets are accessible with `Configuration["KEYVALUEHERE"]`
- for examples:
``` CSharp
client.DefaultRequestHeaders.Add("Ocp-Apim-Subscription-Key", 
                Configuration["myBingAPIKey"]);
```
- In Azure you need to setup the secrets
1. Go to your App Services
1. Select the site you are working on
1. In the left hand navigation, select application settings
1. Under the “App Setting” you can add in user secret data. Azure sees this environment variable data.