
# Non-decreasing Array

## Problem Description

Given an array `nums` with `n` integers, your task is to check if it could become non-decreasing by modifying at most one element.

### Definition

An array is considered non-decreasing if, for every pair of adjacent elements `nums[i]` and `nums[i+1]`, it holds that `nums[i] <= nums[i + 1]` for every `i` in the range `0 <= i <= n - 2`.

## Examples

#### Example 1:

**Input:**

```
nums = [4, 2, 3]
```

**Expected Output:**

```
true
```

**Explanation:**

In this case, we start with the array `[4, 2, 3]`. To make it non-decreasing, we can modify the `4` to `2`, resulting in `[2, 2, 3]`. Thus, it is possible to make the array non-decreasing by modifying at most one element.

#### Example 2:

**Input:**

```javascript
nums = [4, 2, 1]
```

**Expected Output:**

```
false
```

**Explanation:**

In this case, we start with the array `[4, 2, 1]`. No single modification can make this array non-decreasing since both `2` should be greater than or equal to `4` and `1` should be greater than or equal to `2`. Modifying any single element won't resolve both issues.

## Additional Examples

#### Example 3:

**Input:**

```javascript
nums = [4, 5, 7, 2, 9]
```

**Expected Output:**

```
true
```

#### Example 4:

**Input:**

```javascript
nums = [4, 8, 7, 9]
```

**Expected Output:**

```
true
```

#### Example 5:

**Input:**

```javascript
nums = [3, 4, 2, 3]
```

**Expected Output:**

```
false
```

## Solution

To solve this problem, you can use the following JavaScript code:

```javascript
let n = nums.length;
let count = 0;

for (let i = 1; i < n; i++) {
    if (nums[i] < nums[i - 1]) {
        count++;
        if (count > 1) {
            return false;
        }
        if (i == 1 || nums[i - 2] <= nums[i]) {
            nums[i - 1] = nums[i];
        } else {
            nums[i] = nums[i - 1];
        }
    }
}
return true;
```

## Test Cases

### Test Case 1: `nums = [4, 5, 7, 2, 9]`

- **Input:** `[4, 5, 7, 2, 9]`
- **Expected Output:** `true`
- **Explanation:**

    - In this case, we start with the array `[4, 5, 7, 2, 9]`.
    - To make it non-decreasing, we can modify the `2` to `7`, resulting in `[4, 5, 7, 7, 9]`.
    - So, it is possible to make the array non-decreasing by modifying at most one element.

### Test Case 2: `nums = [4, 8, 7, 9]`

- **Input:** `[4, 8, 7, 9]`
- **Expected Output:** `true`
- **Explanation:**

    - In this case, we start with the array `[4, 8, 7, 9]`.
    - To make it non-decreasing, we can modify the `8` to `7`, resulting in `[4, 7, 7, 9]`.
    - So, it is possible to make the array non-decreasing by modifying at most one element.

### Test Case 3: `nums = [3, 4, 2, 3]`

- **Input:** `[3, 4, 2, 3]`
- **Expected Output:** `false`
- **Explanation:**

    - In this case, we start with the array `[3, 4, 2, 3]`.
    - No single modification can make this array non-decreasing because there are two issues here. The `2` should be greater than or equal to `4`, and the second `3` should be greater than or equal to `2`.
    - Modifying any single element won't resolve both issues.
    - Therefore, it is impossible to make the array non-decreasing by modifying at most one element.

---

These explanations illustrate the expected output for the provided test cases and demonstrate how the code determines if it's possible to make the given array non-decreasing with at most one modification.

### Notes

- We can only change `arr[i]` or `arr[i-1]` based on the condition.
- If `arr[i-2] <= arr[i]`, then `arr[i-1] = arr[i]`.
- Otherwise, `arr[i] = arr[i-1]`.

One corner case is when there are only three elements in the array. We use the condition `i == 1 || nums[i - 2] <= nums[i]` to satisfy the output.
```

This revised README.md should be more understandable and properly formatted for your use.