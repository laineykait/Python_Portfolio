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


## Analyzing Patient Data Pts 1 and 2
In this analysis, we learned how to load and print patient data to view the max, min, and mean inflammation data

import numpy
 
numpy.loadtxt(fname = 'inflammation-01.csv', delimiter = ',')
 
array([[0., 0., 1., ..., 3., 0., 0.],
       [0., 1., 2., ..., 1., 0., 1.],
       [0., 1., 1., ..., 2., 1., 1.],
       ...,
       [0., 1., 1., ..., 1., 1., 1.],
       [0., 0., 0., ..., 0., 2., 0.],
       [0., 0., 1., ..., 1., 1., 0.]])
 
data = numpy.loadtxt(fname = 'inflammation-01.csv', delimiter = ',')
 
print(data)
 
[[0. 0. 1. ... 3. 0. 0.]
 [0. 1. 2. ... 1. 0. 1.]
 [0. 1. 1. ... 2. 1. 1.]
 ...
 [0. 1. 1. ... 1. 1. 1.]
 [0. 0. 0. ... 0. 2. 0.]
 [0. 0. 1. ... 1. 1. 0.]]
 
print(type(data))
 
<class 'numpy.ndarray'>
 
print(data.shape)
 
(60, 40)
 
print('first value in data:', data[0,0])
 
first value in data: 0.0
 
print('middle value in data:', data[29,19])
 
middle value in data: 16.0
 
print(data[0:4, 0:10])
 
[[0. 0. 1. 3. 1. 2. 4. 7. 8. 3.]
 [0. 1. 2. 1. 2. 1. 3. 2. 2. 6.]
 [0. 1. 1. 3. 3. 2. 6. 2. 5. 9.]
 [0. 0. 2. 0. 4. 2. 2. 1. 6. 7.]]
 
small = data[:3, 36:]
 
print('small is:')
 
small is:
 
print(small)
 
[[2. 3. 0. 0.]
 [1. 1. 0. 1.]
 [2. 2. 1. 1.]]
 
# Let us use a numpy function
 
print(numpy.mean(data))
 
6.14875
 
maxval, minval, stdval = numpy.amax(data), numpy.amin(data), numpy.std(data)
 
 
print(maxval)
print(minval)
print(stdval)
 
20.0
0.0
4.613833197118566
 
maxval = numpy.amax(data)
minval = numpy.amin(data)
stdval = numpy.std(data)
 
print(maxval)
print(minval)
print(stdval)
 
20.0
0.0
4.613833197118566
 
print('maximum inflammation:', maxval)
print('minimum inflammation:', minval)
print('standard deviation:', stdval)
 
maximum inflammation: 20.0
minimum inflammation: 0.0
standard deviation: 4.613833197118566
 
# Sometimes we want to look at variation in statistical values, such as maximum inflammation per patient,
# or average from day one.
 
patient_0 = data[0, :] # 0 on the first axis(rows), everything on the second (columns)
 
print('maximum inflammation for patient 0:', numpy.amax(patient_0))
 
maximum inflammation for patient 0: 18.0
 
print('maximum inflammation for patient 2:', numpy.amax(data[2,:]))
 
maximum inflammation for patient 2: 19.0
 
print(numpy.mean(data, axis = 0))
 
[ 0.          0.45        1.11666667  1.75        2.43333333  3.15
  3.8         3.88333333  5.23333333  5.51666667  5.95        5.9
  8.35        7.73333333  8.36666667  9.5         9.58333333 10.63333333
 11.56666667 12.35       13.25       11.96666667 11.03333333 10.16666667
 10.          8.66666667  9.15        7.25        7.33333333  6.58333333
  6.06666667  5.95        5.11666667  3.6         3.3         3.56666667
  2.48333333  1.5         1.13333333  0.56666667]
 
print(numpy.mean(data, axis = 0).shape)
 
(40,)
 
print(numpy.mean(data, axis =1))
 
[5.45  5.425 6.1   5.9   5.55  6.225 5.975 6.65  6.625 6.525 6.775 5.8
 6.225 5.75  5.225 6.3   6.55  5.7   5.85  6.55  5.775 5.825 6.175 6.1
 5.8   6.425 6.05  6.025 6.175 6.55  6.175 6.35  6.725 6.125 7.075 5.725
 5.925 6.15  6.075 5.75  5.975 5.725 6.3   5.9   6.75  5.925 7.225 6.15
 5.95  6.275 5.7   6.1   6.825 5.975 6.725 5.7   6.25  6.4   7.05  5.9  ]
 



## Analyzing Patient Data Pt. 3
In this analysis, we continued manipulating inflammation patient data and created graphs from the mean, max, and min data.

import numpy
data = numpy.loadtxt(fname= 'inflammation-01.csv', delimiter = ',')
 
# Heat map of patient inflammation
import matplotlib.pyplot
image = matplotlib.pyplot.imshow(data)
matplotlib.pyplot.show()
 
png

# Average inflammation over time
 
ave_inflammation = numpy.mean(data, axis = 0)
ave_plot = matplotlib.pyplot.plot(ave_inflammation)
matplotlib.pyplot.show()
 
png

max_plot = matplotlib.pyplot.plot(numpy.amax(data, axis = 0))
matplotlib.pyplot.show()
 
png

min_plot = matplotlib.pyplot.plot(numpy.amin(data, axis = 0))
matplotlib.pyplot.show()
 
png

fig = matplotlib.pyplot.figure(figsize = (10.0, 3.0))
 
axes1 = fig.add_subplot(1, 3, 1)
axes2 = fig.add_subplot(1, 3, 2)
axes3 = fig.add_subplot(1, 3, 3)
 
axes1.set_ylabel('average')
axes1.plot(numpy.mean(data, axis = 0))
 
axes2.set_ylabel('max')
axes2.plot(numpy.amax(data, axis = 0))
 
axes3.set_ylabel('min')
axes3.plot(numpy.amin(data, axis = 0))
 
fig.tight_layout()
 
matplotlib.pyplot.savefig('inflammation.png')
matplotlib.pyplot.show()
 
png

 
 
 
