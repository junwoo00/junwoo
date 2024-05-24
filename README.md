# Number of cases where 3 of the given numbers become prime when added together - Python
---

### 1.Import itertools
```
from itertools import combinations
```

### 2.Create a function to determine prime numbers
- Create a function considering that a prime number is a number that has only 1 and itself as divisors. 
```
def prime_num(nums) :
  if nums < 2 :
    return False
  elif nums >= 2 :
    for i in range(2,nums+1) :
      for j in range(2,i) :
        if i % j == 0 :
          return False  
  return True 

```

### 3.Create solution function
- Use combinations(nums, 3) to create a combination of three numbers from the nums array. Find the sum of each combination and determine whether the sum is prime. To do this, we use the prime_num function. The sum of the combinations is prime. In this case, count is incremented by 1. Finally, the function returns count, which is the number of cases in which it becomes a prime number.
```
def solution(nums):
    count = 0
    for comb in combinations(nums, 3):
        if prime_num(sum(comb)):
            count += 1
    return count
  
```

### 4.Print result example
- Check the output with example values
```
nums = [1,2,7,6,4]
result = solution(nums)
print(result)
     
```
