___
1. Count how many binary strings of length `n` contain exactly `k` ones.
```
from math import comb
n = int(input("Enter the lenght of the string (n): "))
k = int(input("Enter the number of ones: "))

if 0 <= k <= n:
    count = comb(n,k)
    print("No. of binary strings: ",count)
else: 
    print("Invalid!!")
```

2. 