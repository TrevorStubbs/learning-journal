# Readings: Unit Testing and Documentation
#### 7/3/20

- [Unit Testing Best Practices *Not in Xunit, but concepts are still true](https://stackify.com/unit-testing-basics-best-practices/)
- [XUnit Documentation](https://xunit.github.io/#documentation)
- [Art of Readme](https://github.com/noffle/art-of-readme)
- [ReadMe Best Practices](https://github.com/jehna/readme-best-practices)

## Unit Testing Best Practices
### What isn't a unit test?
- adding things to a DB or reading a file is not a unit test
- Unit tests don't deal with their environment
- Smoke test vs Unit test
    - throwing thousands of tests at a service
### What is a unit test?
- they isolate and exercise specific units of code. 
- Unit is a method
- tests something specific about that method in isolation.
    - they don't test all the things
### Antaomy of a Unit Test
- name the class [NameOfTheThingTested]Test  
    - so you know what method it is testing
    - it gets an attribute [TestClass]
    - name the testing method exactly how you are testing it
        - `Adding_4_And_3_Should_Return_7`
    - use the `Assert` class's methods to test what you need.
        - `Assert.AreEqual`
    
### UT Best Practices
1. Arrange, Act, Assert
    - Lean on the scientific method
    - Your test name is a hypothesis
        - the result is your experiment
    - First arrange everything we need to run the experiment.
    - Act - run the test
    - Assert - what is the result and does it match your hypothesis?
1. One Assert Per Test Method
    - Test only 1 thing at a time
        - same as methods
    - I will be hard to understand what went wrong if there are more than 1 assertions per test.
1. Avoid Test Interdependence
    - Each test should handle its own setup and tear down. 
    - Tests might run in parallel or out of order
        - don't depend on the order for a successful test. 
1. Keep it Short, Sweet and Visible
    - Resist abstract test setup.
        - some argue that base classes are inappropriate in testing.
    - comes down to knowing what went wrong
        - more complex more difficult to find the problem
1. Recognize Test Setup Pain as a Smell
    - If 'arrange' becomes hard, STOP!
    - If the tests are hard to build there might be a problem with your design not your code.
    - Heavy setup tests are brittle tests.
1. Add Them to the Build
    - if tests fail build fails
    - will help in the long run

### Xunit Setup
``` XML
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFramework>netcoreapp2.1</TargetFramework>
  </PropertyGroup>

  <ItemGroup>
    <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.9.0" />
    <PackageReference Include="xunit" Version="2.4.1" />
    <PackageReference Include="xunit.runner.visualstudio" Version="2.4.1" />
  </ItemGroup>

</Project>
```

- `dotnet test`
- [Fact] Vs [Theory]
    - Facts are always true. They test invariant conditions
    - Theories are tests which are only true for a particular set of data.
        - something to cause the test to fail but not cause of a bad algorithm.

### Multi target tests
``` XML
  <PropertyGroup>
    <TargetFrameworks>net452;netcoreapp2.1</TargetFrameworks>
  </PropertyGroup>
```

- if you change the `.csproj` file you need to run `dotnet restore`
### Running tests with VS
- test explorer panel

---

## Art of README
- all caps
- Writing good docs is all about getting the user out of the source code.
### The README: Your one-stop shop
1. tell them what your module (app) is
1. show them what it looks like in action
1. show them how they use it
1. tell them any other relevant details

- TL:DR but not too short to not give any useful info
- Learn from others
    - Pearl and CPAN are great

>Your documentation is complete when someone can use your module without ever having to look at its code. This is very important. This makes it possible for you to separate your module's documented interface from its internal implementation (guts). This is good because it means that you are free to change the module's internals as long as the interface remains the same.
>
>Remember: the documentation, not the code, defines what a module does. -- Ken Williams

- A well constructed README will help the dev determine if the software fits their needs. 

- Outline
    1. Name
    1. one-liner
    1. usage
    1. api
    1. installation
    1. license

- Provides cognitive funneling
- Show a care for Devs time

## README Best Practices
- Provided outline for building a good README.md

![Logo of the project]()

# Name of the project
> Additional information or tagline

A brief description of your project, what it is used for and how does life get
awesome when someone starts to use it.

## Installing / Getting started

A quick introduction of the minimal setup you need to get a hello world up &
running.

```shell
packagemanager install awesome-project
awesome-project start
awesome-project "Do something!"  # prints "Nah."
```

Here you should say what actually happens when you execute the code above.

### Initial Configuration

Some projects require initial configuration (e.g. access tokens or keys, `npm i`).
This is the section where you would document those requirements.

## Developing

Here's a brief intro about what a developer must do in order to start developing
the project further:

```shell
git clone https://github.com/your/awesome-project.git
cd awesome-project/
packagemanager install
```

And state what happens step-by-step.

### Building

If your project needs some additional steps for the developer to build the
project after some code changes, state them here:

```shell
./configure
make
make install
```

Here again you should state what actually happens when the code above gets
executed.

### Deploying / Publishing

In case there's some step you have to take that publishes this project to a
server, this is the right time to state it.

```shell
packagemanager deploy awesome-project -s server.com -u username -p password
```

And again you'd need to tell what the previous code actually does.

## Features

What's all the bells and whistles this project can perform?
* What's the main functionality
* You can also do another thing
* If you get really randy, you can even do this

## Configuration

Here you should write what are all of the configurations a user can enter when
using the project.

#### Argument 1
Type: `String`  
Default: `'default value'`

State what an argument does and how you can use it. If needed, you can provide
an example below.

Example:
```bash
awesome-project "Some other value"  # Prints "You're nailing this readme!"
```

#### Argument 2
Type: `Number|Boolean`  
Default: 100

Copy-paste as many of these as you need.

## Contributing

When you publish something open source, one of the greatest motivations is that
anyone can just jump in and start contributing to your project.

These paragraphs are meant to welcome those kind souls to feel that they are
needed. You should state something like:

"If you'd like to contribute, please fork the repository and use a feature
branch. Pull requests are warmly welcome."

If there's anything else the developer needs to know (e.g. the code style
guide), you should link it here. If there's a lot of things to take into
consideration, it is common to separate this section to its own file called
`CONTRIBUTING.md` (or similar). If so, you should say that it exists here.

## Links

Even though this information can be found inside the project on machine-readable
format like in a .json file, it's good to include a summary of most useful
links to humans using your project. You can include links like:

- Project homepage: https://your.github.com/awesome-project/
- Repository: https://github.com/your/awesome-project/
- Issue tracker: https://github.com/your/awesome-project/issues
  - In case of sensitive bugs like security vulnerabilities, please contact
    my@email.com directly instead of using issue tracker. We value your effort
    to improve the security and privacy of this project!
- Related projects:
  - Your other project: https://github.com/your/other-project/
  - Someone else's project: https://github.com/someones/awesome-project/


## Licensing

One really important part: Give your project a proper license. Here you should
state what the license is and how to find the text version of the license.
Something like:

"The code in this project is licensed under MIT license."