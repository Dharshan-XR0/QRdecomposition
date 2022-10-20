# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by

    ![eqn1](./ex4.jpg)

    ![eqn2](./ex6.jpg)

    ![eqn3](./ex3.jpg)

3.	Obtain the Q matrix   
    ![eqn4](./ex1.jpg)
4.	Construct the upper triangular matrix R
    ![eqn5](./ex2.jpg)



## Program:
### Gram-Schmidt Method
```python
Program to find 2-norm of a matrix.
Developed by: yourname DHARSHAN V
RegisterNumber: 22003103

import numpy as np
arr =np.array(eval(input()))
n,m=arr.shape
u=np.empty((n,m))
e=np.empty((n,m))
u[:,0]=arr[:,0]
e[:,0]=u[:,0]/np.linalg.norm(u[:,0])
for i in range(1,n):
    u[:,i]=arr[:,i]
    for j in range(i):
        u[:,i]-=(arr[:,i]@e[:,j])*e[:,j]
        e[:,i]=u[:,i]/np.linalg.norm(u[:,i])
R=np.zeros((n,m))
for i in range(n):
    for j in range(i,m):
        R[i,j]=arr[:,j]@e[:,i]
print(e)
print(R)


```

## Output

![output](/Ex8CR.png)

```
# Result

Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
