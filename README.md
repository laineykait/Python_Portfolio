# Python_Portfolio_Ray
This is the portfolio of Python code that I learned during BISC 4503-384

## Jupyter Notebooks 1 and 2
In this analysis, we learned how to operate Jupyter notebooks by manipulating Fortune 500 company data.

%matplotlib inline
import pandas as pd 
import matplotlib.pyplot as plt
import seaborn as sns
sns.set(style = "darkgrid")
 
df = pd.read_csv('/home/student/Desktop/classroom/myfiles/notebooks/fortune500.csv')
 
df.head()
 
