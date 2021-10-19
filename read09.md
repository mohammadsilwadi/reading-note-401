# [reading-note-401](https://mohammadsilwadi.github.io/reading-note-401/)

##      Dunder Methods
special methods are a set of predefined methods you can use to enrich your classes. They are easy to recognize because they start and end with double underscores, for example `__init__` or `__str__.`
Dunder methods let you emulate the behavior of built-in types. For example, to get the length of a string you can call len('string'). But an empty class definition doesn’t support this behavior out of the box:

`class NoLenSupport:`
    `pass`

`>>> obj = NoLenSupport()`
`>>> len(obj)`
`TypeError: "object of type 'NoLenSupport' has no len()"`

`To fix this, you can add a __len__ dunder method to your class:`

`class LenSupport:`
`    def __len__(self):`
`        return 42`

`>>> obj = LenSupport()`
`>>> len(obj)`
`42`

Object Representation:` __str__, __repr__`

It’s common practice in Python to provide a string representation of your object for the consumer of your class (a bit like API documentation.) There are two ways to do this using dunder methods:

+ ` __repr__`: The “official” string representation of an object. This is how you would make an object of the class. The goal of` __repr__` is to be unambiguous.
+ `__str__`: The “informal” or nicely printable string representation of an object. This is for the enduser.
## Statistics - Probability
 What is probability?

At the most basic level, probability seeks to answer the question, “What is the chance of an event happening?” An event is some outcome of interest. To calculate the chance of an event happening, we also need to consider all the other events that can occur. The quintessential representation of probability is the humble coin toss. In a coin toss the only events that can happen are:

+  Flipping a heads
+   Flipping a tails
 ### From statistics to probability

Our data will be generated by flipping a coin 10 times and counting how many times we get heads. We will call a set of 10 coin tosses a trial. Our data point will be the number of heads we observe. We may not get the “ideal” 5 heads, but we won’t worry too much since one trial is only one data point. If we perform many, many trials, we expect the average number of heads over all of our trials to approach the 50%. The code below simulates 10, 100, 1000, and 1000000 trials, and then calculates the average proportion of heads observed. Our process is summarized in the image below as well. 
- ![Big O ](https://i.imgur.com/GtbawRt.jpg)

### Normal distribution
Normal distributions
are important in statistics and are often used in the natural and social sciences to represent real-valued random variables whose distributions are not known.[3][4] Their importance is partly due to the central limit theorem. It states that, under some conditions, the average of many samples (observations) of a random variable with finite mean and variance is itself a random variable—whose distribution converges to a normal distribution as the number of samples increases. Therefore, physical quantities that are expected to be the sum of many independent processes, such as measurement errors, often have distributions that are nearly normal.
[ For more click here ](https://en.wikipedia.org/wiki/Normal_distribution)
#### Three Sigma Rule

The Three Sigma rule, also known as the empirical rule or 68-95-99.7 rule, is an expression of how many of our observations fall within a certain distance of the mean. Remember that the standard deviation (a.k.a. “sigma”) is the average distance an observation in the data set is from the mean. The Three Sigma rule dictates that given a normal distribution, 68% of your observations will fall between one standard deviation of the mean. 95% will fall within two, and 99.7% will fall within three. A lot of complicated math goes into the derivation of these values, and as such, is out of the scope of this article. The key takeaway is to know that the Three Sigma Rule enables us to know how much data is contained under different intervals of a normal distribution. The picture below is a great summary of what the Three Sigma Rule represents.
- ![Big O ](https://i.imgur.com/Mt3RyE0.png)
We’ll connect these concepts back to our wine data. As a sommelier, we’d like to know with high confidence that Chardonnay and Pinot Noir are more popular than the average wine. We have many thousands of wine reviews, so by Central Limit Theorem, the average score of these reviews should line up with a so-called “true” representation of the wine’s quality (as judged by the reviewer). Although the Three Sigma rule is a statement of how much of your data falls within known values, it is also a statement of the rarity of extreme values. Any value that is more than three standard deviations away from the mean should be treated with caution or care. By taking advantage of the Three Sigma Rule and the Z-score, we’ll finally be able to prescribe a value to how likely Chardonnay and Pinot Noir are different from the average wine. 
