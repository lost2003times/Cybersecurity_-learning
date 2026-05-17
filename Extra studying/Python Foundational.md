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

2. Count binary strings of length n that do NOT contain consecutive 1s.
```
memo = {}

def count_strings(n):

    if n in memo:
        return memo[n]
    
    if n == 1:
        return 2
    
    if n == 2:
        return 3
    
    memo[n] = count_strings(n-1) + count_strings(n-2)

    return memo[n]

n = int(input("Enter the value of n:"))
print("The count is : ", count_strings(n))
```

3. Subset Sum Count
Given:
arr = [1,2,3,4,5]
Count subsets whose sum equals 7.
```
from itertools import combinations

arr = [1,2,3,4,5]
target = 5
count = 0
 
for i in range(len(arr) + 1):
    for subset in combinations(arr,i):
        if sum(subset) == target:
            print(subset)
            count += 1

print("/n Total subsets = ",count)
```

Works something like this : 
```
i = 0
    generate subsets of size 0

i = 1
    generate subsets of size 1

i = 2
    generate subsets of size 2

i = 3
    generate subsets of size 3
...
```
