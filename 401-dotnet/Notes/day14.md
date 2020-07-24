# Day 14

- DI
- Nav properties
- DTOs
- REST
- Model binding

# DI 
- depend on behavoir not actions

# Adding Join Table
- migration after the join table is made
- CLI Commands
    - `add-migration [nameOfMigration]`
    - `update-database`

    `Install - Package Microsoft.AspNetCore.Mvc.NewtonsoftJson - Version 3.1.2`
``` CSharp
services.AddControllers().AddNewtonsoftJson(options =>
options.SerializerSettings.ReferenceLoopHandling = Newtonsoft.Json.ReferenceLoopHandling.Ignore
);
```

```CSharp
var enrollments = await _context.Enrollments.Where(x => x.CourseId == id)
                            .Include(x => x.Student)
                            .ToListAsync();
```

```CSharp
var enrollments = await _context.Enrollments.Where(x => x.StudentId == id)
                                            .Include(x => x.Student)
                                            .ToListAsync();
```

---

## Steps to add Join Table with nav properties
1. Download and install NewtonSoftJson
    - in Package Manager Console
        - `Install-Package Microsoft.AspNetCore.Mvc.NewtonsoftJson`
        - add this to the `services.AddControllers();` method call:
```CSharp
services.AddControllers().AddNewtonsoftJson(options =>
    options.SerializerSettings.ReferenceLoopHandling = Newtonsoft.Json.ReferenceLoopHandling.Ignore
    );
```

2. Add a model of the join table
    - Add table properties
    - Add Nav properties
        - Nav properties are properties of the pointing model
            - `public [ModelName] [PropertyName] {get; set;}`
        - add Nav properties to the other 2 tables
            - make them List properties
    - add a reference to the composite key to the DbContext file
        - `modelBuilder.Entity<[ModelName]>().HasKey(x => new { x.[CompositeKey1], x.[CompositeKey2] });`
    - `add-migration [nameOfMigration]`
    - `update-database`


3. update Services (repository files) (point to the join table)
- add new method to link 1 service file to the join table model
```CSharp
public async Task Add[OtherModel](int [compositeKey1], int [compositeKey2]) // otherModel is the model from the other table
{
    [JoinModel] [variableName] = new [JoinModel]() //modelName is the join table
    {
        [CompositeKey1] = [compositeKey1],
        [CompositeKey2] = [compositeKey2]
    };
    _context.Entry([variableName]).State = EntityState.Added;
    await _context.SaveChangesAsync();
}
```
- add new method to remove the association
```CSharp
public async Task Remove[OtherModelFromJoinThisTable](int compositeKey1, int compositeKey1)
{
    var result = await _context.[joinModel[].FirstOrDefaultAsync(x => x.[CompositeKey1] == [compositeKey1] && x.[CompositeKey2] == [compositeKey2]);
    _context.Entry(result).State = EntityState.Deleted;
    await _context.SaveChangesAsync();
}
```
- update get specific item
    - include:
``` CSharp
var [joinModel] = await _context.[JoinModel].Where(x => x.[CompositeKeyId] == id)
                                            .Include(x => x.[OtherModel])
                                            .ToListAsync();
[thisModel].[JoinModel] = [joinModel];
```

4. Add the new models to the interfaces
- `Task AddStudent(int studentId, int courseId);`
- `Task RemoveStudentFromCourse(int courseId, int studentId);`

5. Update Controllers
```CSharp
[HttpPost]
[Route("{courseId}/{studentId}")]
// POST: {courseId}/{studentId}
// Model Binding
public async Task<IActionResult> AddStudentToCourse(int courseId, int studentId)
{
    await _course.AddStudent(studentId, courseId);
    return Ok();
}

[HttpDelete]
[Route("{courseId}/{studentId}")]
public async Task<IActionResult> RemoveStudentFromCourse(int courseId, int studentId)
{
    await _course.RemoveStudentFromCourse(courseId, studentId);
    return Ok();
}
```