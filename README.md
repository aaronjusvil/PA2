Aaron Justine V. Sanga 2ECE-A
# PA2 - Numerical Python
In this Programming Assignment, we are asked to utilize basic codes and functions in the NumPy library in different situations

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
array([[0.41900645, 0.28446039, 0.13441434, 0.23481237, 0.79814642],
       [0.13724286, 0.25604867, 0.06853768, 0.94714114, 0.6256771 ],
       [0.29346968, 0.90295031, 0.24385552, 0.35716048, 0.23939227],
       [0.93025051, 0.71895823, 0.94355482, 0.39612829, 0.09441483],
       [0.61187389, 0.11851098, 0.76529925, 0.38322747, 0.17788595]])

'Normalized Array:'
array([[-0.08247783, -0.53932889, -1.04881012, -0.70790868,  1.20489158],
       [-1.03920588, -0.63580086, -1.27249426,  1.71080303,  0.61927218],
       [-0.50873783,  1.56075313, -0.67720267, -0.29247579, -0.69235765],
       [ 1.65345092,  0.93600815,  1.69862569, -0.16016063, -1.18462842],
       [ 0.57240337, -1.10280994,  1.09335906, -0.20396533, -0.9012023 ]])
```
using the display() function. Finally, the normalized array is saved as a .npy file using ```
