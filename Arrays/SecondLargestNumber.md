
# Second Largest Number

Given an array of integers, our task is to write a program that efficiently finds the second-largest element present in the array. 

## Example:

```bash

Input: arr[] = {12, 35, 1, 10, 34, 1}
Output: The second largest element is 34.
Explanation: The largest element of the 
array is 35 and the second 
largest element is 34

Input: arr[] = {10, 5, 10}
Output: The second largest element is 5.
Explanation: The largest element of 
the array is 10 and the second 
largest element is 5

Input: arr[] = {10, 10, 10}
Output: The second largest does not exist.
Explanation: Largest element of the array 
is 10 there is no second largest element
```


### Approach 1
In this Approach we will use two variables
```bash
let first_largest_number = Math.max(arr[0],arr[1])
let second_largest_number = Math.min(arr[0],arr[1]);
```

Then there will be 2 loops,
In first loop we will find first largest number, with condition if arr[i] > first_largest_number

```bash
if(arr[i]>first_largest_number) first_largest_number = arr[i];

```

with this we will find first largest number and then in second loop we will find second_largest_number with condition if 
```bash
if(arr[i]<first_largest_number && arr[i]>second_largest_number)
    second_largest_number = arr[i];
```

with this Approach we will get output.

### Time and Space Complexity with this Approach.
Time_Complexity = O(n)+O(n) = 2 * O(n) = O(n).
Space_Complexity =  O(1)+O(1) = 2 * O(1) = O(1).

As 2 work as a constant.


### Approach 2
Approach 1st can be optimised with Time_Complexity.

In new Approach we can do the same with one loop.

Then the condition will change as.

```
for(let i=0;i<n;i++){
    if (arr[i] > first_largest_number) {
        second_largest_number=first_largest_number;
        first_largest_number = arr[i];
        } else if{
            (arr[i] > second_largest_number && arr[i] !== first_largest_number){
                second_largest_number = arr[i]
            }
        }
    }
}
```
In this approach we taking two condition 1st, if arr[i]> first_largest_number then changing the value of second_largest_number = first_largest_number and first_largest_number = arr[i].
There is one more case what if we counter some element which is lesser than first_largest_number and greater then second_largest_number, for this we are doing 
if arr[i] > second_largest_number && arr[i] !== first_largest_number than we change the value of second_largest_number = arr[i];

### Time and Space Complexity
Time_Complexity = O(n).
Space_Complexity =  O(1)+O(1) = 2 * O(1) = O(1).

