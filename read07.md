# [reading-note-401](https://mohammadsilwadi.github.io/reading-note-401/)

##   Python Scope

#### Names and Scopes in Python

| Operation | Statement |
| ---------------    | ----------- |
| Assignments |	x = value |
| Import operations | import name |
| Function definitions|def my_func(): ... |
| Argument definitions in the context of functions	 |	def my_func(arg1, arg2,... argN):  |
|Class definitions | class MyClass:|

#### Python Scope vs Namespace
In Python, the concept of scope is closely related to the concept of the namespace. As you’ve learned so far, a Python scope determines where in your program a name is visible. Python scopes are implemented as dictionaries that map names to objects. These dictionaries are commonly called namespaces. These are the concrete mechanisms that Python uses to store names. They’re stored in a special attribute called .__dict__.

Names at the top level of a module are stored in the module’s namespace. In other words, they’re stored in the module’s .__dict__ attribute. Take a look at the following code:

>>> `import sys`
>>> `sys.__dict__.keys()`
`dict_keys(['__name__', '__doc__',` `'__package__',..., 'argv', 'ps1', 'ps2'])`

#### Using the LEGB Rule for Python Scope
when you use nested functions, names are resolved by first checking the local scope or the innermost function’s local scope. Then, Python looks at all enclosing scopes of outer functions from the innermost scope to the outermost scope. If no match is found, then Python looks at the global and built-in scopes. If it can’t find the name, then you’ll get an error.

At any given time during execution, you’ll have at most four active Python scopes—local, enclosing, global, and built-in—depending on where you are in the code. On the other hand, you’ll always have at least two active scopes, which are the global and built-in scopes. These two scopes will always be available for you.
## Global
Note: Global names can be updated or modified from any place in your global Python scope. Beyond that, the global statement can be used to modify global names from almost any place in your code, as you’ll see in The global Statement.

Modifying global names is generally considered bad programming practice because it can lead to code that is:

Difficult to debug: Almost any statement in the program can change the value of a global name.
Hard to understand: You need to be aware of all the statements that access and modify global names.
Impossible to reuse: The code is dependent on global names that are specific to a concrete program.
Good programming practice recommends using local names rather than global names. Here are some tips:

Write self-contained functions that rely on local names rather than global ones.
Try to use unique objects names, no matter what scope you’re in.
Avoid global name modifications throughout your programs.
Avoid cross-module name modifications.
Use global names as constants that don’t change during your program’s execution.

