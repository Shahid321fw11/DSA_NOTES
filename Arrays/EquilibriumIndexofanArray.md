# Equilibrium Index of an Array

## Introduction

The equilibrium index of an array is an index such that the sum of elements at lower indexes is equal to the sum of elements at higher indexes. In other words, it's the index at which the cumulative sum of elements to the left of that index is equal to the cumulative sum of elements to the right of that index.

For example, consider the array `A[] = {-7, 1, 5, 2, -4, 3, 0}`. The equilibrium index is `3` because:

```
A[0] + A[1] + A[2] = A[4] + A[5] + A[6]
-7 + 1 + 5 = -4 + 3 + 0
```

If there is no equilibrium index in the array, the function should return `-1`.

## Code
```
if (a.length === 1) return 1; // Handle the case where the array has only one element, which is considered as an equilibrium index.
let total_point = 0;
let output = 0;
for (let i = 0; i < n; i++) {
    total_point += a[i]; // Calculate the total sum of all elements in the array.
}
let sum = a[0];
total_point -= a[0]; // Initialize 'sum' with the first element and update 'total_point' accordingly.
for (let i = 1; i < n; i++) {
    total_point -= a[i]; // Subtract the current element from 'total_point'.
    if (sum === total_point) {
        return i + 1; // If 'sum' is equal to 'total_point', return the equilibrium index (index + 1).
    } else {
        sum += a[i]; // If not, add the current element to 'sum'.
    }
}
return -1; // If no equilibrium index is found, return -1.

```

## Algorithm Explanation

The algorithm for finding the equilibrium index involves iterating through the array once, calculating the total sum of all elements, and then iterating through the array again to find the equilibrium index.

Here is a step-by-step explanation of the algorithm:

1. If the length of the input array `arr` is 1, return 0 (since the only element in the array is considered as an equilibrium index).

2. Calculate the total sum of all elements in the array `arr` and store it in the variable `total_point`.

3. Initialize two variables: `sum` to store the cumulative sum of elements to the left of the current index and `output` to store the equilibrium index.

4. Iterate through the array from left to right using a loop. For each element at index `i`, do the following:

   a. Subtract the current element `a[i]` from `total_point`. This represents the sum of elements to the right of the current index.

   b. Check if `sum` (the cumulative sum of elements to the left of the current index) is equal to `total_point` (the sum of elements to the right of the current index). If they are equal, set `output` to `i+1` and return `output` as the equilibrium index.

   c. If `sum` is not equal to `total_point`, add the current element `a[i]` to `sum` to update the cumulative sum of elements to the left.

5. If no equilibrium index is found during the iteration, return -1 to indicate that no equilibrium index exists.

## Time Complexity

The time complexity of this algorithm is O(n), where n is the length of the input array. This is because we iterate through the array twice, and each iteration takes linear time.
* Time Complexity = O(n)

## Space Complexity

The space complexity of this algorithm is O(1) because it uses a constant amount of additional space to store variables (`total_point`, `output`, `sum`) regardless of the size of the input array.
* Space Complexity = O(1)


## Testing and Corner Cases

Let's test the algorithm with some test cases and corner cases:

### Test Case 1:

Input: `A[] = {-7, 1, 5, 2, -4, 3, 0}`
Expected Output: `3`

### Test Case 2:

Input: `A[] = {1, 2, 3}`
Expected Output: `-1`

### Test Case 3:

Input: `A[] = {1}`
Expected Output: `0`

### Test Case 4:

Input: `A[] = {0, 0, 0, 0, 0}`
Expected Output: `0`

### Test Case 5:

Input: `A[] = {1, -1, 1, -1, 1}`
Expected Output: `2`

The algorithm handles both small and large input arrays efficiently and correctly identifies the equilibrium index when it exists. It also returns -1 when there is no equilibrium index in the array.