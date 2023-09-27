# First Positive Number Missing

## Problem Description

Given an array of integers, find the smallest positive integer that is missing. For example:

### Example 1

Input: `arr = [2, 3, 7, 6, 8, -1, -10, 15]`

Output: `1`

### Example 2

Input: `arr = [2, 3, -7, 6, 8, 1, -10, 15]`

Output: `4`

### Example 3

Input: `arr = [1, 1, 0, -1, -2]`

Output: `2`

## Approach 1: Brute Force

### Solution Idea

Positive numbers start from 1 on the number scale. If the first missing positive number is `k`, then all the positive numbers from 1 to `k - 1` will be present in the array. The maximum possible missing positive number in an array of size `n` is `n + 1`.

### Code

```
for (let i = 1; i <=n+1; i++){
        let flag = true;
        for (let j = 0; j < n; j++){
            if (arr[j] === i){
                flag = false;
                break;
            }
        }
        if (flag) {
            return i;
        }
    }
```

* Note :- There is two loops in this question

### Time Complexity

The time complexity of this approach is O(n^2) because for each of the `n` positive integers, we potentially search through the entire array of size `n`.

### Space Complexity

The space complexity is O(1) as we do not use any additional data structures.

## Approach 2: Optimized

### Solution Idea

This approach optimizes the previous one by using a separate Boolean array to keep track of positive integers. We iterate through the input array, marking the positions of positive integers in the Boolean array. Then, we find the first unmarked position, which corresponds to the smallest missing positive integer.

### Code

```
function firstMissingPositiveApproach2(arr) {
    let hashTable = new Array(n + 2);
    hashTable.fill(0);

    for (let i = 0; i <n; i++){
        if (arr[i] > 0) {
            hashTable[arr[i]] = arr[i];
        }
    }
    for (let i = 1; i < n + 2; i++) { 
        if (hashTable[i] === 0) {
            return i;
        }
    }
}
```

### Time Complexity

The time complexity of this approach is O(n), where `n` is the size of the input array.

### Space Complexity

The space complexity is O(n) because of the Boolean array used to track positive integers.

#### Thank you :)