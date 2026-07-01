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
 


## Python Fundamentals
In this analysis, we learned how to manipulate variables in Python by using integers and measurements

# Any python interpreter can be used as a calculator
3 + 5 * 4
 
23
 
# Lets save a value to a variable 
weight_kg = 60
 
print(weight_kg)
 
60
 
# weight0 = valid
# 0weight = invalid
# weight and Weight are different 
 
# Types of data
# There are three common types of data
# Integer numbers 
# floating point numbers
# Strings
 
# Floating point number
weight_kg = 60.3
 
# String comprised of letters
patient_name = "John Smith"
 
# String comprised of numbers
patient_id = '001'
 
# Use variables in python
 
weight_lb = 2.2 * weight_kg
 
print(weight_lb)
 
132.66
 
# Lets add a prefix to our patient id
 
patient_id = 'inflam_' + patient_id
 
print(patient_id)
 
inflam_inflam_inflam_inflam_inflam_inflam_inflam_inflam_001
 
# Lets combine print statements
 
print(patient_id, 'weight in kilograms:',weight_kg)
 
inflam_inflam_inflam_inflam_inflam_inflam_inflam_inflam_001 weight in kilograms: 60.3
 
# we can call a function inside another function
 
print(type(60.3))
 
print(type(patient_id))
 
<class 'float'>
<class 'str'>
 
# We can also do calculations inside the print function
 
print('weight in lbs:',2.2 * weight_kg)
 
weight in lbs: 132.66
 
print(weight_kg)
 
60.3
 
