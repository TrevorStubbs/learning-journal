# Readings: Exception Handling
#### 7/3/20

- [Debugging for absolute beginners](https://docs.microsoft.com/en-us/visualstudio/debugger/debugging-absolute-beginners?view=vs-2019)
- [Try/Catch Blocks](https://docs.microsoft.com/en-us/dotnet/standard/exceptions/how-to-use-the-try-catch-block-to-catch-exceptions)
- [Exception Handling](https://docs.microsoft.com/en-us/dotnet/standard/exceptions/how-to-use-the-try-catch-block-to-catch-exceptions)
- C# 7.0 in a Nutshell - pg. 158 - 166 (start @ “try Statements and Exceptions)
    - Try/Catch & Exceptions excerpt from assigned book (introduction)
- [Therac-25](https://en.wikipedia.org/wiki/Therac-25)
- [Ariane 5](https://en.wikipedia.org/wiki/Ariane_5)

## Debugging for Absolute Beginners
- Debugging means to run code 1 step at atime to find the exact point where the programming mistake was made. 
### Clarify the problem: Ask the right questions
- What did we expect the code to do?
- What is happening instead?
- Exceptions are good things
    - they tell you exactly where the error is. 
- If there are no exceptions then it can get more complicated
    - What is the symptom of the problem?
    - Do you suspect where the problem is?

### Examine your assumptions
- Are you sing the right API?
- Are you using the API correctly?
- Are there any typos?
- Did you change the code and assume it is unrelated to the problem?
- Are the values different than what you expected?
- DO you know the intent of the code?
### Step through the code
- Debugging monitors everything that's happening as the program runs
- It allows you to pause the app.
- VS exception helper takes you to the exact point where the exception occurred
- Use breakpoints the examine what exactly is happening

## How to use try/catch
- Place code statements that might raise or throw an exception in a try block
- place a catch block after a try block to catch exceptions
    - In the catch block place statements to handle the exception
``` C#
using System;
using System.IO;

public class ProcessFile
{
    public static void Main()
    {
        // Try to open the file
        try
        {
            using (StreamReader sr = File.OpenText("data.txt"))
            {
                Console.WriteLine($"The first line of this file is {sr.ReadLine()}");
            }
        }
        // if the file is not there cw this
        catch (FileNotFoundException e)
        {
            Console.WriteLine($"The file was not found: '{e}'");
        }
        // if the directory isn't there cs this
        catch (DirectoryNotFoundException e)
        {
            Console.WriteLine($"The directory was not found: '{e}'");
        }
        // if the file can not be opened cw this
        catch (IOException e)
        {
            Console.WriteLine($"The file could not be opened: '{e}'");
        }
    }
}
```

- the CLR will catch exceptions but will send them in 1 of 3 ways
    - A debug dialog box appears
    - the program stops completely and dialog box appears with the exception
    - An error prints out to the standard error output stream
- using a try/catch block allows us to direct that flow.

## Statement keywords
- `if` `else` `switch` `case`
- `do` `for` `foreach` `in` `while`
- `break` `continue` `default` `goto` `return` `yield`
- `throw` `try-catch` `try-finally` `try-catch-finally`

## Try/Catch & Exceptions - pg. 158 - 166 
- `try` block must be followed by a `catch` block or a `finally` block or both
- `catch` has access to an `Exception` object that contains info about the error.
- `finally` always gets called even if there weren't any errors.
    - adds determinism
> Checking for preventable errors is preferable than using `try/catch` since exceptions are expensive to handle (100s of clock cycles).
- CLR with exceptions: 'Is execution currently withing a `try` statement that can catch the exception?'
    - if so, execution is passed to the `catch` block. 
    - if not, execution jumps back to the caller of the method.
- If no function takes responsibility for the exception, an error box is displayed and the program terminates.
### The `catch` Clause
- A `catch` clause specifies what type of exception to catch.
- `System.Exception` catches all possible errors: (useful when)
    - Program can potentially recover regardless of the exception type
    - Plan to rethrow the exception (logging it?)
    - Last resort prior to termination of the program
- use specific catches first before `System.Exception`
### Exception filters
- use `when` to filter the exception
``` C#
catch (WebException ex) when (ex.Status == WebExceptionStatus.Timeout)
{
    ...
}
```
### Finally Block
- `finally` always gets executed no matter if there was an exception thrown or not.
    - even gets called if the `try` hit a `jump` statement
- the only thing that can defeat a `finally` is an infinite loop or the process ending abruptly.
### `using` statement
- `using (StreamReader reader = File.OpenText("file.txt")){}`
### Throwing Exceptions
- prior to C# 7 throw was always a statement.
- now can be in expression-bodied functions
- `throw;` will rethrow the same exception
``` C#
string s = null;
using (WebClient wc = new WebClient())
    try { s = wc.DownloadString ("http:\/\/www.albahari.com/nutshell/"); }
    catch (WebException ex)
    {
    if (ex.Status == WebExceptionStatus.Timeout)
        Console.WriteLine ("Timeout");
    else
        throw; // Can't handle other sorts of WebException, so rethrow
    }
```
``` C#
 // 6.0+
catch (WebException ex) when (ex.Status == WebExceptionStatus.Timeout)
{
    Console.WriteLine ("Timeout");
}
```

### Key Properties of `System.Exception`
- StackTrace
- Message
- InnerException

### Common Exception Types
using System;
- ArgumentException
- ArgumentNullException
- ArgumentOutOfRangeException
- InvalidOperationException
- NotSupportedException
- NotImplementedException
- ObjectDisposedException
- NullReferenceException

## Therac-25
- overdose of radiation causing death or serous injury
    - caused by programming errors
- 2 software faults
    - operator incorrectly selected X-ray mode before quickly changing to electron mode. 
    - allowed the electron beam to activate during field-light mode
- Previous models had hardware locks to prevent faults but Therac-25 removed them (saving cost) and depended on software.
- Software was designed so that it was impossible to test in a clean automated way.

## Ariane 5
- First test flight failed do to a malfunction in the control software.
- 64-bit float was being converted to a 16-bit int
- complete reuse of Ariane 4 into 5.
    - 5 has a different preparation sequence
