# NumPy Examples

> NumPy is the fundamental package for scientific computing with Python. It contains among other things:
> 
> - a powerful N-dimensional array object
> - useful linear algebra, Fourier transform, and random number capabilities

- [NumPy Quickstart Tutorial](https://numpy.org/devdocs/user/quickstart.html)

matrix vs. array

- "matrix" typically refers to a 2d array, whereas an "array" can be n-dimensional
- array operations are different to matrix operations. [stackoverflow answer](https://stackoverflow.com/questions/29020815/what-is-the-difference-between-matrix-and-array/29023031#29023031)
- [Wikipedia: Matrix (Mathematics)](https://en.wikipedia.org/wiki/Matrix_(mathematics))


```python
import numpy as np
```

### Create an array


```python
np.arange(8)
```




    array([0, 1, 2, 3, 4, 5, 6, 7])



### Create an 3x2 array


```python
np.arange(8).reshape(4,2)
```




    array([[0, 1],
           [2, 3],
           [4, 5],
           [6, 7]])



### Create a column vector


```python
np.arange(4).reshape(4,1)
```




    array([[0],
           [1],
           [2],
           [3]])



## create vetor with random numbers


```python
np.random.random(4)
```




    array([0.23624456, 0.54476079, 0.40378923, 0.00776239])




```python
np.random.random((2,3))
```




    array([[0.54265357, 0.6840049 , 0.31545199],
           [0.31731065, 0.25964965, 0.45016353]])



random number between 1 and 10 (see [Python Docs](https://docs.python.org/2/library/random.html))


```python
np.random.randint((10, 10, 10, 10))
```




    array([1, 5, 7, 7])



### Matrix Product


```python
v = np.arange(4).reshape(4,1)
v
```




    array([[0],
           [1],
           [2],
           [3]])




```python
h = np.arange(3)
h
```




    array([0, 1, 2])




```python
v * h
```




    array([[0, 0, 0],
           [0, 1, 2],
           [0, 2, 4],
           [0, 3, 6]])



### Multimatrix multiplication
Mind that the vertical matrix column number has to match the horrizontal matrix row number.



```python
A = np.arange(8).reshape(4,2)
A
```




    array([[0, 1],
           [2, 3],
           [4, 5],
           [6, 7]])



nicer output when using `print()`


```python
print(A)
```

    [[0 1]
     [2 3]
     [4 5]
     [6 7]]



```python
B = np.arange(8).reshape(2,4)
print(B)
```

    [[0 1 2 3]
     [4 5 6 7]]



```python
C = B.dot(A)
print(C)
```

    [[28 34]
     [76 98]]


another way to write the `dot` operator


```python
D = B @ A
print(D)
```

    [[28 34]
     [76 98]]



```python
E = A * B
print(E)
```


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    <ipython-input-67-f24246073c0a> in <module>
    ----> 1 E = A * B
          2 print(E)


    ValueError: operands could not be broadcast together with shapes (4,2) (2,4) 


### Array with explicit complex numbers


```python
i = np.array( [ [1,2], [3,4] ], dtype=complex )
i
```




    array([[1.+0.j, 2.+0.j],
           [3.+0.j, 4.+0.j]])




```python
print(i)
```

    [[1.+0.j 2.+0.j]
     [3.+0.j 4.+0.j]]

