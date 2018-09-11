# Test Driven Development
TDD was created by Kent Beck in the mid 1990s as part of his work for the Chrysler Corporation where he also created Extreme Programming, of which TDD is just a part.

## Overview
* The process drives this by having you write the unit tests before the production code. 
* You write one unit test for one test case and then you write the production code to make it pass. 
* The tests and the production code are written together with small tests being written and then small bits of production code that make those tests pass. 

### Benefits of TDD
* TDD gives you confidence to make changes in your code because you have to test before you begin that verifies the code is working and will tell you if any of your changes have broken anything
* Writing the unit test first helps drive good object oriented design as making individual classes and functions testable and isolation drives the developer to break the dependencies and add interfaces rather than linking concrete implementations together directly.

### TDD Workflow: Red, Green and Refactor
* Write a failing unit test (the RED phase)
* Write just enough production code to make the test pass (the GREEN phase)
* Refactor the unit test and the production code to make it clean (the REFACTOR phase)
* Repeat until the feature is complete

### Uncle Bob's 3 laws of TDD
* You may not write any production code until you have written a failing unit test
* You may not write more of a unit test than is sufficient to fail, and not compiling is failing
* You may not write more production code than is sufficient to pass the currently failing unit test


