# [reading-note-401](https://mohammadsilwadi.github.io/reading-note-401/)
## In Tests We Trust - TDD with Python
 Important aspects about the unit test
 + The test file name should follow the same name of module name. For instance, if our module is gender.py, our test name should be test_gender.py.
 + Other thing to care about is the structure. A convention widely used is the AAA: Arrange, Act and Assert.
     + Arrange: you need to organize the data needed to execute that piece of code (input);
     + Act: here you will execute the code being tested (exercise the behaviour);
     +  Assert: after executing the code, you will check if the result (output) is the same as you were expecting.
+ Write a unit test and make it fail (it needs to fail because the feature isn’t there, right? If this test passes, call the Ghostbusters, really)
✅ Write the feature and make the test pass! (you can dance after that)
🔵 Refactor the code — the first version doesn’t need to be the beautiful one (don’t be shy)

## If name equals main
Before executing code, Python interpreter reads source file and define few special variables/global variables. 
If the python interpreter is running that module (the source file) as the main program, it sets the special __name__ variable to have a value “__main__”. If this file is being imported from another module, __name__ will be set to the module’s name. Module’s name is available as value to __name__ global variable. 

A module is a file containing Python definitions and statements. The file name is the module name with the suffix .py appended. 

Advantages : 

+ Every Python module has it’s __name__ defined and if this is ‘__main__’, it implies that the module is being run standalone by the user and we can do corresponding appropriate actions.
+ If you import this script as a module in another script, the __name__ is set to the name of the script/module.
+ Python files can act as either reusable modules, or as standalone programs.
+ if __name__ == “main”: is used to execute some code only if the file was run directly, and not imported.

## recursion 
A recursive function is a function defined in terms of itself via self-referential expressions. This means that the function will continue to call itself and repeat its behavior until some condition is met to return a result.