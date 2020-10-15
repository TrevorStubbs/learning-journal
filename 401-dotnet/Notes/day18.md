# Day 18

# JWT - JSON web tokens
- Importing the JWT into the app
- `Install-Package Microsoft.AspNetCore.Authentication.JwtBearer`
- In the setup file under AddDbContext method call in ConfigureServices.
```CSharp
services.AddAuthentication(options =>
{
    options.DefaultAuthenticateScheme = JwtBearerDefaults.AuthenticationScheme;
    options.DefaultChallengeScheme = JwtBearerDefaults.AuthenticationScheme;
    options.DefaultScheme = JwtBearerDefaults.AuthenticationScheme;
})
.AddJwtBearer(options =>
{
    options.TokenValidationParameters = new Microsoft.IdentityModel.Tokens.TokenValidationParameters
    {
        ValidateIssuer = true,
        ValidateAudience = true,
        ValidateLifetime = true,
        ValidateIssuerSigningKey = true,
        ValidIssuer = Configuration["JWTIssuer"]
    };
});
```
- right click project and click `Manage User Secrets`
- in secrets
``` JSON
{
  "ConnectionStrings": {
    "DefaultConnection": "Server=(localdb)\\MSSQLLocalDB;Database=AsyncInnDB;Trusted_Connection=True;MultipleActiveResultSets=true"
  },
  "JWTIssuer": "AsyncInn",
  "JWTKey": "M8+RgzRV0dN3eHTaPVXycwAk/LrnOPfblsAS96qNmrk="
}
```
- if you don't want your things to be sent to github then remove this `ConnectionStrings` from `appsettings.json`

- in Configure Method `app.UseAuthentication();` and `app.UseAuthorization();` AFTER `app.UseRouting()` and BEFORE `app.UseEndpoints(...)`

- Claims are things that are true about the user.

```CSharp
public async Task<IActionResult> Login(LoginDTO login)
{
    var result = await _signInManager.PasswordSignInAsync(login.Email, login.Password, false, false);

    if (result.Succeeded)
    {
        // Look up the user
        var user = await _userManager.FindByEmailAsync(login.Email);

        var token = CreateToken(user);

        // Make them a JWT token based on their account

        // Send them the JWT token back to the user

        // log the user in

        // log the user in
        return Ok(new
        {
            jwt = new JwtSecurityTokenHandler().WriteToken(token),
            expiration = token.ValidTo
        });
    }
    return BadRequest("Invalid Attempt");
}

private JwtSecurityToken CreateToken(ApplicationUser user)
{
    // Token requires pieces of info called "claims" 
    // Person/User is the principle
    // A principle can have many forms of ID
    // An id contains many claims
    // a claim is a statement about the user. 

    var authClaims = new[]
    {
        new Claim(JwtRegisteredClaimNames.Sub, user.UserName),
        new Claim(JwtRegisteredClaimNames.Jti, Guid.NewGuid().ToString()),
        new Claim("FirstName", user.FirstName),
        new Claim("LastName", user.LastName),
        new Claim("UserId", user.Id)
    };
    var token = AuthenticateToken(authClaims);

    return token;
}

private JwtSecurityToken AuthenticateToken(Claim[] claims)
{
    var signingKey = new SymmetricSecurityKey(Encoding.UTF8.GetBytes(_config["JWTKey"]));

    var token = new JwtSecurityToken(
        issuer: _config["JWTIssuer"],
        expires: DateTime.UtcNow.AddHours(24),
        claims: claims,
        signingCredentials: new SigningCredentials(signingKey, SecurityAlgorithms.HmacSha256)
        );

    return token;
}
```

- test using [jwt.io](https://jwt.io/)
- [AllowAnonymous] - allows anyone to view (no JWT needed to view)
- [Authorize] - requires a JWT token

## Testing MVC
- DB test class
    - implement IDisposable

```CSharp
public abstract class DatabaseTestBase : IDisposable
{
    private readonly SqlliteConnection _connection;
    protected readonly AsyncDbContext _db;

    public DatabaseTestBase(){
        _connection = new SqliteConnection("Filename=:memory:");
        _connection = Open();

        _db = new AsyncInnDbContext(new DbContextOptionBuilder<AsyncInnDbContext>()
                .UseSqlite(_connection)
                .Options);

        _db.Database.EnsureCreated();
    }

    public void Dispose()
    {
        _db?.Dispose();
        _connection?.Dispose();
    }
}
```
- in xunit
```CSharp
public class StudentServiceTest : DatabaseTestBase
{
    private IStudent BuildRepository()
    {
        return new StudentRepository(_db);
    }

    [Fact]
    public Task CanSaveAndGet()
    {
        // Arrange
        var student = new Student()
        {
            FirstName = "Josie",
            LastName = "Cat",
            Birthdate = DateTime.Now
        };

        var repository = BuildRepository();

        // Act
        var saved = await repository.Create(student);

        // Assert
        Assert.NotNull(saved);
        Assert.NotEqual(0, student.Id);
        Assert.Equal(saved.Id, student.Id);
        Assert.Equal(student.FirstName, saved.FirstName);
    }

}