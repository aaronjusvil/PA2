Aaron Justine V. Sanga 2ECE-A
# PA2 - Numerical Python
In this Programming Assignment, we are asked to utilize basic codes and functions in the NumPy library in different situations

```import numpy as np``` is used in this PA as the first line of code. Using np, we are able to call on the numpy library and use its codes and functions

**1. Normalization Problem:** Create a random 5 x 5 ndarray and store it to variable X. Normalize X. Save your normalized
ndarray as X_normalized.npy

```
X = np.random.random((5,5)) #Generating an np array with randomized elements

Normalized_X = (X - np.mean(X))/np.std(X) #using the normalization formula by calling on functions

display('Random Array:', X) #prints Random Array

print('\n') #creates space between the two arrays when presented

display('Normalized Array:' , Normalized_X) #displays the normalized array

np.save('X_normalized.npy', Normalized_X) #Saving normalized array into a .npy file
```

**Code Description:** This code uses the ```np.random.random((5, 5))``` code to generate a random array, where ```((5, 5)) indicates its shape and size. This array is saved to a variable X. The formula for normalization is then used on the array, using ```np.mean(X)``` and ```np.std(X)``` as the element-wise mean and element-wise standard deviation respectively. The two arrays are presented as output:
```
'Random Array:'
array([[0.5145429 , 0.55026264, 0.51697057, 0.78519475, 0.39294007],
       [0.27812932, 0.24523979, 0.4468004 , 0.17724118, 0.46046243],
       [0.41358045, 0.43853758, 0.84528233, 0.32300998, 0.01091335],
       [0.14745217, 0.72897877, 0.05510303, 0.41404584, 0.59457067],
       [0.72782929, 0.24213202, 0.18048506, 0.83233656, 0.7637634 ]])

'Normalized Array:'
array([[ 0.29722332,  0.44652205,  0.30737031,  1.42847386, -0.21104318],
       [-0.69092066, -0.82838986,  0.01407823, -1.1126054 ,  0.07118176],
       [-0.12477206, -0.02045811,  1.67962344, -0.50333177, -1.80781015],
       [-1.23711532,  1.19350644, -1.62310938, -0.12282687,  0.63171746],
       [ 1.18870192, -0.84137951, -1.09904689,  1.62551368,  1.33889668]])
```
using the display() function. Finally, the normalized array is saved as a .npy file using ```np.save('X_normalized.npy', Normalized_X)```.

**2. Divisible by 3 Problem:** Create a 10x10 array of the squares of numbers from 1-100, and find all the elements divisible by 3. Save the result as div_by_3.npy.

```
arr = np.arange(1, 101, 1)#creates an array that stores numbers from 1-101, not including 101, with an interval of 1 per number

arr_squared = arr*arr #multiplies the array by itself, essentially squaring all elements in the array

arr10x10 = arr_squared.reshape(10,10) #reshapes the array into 10x10

div_by_3 = arr10x10[arr10x10%3==0] #getting all of the elements that have a 0 remainder when divided by 3, and assigning that array to a variable

display('Original Array: ', arr10x10) #Displays original 10x10 array

print('\n') #creates space between the two arrays when presented

display('Divisible by 3 Only: ', div_by_3) #Displays the array that has only the elements divisible by 3

np.save('div_by_3.npy', div_by_3) #Saving div_by_3 array into a .npy file
```
**Code Description:** First, an array of all numbers from 1-100 is created using the code ```arr = np.arange(1, 101, 1)``` where the range of elements is from 1-101 (not including 101), with an interval of 1 in between all numbers. ```arr_squared = arr*arr``` is used to create a new array, one that multiples the original array by itself element wise, essentially squaring all the elements, and assigning that to ```arr_squared```. The created array does not naturally have a 10x10 shape, so using ```arr_squared.reshape(10,10)```, the squared array is reshaped into a 10x10. Using ```arr10x10[arr10x10%3==0]```, we are able to get only those elements of the new squared 10x10 array that are divisible by 3, by testing the value of their remainder when divided by 3. All of those that have a 0 remainder is put into their own array named ```div_by_3```. Lastly, the original squared 10x10 array and the final array containing those divisible by 3 are presented:
```
'Original Array: '
array([[    1,     4,     9,    16,    25,    36,    49,    64,    81,
          100],
       [  121,   144,   169,   196,   225,   256,   289,   324,   361,
          400],
       [  441,   484,   529,   576,   625,   676,   729,   784,   841,
          900],
       [  961,  1024,  1089,  1156,  1225,  1296,  1369,  1444,  1521,
         1600],
       [ 1681,  1764,  1849,  1936,  2025,  2116,  2209,  2304,  2401,
         2500],
       [ 2601,  2704,  2809,  2916,  3025,  3136,  3249,  3364,  3481,
         3600],
       [ 3721,  3844,  3969,  4096,  4225,  4356,  4489,  4624,  4761,
         4900],
       [ 5041,  5184,  5329,  5476,  5625,  5776,  5929,  6084,  6241,
         6400],
       [ 6561,  6724,  6889,  7056,  7225,  7396,  7569,  7744,  7921,
         8100],
       [ 8281,  8464,  8649,  8836,  9025,  9216,  9409,  9604,  9801,
        10000]])

'Divisible by 3 Only: '
array([   9,   36,   81,  144,  225,  324,  441,  576,  729,  900, 1089,
       1296, 1521, 1764, 2025, 2304, 2601, 2916, 3249, 3600, 3969, 4356,
       4761, 5184, 5625, 6084, 6561, 7056, 7569, 8100, 8649, 9216, 9801])
```
using the ```display()``` function. Finally, the div_by_3 array is saved as a .npy file using np.save('div_by_3.npy', div_by_3).

