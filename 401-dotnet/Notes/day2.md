# Day 2
#### 7/7/20

## Code Review
- int[] index defaults to 0
- `try-finally` `try-catch` `try-catch-finally` are ok.

## Data Structures
- mon-wed
- challenges and data structures folder
### Expectations
- whiteboard for an hour
- need your own tests
- big O
    - time
    - space
- visual and pseudo code is great for project managers
- 'truth table' or 'desk check'
- get the whiteboard and the github updated

- Documentations and Tests
    - keys to selling your product

## Summary Comments
- ///

## Unit Tests
- Test driven dev
    - red 
        - make it green
    - green
        - either make it refactor
        - or build a new test
    - refactor
        - make it green
- test should be independent
- you can never guarantee the order in which tests run
- all tests need to be green
- most lab assignments expect to have tests
    - cant test cw or readline
    - cant test a void method
        - must test a return type


## Lab
- values must be decimals

### Personal Notes for Lab
- Methods
    - UserInterface
        - return `void`
        - Keep asking the user to choose a transaction till they say exit
            1. Balance
            1. Deposit
            1. Withdraw
            1. Exit
        - holds all of the Console.ReadLine's
        - dont test this method
    - ViewBalance()
        - returns current balance
        - returns: decimal
        - Test to ensure balance is correct after each transaction
    - Withdraw()
        - subtracts money from the balance
        - return: decimal
        - do not allow user to withdraw more money that what's available
        - DOnt allow the user to withdraw a value less than 0
    - Deposit()
        - return: decimal
        - adds money to the balance
        - don't allow the user to deposit a neg number
- Variable
    - global `static public decimal Balance` above the `main`
- Keys:
    - Balance can never be below 0
    - don't use WriteLine or Readline in methods (Can't be tested)
    - make sure methods are just returning values
    - use proper data types (decimal) format the prints with $
    - each method should be `static public`
    - app needs to start without user input
- Unit Tests
    - use xUnit
    - test the things that DON'T require user input
    - at least 2 tests for every return type methods
    - A failing test, is not a valid test

## Directions for adding a test project
1. Right click on Solution and select Add
2. Select Project
3. Pick XUnit C#
4. Once loaded...Go back to Program.cs file and make that class public
5. Go back to Xunit Project and right click on Dependencies
6. Add Project dependency
7. Click the checkbox with your lab02 project
8. Save/Complete the popup.
5. Add in the following to the Top of your project: `using static Class02UnitTests.Program;` (Your Class02UnitTests name will be different)
6. You can now call all of yor Public methods in your program file.
