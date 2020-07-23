# Day 12

- [Ref](https://codefellows.github.io/code-401-dotnet-guide/Curriculum/Class12/lab/)

## Building out a .NET server
- Change app.UseEndpoints to `endpoints.MapControllerRoute("Default", "{controller=Home}/{action=Index}/{id?}");`
- Make a models folder
    - build properties that follow the ERD plan
- Make a Data 
    - Make a new class `[ProjectName]DbContext`
        - Inherits from `DbContext`
        - Build a contstructor
            -  `public [ProjectName]DbContext(DbContextOptions<[ProjectName]DbContext> options) : base(options)`
        - Make class properties
            - `public DbSet<[ModelName]> [ModelName] {get;set;}`
- In appsettings.json add
    - `"ConnectionStrings": {`
    `"DefaultConnection": "Server=(localdb)\\MSSQLLocalDB;Database=[ProjectName]DB;Trusted_Connection=True;MultipleActiveResultSets=true"`
- Startup Update
``` CSharp
        public IConfiguration Configuration { get; }

        public Startup(IConfiguration configuration)
        {
            Configuration = configuration;
        }
        // This method gets called by the runtime. Use this method to add services to the container.
        // For more information on how to configure your application, visit https://go.microsoft.com/fwlink/?LinkID=398940
        public void ConfigureServices(IServiceCollection services)
        {
            services.AddControllers();

            services.AddDbContext<AsyncInnDbContext>(options =>
           {
               options.UseSqlServer(Configuration.GetConnectionString("DefaultConnection"));
           });
        }
```
- Package Manager Console Commands:
    - `Install-Package Microsoft.EntityFrameworkCore.SqlServer` - install sql into the project. (do this before adding to the appsettings.json file)
    - `Install-Package Microsoft.EntityFrameworkCore.Tools` - install migration tools
    - `add-migration [initial]` - Each migration needs this add a unique name to each one.
    - `update-database` - will update the database with the new migration
- Seed the data using this format:
``` CSharp
protected override void OnModelCreating(ModelBuilder modelBuilder)
{
    modelBuilder.Entity<Student>().HasData(
        new Student
        {
            Id = 1,
            FirstName = "Jack",
            LastName = "Shepard",
            Birthdate = new DateTime(1970, 3, 5)
        },
        new Student
        {
            Id = 2,
            FirstName = "Kate",
            LastName = "Austin",
            Birthdate = new DateTime(1980, 11, 11)

        }
        );

    modelBuilder.Entity<Course>().HasData(
        new Course
        {
            Id = 1,
            CourseCode = "seattle-dotnet-401d11",
            Price = 100m,
            Technology = Technology.dotNet
        },
        new Course
        {
            Id = 2,
            CourseCode = "seattle-201d100",
            Price = 50m,
            Technology = Technology.javascript
        }
        );
}
```
- Make a Controllers Folder - Must be called Controllers
    - Add new API Controller with actions, using Entity Framework





## Filling the DB
- created a models folder
- make a simple model
    - 