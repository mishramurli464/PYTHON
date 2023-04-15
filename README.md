# NUMPY
## why numpy
NumPy provides efficient storage   
It also provides better ways of handling data for processing  
It is fast   
It is easy to learn   
NumPy uses relatively less memory to store data   

## There are 5 general mechanisms for creating arrays:  

### 1)Conversion from other Python structures (e.g., lists, tuples)
'''{python}   
import numpy as np  
myarr = np.array([10,2,5,3],np.int8) #8 byte m/m management of 1d array  
print(myarr)  
myarr[0]  
myarr2 = np.array([[10,244,5,3]],np.int32)  
myarr2[0,1]  
'''   

### 2)Intrinsic numpy array creation objects (e.g., arange, ones, zeros, etc.   

3)Reading arrays from disk, either from standard or custom formats   
4)Creating arrays from raw bytes through the use of strings or buffers   
5)Use of special library functions (e.g., random)   
