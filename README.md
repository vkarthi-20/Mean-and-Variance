#  Mean and variance of a discrete  distribution

# Aim : 

To find mean and variance of arrival of objects from the feeder using probability distribution

# Software required :  

Python and Visual components tool
# Theory:

The expectation or the mean of a discrete random variable is a weighted average of all possible
values of the random variable. The weights are the probabilities associated with the corresponding values. 
It is calculated as,

![image](https://user-images.githubusercontent.com/103921593/192938463-e34177f4-f188-48a0-bda2-8f6d1d660ed2.png)

The variance of a random variable shows the variability or the scatterings of the random variables.
It shows the distance of a random variable from its mean. It is calcualted as

![image](https://user-images.githubusercontent.com/103921593/192938695-99fedc01-34d5-4d36-84df-5880e766ed0c.png)

# Procedure :

1. Construct frequency distribution for the data

2. Find the  probability distribution from frequency distribution.

3. Calculate mean using 
   
   ![image](https://user-images.githubusercontent.com/103921593/192940431-03b81777-c54d-4286-b4f4-82dfe7666b4c.png)

4. Find  
   
      ![image](https://user-images.githubusercontent.com/103921593/192940255-2d9dd746-6875-4a6d-877b-6da6cdb96ab1.png)

5.  Calculate variance using 
  
      ![image](https://user-images.githubusercontent.com/103921593/192942852-913550a9-fabe-4a55-b956-0487b18bbd97.png)

# Program :
Name: KARTHI V
Reg no: 212225230130
```
import numpy as np

# Input: Enter the number of arrivals separated by space
L = [int(i) for i in input("Enter arrival data: ").split()]

N = len(L)
M = max(L)
X = []
f = []

# Counting frequency of each arrival
for i in range(M + 1):
    c = 0
    for j in range(N):
        if L[j] == i:
            c += 1
    f.append(c)
    X.append(i)

sf = np.sum(f)

# Calculating probability for each occurrence
p = [f[i] / sf for i in range(M + 1)]

# Mean of arrival (expected value)
mean = np.inner(X, p)

# Second moment (E[X²])
EX2 = np.inner(np.square(X), p)

# Variance and standard deviation
var = EX2 - mean**2
SD = np.sqrt(var)

# Printing X and p(x)
print("\nX\tp(x)")
for i in range(M + 1):
    if f[i] > 0:   # Only print arrivals that actually occurred
        print(f"{X[i]}\t{p[i]:.3f}")

print(f"\nThe Mean arrival rate is {mean:.3f}")
print(f"The Variance of arrival from feeder is {var:.3f}")
print(f"The Standard deviation of arrival from feeder is {SD:.3f}")

```
# Output : 

<img width="914" height="344" alt="image" src="https://github.com/user-attachments/assets/8e0fd7c7-d9d8-4c07-8ad1-35b423f2bdde" />

# Results :
The mean and variance of arrivals of objects from feeder using probability distribution are calculated.

https://github.com/vkarthi-20/Mean-and-Variance.git
