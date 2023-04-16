# NUMPY
NumPy is a Python library that provides support for multi-dimensional arrays and matrices, along with a large collection of high-level mathematical functions   
## why numpy
NumPy provides efficient storage   
It also provides better ways of handling data for processing  
It is fast   
It is easy to learn   
NumPy uses relatively less memory to store data   

## There are 5 general mechanisms for creating arrays:  

### 1)Conversion from other Python structures (e.g., lists, tuples)
The simplest way to create a NumPy array is by passing a list to the numpy.array() function. For example:  
```py   
import numpy as np  
myarr = np.array([10,2,5,3],np.int8) #8 byte m/m management of 1d array  
print(myarr)  
myarr[0]  
myarr2 = np.array([[10,244,5,3]],np.int32) #32 byte m/m management of 2d array   
myarr2[0,1]  
```    


### 2)Creating an array with a specified data type:
```py  
a = np.array([1, 2, 3], dtype=np.float64)
print(a) #This creates a 1-dimensional array with three elements of data type float64.  
```

### 3)Creating a multi-dimensional array:
You can create multi-dimensional arrays in NumPy using nested lists. For example:  
```py  
b = np.array([[1, 2, 3], [4, 5, 6]])  
print(b) #This creates a 2-dimensional array with 2 rows and 3 columns.  
```
This creates a 2-dimensional array with 2 rows and 3 columns.  

### 4)Creating an array with a range of values:
NumPy provides a numpy.arange() function that creates an array with evenly spaced values within a given range. For example:  
```py  
c = np.arange(0, 10, 2)
print(c)
```  
This creates a 1-dimensional array with values ranging from 0 to 10 (exclusive) with a step size of 2.  

### 5)Creating an array with a specified shape:
You can create an array with a specified shape using the numpy.zeros() or numpy.ones() functions. For example:
``` py  
d = np.zeros((3, 3))
print(d)
```   
This creates a 2-dimensional array with 3 rows and 3 columns, initialized with zeros.  

#### numpy axix  
In NumPy, an axis refers to a particular dimension of a multi-dimensional array. NumPy functions often take an axis parameter that allows you to specify the dimension along which the operation should be applied.  
To understand the concept of NumPy axis, let's consider the following examples:  
**Example 1:**  
```py
import numpy as np
arr = np.array([[1, 2, 3], [4, 5, 6]])
print(arr.sum())  # Output: 21
``` 
Since we didn't specify an axis parameter, the sum() function summed all the elements in the array and returned the result 21.  

**Example 2:**   
```py   
import numpy as np
arr = np.array([[1, 2, 3], [4, 5, 6]])
print(arr.sum(axis=0))  # Output: [5 7 9]
```  
The output is a 1-dimensional array containing the sum of the elements in each column. 

**Example 3:**  
```py  
import numpy as np
arr = np.array([[1, 2, 3], [4, 5, 6]])
print(arr.sum(axis=1))  # Output: [ 6 15]
```  
The output is a 1-dimensional array containing the sum of the elements in each row.  

### Attributes  
Attributes are properties of an array that provide information about its shape, size, data type, and other metadata. They do not change the array itself but rather   provide information about it. Attributes are accessed using dot notation and do not require any arguments.  

**dtype**	  -->  Data-type of the array’s elements.  
**flags**	  -->   Information about the memory layout of the array.  
**flat**	  -->   A 1-D iterator over the array.  
**imag**	  -->   The imaginary part of the array.  
**real**	  -->  The real part of the array.  
**size**	  -->  Number of elements in the array.  
**itemsize**-->  Length of one array element in bytes.  
**nbytes**	--> Total bytes consumed by the elements of the array.  
**ndim**	  -->  Number of array dimensions.   
**shape**	  -->  Tuple of array dimensions.  
**strides**	-->  Tuple of bytes to step in each dimension when traversing an array.  
**ctypes**	-->  An object to simplify the interaction of the array with the ctypes module.  
**base**	  -->  Base object if memory is from some other object.  

### Methods  
methods are functions that are called on an array to perform specific operations or calculations on the array. They can modify the array or return a new array  
with the  results of the operation. Methods in NumPy are accessed using dot notation, followed by parentheses with arguments (if any) enclosed in them.  

**all([axis, out, keepdims])**	-->Returns True if all elements evaluate to True.  
**any([axis, out, keepdims]**)	-->Returns True if any of the elements of a evaluate to True.  
**argmax([axis, out])**	-->Return indices of the maximum values along the given axis.  
**argmin([axis, out])**	-->Return indices of the minimum values along the given axis of a.  
**argpartition(kth[, axis, kind, order])**	-->Returns the indices that would partition this array.  
**argsort([axis, kind, order])**	-->Returns the indices that would sort this array.  
**astype(dtype[, order, casting, subok, copy])**	-->Copy of the array, cast to a specified type.  
**byteswap([inplace])**	-->Swap the bytes of the array elements  
**choose(choices[, out, mode])**	-->Use an index array to construct a new array from a set of choices.    
**ravel([order])**	-->Return a flattened array.  
**repeat(repeats[, axis])**	-->Repeat elements of an array.  
**reshape(shape[, order])**	-->Returns an array containing the same data with a new shape.  
**resize(new_shape[, refcheck])**-->	Change shape and size of array in-place.  
**round([decimals, out])**	-->Return a with each element rounded to the given number of decimals.  
