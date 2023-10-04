# Minimum Parentheses to Make a String Valid

## Problem Statement

You are given a string containing only two types of characters: '(' and ')'. Your task is to determine the minimum number of parentheses you need to add to the string in order to make it a valid sequence of parentheses.

A valid sequence of parentheses is one in which every open '(' parenthesis is followed by a closing ')' parenthesis, and the parentheses are properly nested within each other.

Write a function called `min_parentheses_to_make_valid(str: str) -> int` that takes the input string `str` and returns the minimum number of parentheses needed to make it valid.

## Code
```
 let balance = 0;
    let addition = 0;
    for (let i = 0; i < str.length-1; i++){
        if (str[i] === '(') {
            balance++;
        } else {
            if (balance === 0) {
                addition++;
            } else {
                balance--;
            }
        }
    }
    let output = balance+addition
    return output
```

## Explanation

- In the first example, the input string "()((()))" is already a valid sequence of parentheses. There is no need to add any more parentheses, so the function returns 0.

- In the second example, the input string ")((()" can be made valid by adding the following parentheses:
    - Add an opening '(' at the beginning to get "(())((()"
    - Add a closing ')' at the end to get "(())(()))"
    - Add a closing ')' at the beginning to get "(()())(()))"
    - The minimum number of parentheses needed is 3, and the function returns 3.

## Constraints

- You must implement the solution using Python.
- The input string contains only '(' and ')' characters.
- The input string may not be a valid sequence of parentheses initially.
- The function should have a time complexity of O(N), where N is the length of the input string.
- The function should have a space complexity of O(1) as it does not use any data structures that depend on the input size.