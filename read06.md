# [reading-note-401](https://mohammadsilwadi.github.io/reading-note-401/)

## Big O:  Random Module
+ The random module provides access to functions that support many operations. Perhaps the most important thing is that it allows you to generate random numbers.

| Function Name | Description |
| ---------------    | ----------- |
| choice() |	Returns a random item from a list, tuple, or string |
| choices() |	Returns multiple random elements from the list with replacement |
| sample() |	 Returns a particular length list of items chosen from the sequence |
| random() |	Generate random floating numbers |

##  Risk Analysis
Risk analysis is the process of assessing the likelihood of an adverse event occurring within the corporate, government, or environmental sector.

How to perform Risk Analysis?
There are three steps:

+ Searching the risk

+ Analyzing the impact of each individual risk

+ Measures for the risk identified

## Test Coverage

Like most aspects of programming, testing requires thoughtfulness. TDD is a very useful, but certainly not sufficient, tool to help you get good tests. If you are testing thoughtfully and well, I would expect a coverage percentage in the upper 80s or 90s. I would be suspicious of anything like 100% - it would smell of someone writing tests to make the coverage numbers happy, but not thinking about what they are doing.

The reason, of course, why people focus on coverage numbers is because they want to know if they are testing enough. Certainly low coverage numbers, say below half, are a sign of trouble. But high numbers don't necessarily mean much, and lead to ignorance-promoting dashboards. Sufficiency of testing is much more complicated attribute than coverage can answer. I would say you are doing enough testing if the following is true:

+ You rarely get bugs that escape into production, and
+ You are rarely hesitant to change some code for fear it will cause production bugs.