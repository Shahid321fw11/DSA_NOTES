# Encode the Message


The question is asking to return aaabbbcc to a3b3c2.

## Code

```
  let count = 1;
    let output = ''+str[0];
    let check = str[0];

    for (let i = 1; i < str.length; i++){
        if (str[i] == check) {
            count++;
        } else {
            output += count;
            output += str[i];
            check = str[i];
            count = 1;
        }
    }
    output += count
    return output;
```

## Time and Space Complexity.
* Time :- O(n)
* Space :- O(1)

### Explaination.
Self Explainale, Please see the code.

### Thanks :) 

