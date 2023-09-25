
# Rotate array

Given an array of integers arr[] of size N and an integer, the task is to rotate the array elements to the left by d positions.

## Example:

```bash

Input: 
arr[] = {1, 2, 3, 4, 5, 6, 7}, d = 2
Output: 3 4 5 6 7 1 2

Input: arr[] = {3, 4, 5, 6, 7, 1, 2}, d=2
Output: 5 6 7 1 2 3 4

```


### Approach 1
In this approach we can create two new array
one for left and one for right and in the end merge both.

I am taking both left and right because it can work with right shift also.
There is one more thing that we need to understand, we must take a modulus of k because, suppose that  the total number of element present in an array in 10 and the k is 15 then only total 5 rotation is placing at all. Wheather it is in right or left.

### Time and Space Complexity with this Approach.
Time_Complexity = O(n).
Space_Complexity = O(n).

### Approach 2
In this approach we can do this by shifting the element.
With this approach the time and space Complexity will reduce.

Time Complexity in the worst case will take O(n) and there is no other space that we are consuming.
### Time and Space Complexity
Time_Complexity = O(n)
Space_Complexity = O(1).


#### Thank you :)
