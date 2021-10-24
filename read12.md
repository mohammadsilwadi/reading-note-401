# [reading-note-401](https://mohammadsilwadi.github.io/reading-note-401/)

###   Pandas 
Pandas is mainly used for data analysis. Pandas allows importing data from various file formats such as comma-separated values, JSON, SQL, and Microsoft Excel. Pandas allows various data manipulation operations such as merging, reshaping, selecting, as well as data cleaning, and data wrangling features.
- ![ ](https://media.geeksforgeeks.org/wp-content/uploads/finallpandas.png)

`import numpy as np`

`import pandas as pd`
## Object creation



Creating a Series by passing a list of values, letting pandas create a default integer index:

`s = pd.Series([1, 3, 5, np.nan, 6, 8])`

## Viewing data
`df.head()`