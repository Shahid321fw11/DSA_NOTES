module.exports = { 
    //param A : string
    //return a strings

    solve : function(A){
        // function to check palindrome.
        function checkPalindrome(input){
            const reversedInput = input.split('').reverse().join('');
            return input === reversedInput;
        }
        // Function to increment a string representing a number
        function incrementString(str) {
            const len = str.length;
            let carry = 1;
            let result = '';
            for (let i = len - 1; i >= 0; i--) {
                const digit = parseInt(str[i]) + carry;
                carry = Math.floor(digit / 10);
                result = (digit % 10) + result;
            }
            if (carry > 0) {
                result = carry + result;
            }
            return result;
        }
        
        function reverseLeft(inp){
            let output = String(inp);
            const reversedInput = output.split('').reverse().join('');            
            return reversedInput;
        }
        
        let input = A;
        let check = checkPalindrome(input);
        if(check){
            // input = String(Number(input)+1);
            input = incrementString(input);
        }
        // odd or even
        let n = input.length;
        let flag = (n%2===0)?true:false;
        let numOfHalfEle = Math.floor(n / 2);
        // console.log(input,n,flag,numOfHalfEle)

        // for odd numbers of elements
        if(!flag){
            if(n===1){
                return input;
            }
            let left = Number(input.slice(0, numOfHalfEle));
            let mid = Number(input[numOfHalfEle]);
            let right = Number(input.slice(numOfHalfEle+1));
            let reverseOFLeft = reverseLeft(left);
            // console.log(numOfHalfEle,left,mid,right,reverseOFLeft)            
            let output = ""
            if(mid===9){
                left = left+1;
                reverseOFLeft = reverseLeft(left);
                mid = 0;
                output = String(left)+String(mid)+String(reverseOFLeft);
                return output;
            }
            else if(reverseOFLeft>right){
                if(right===0){
                    reverseOFLeft = String(left).split('').reverse().join('');
                }
                output = String(left)+String(mid)+String(reverseOFLeft);
                return output;
            }
            else{
                output = String(left)+String(mid+1)+String(reverseOFLeft);
                return output;
            }
        }else{
            let left = Number(input.slice(0, numOfHalfEle));
            let right = Number(input.slice(numOfHalfEle));
            let reverseOFLeft = reverseLeft(left);
            // console.log(left,right,reverseOFLeft,n,flag,numOfHalfEle)
            let output = ""
            if(reverseOFLeft>right){
                output = String(left)+String(reverseOFLeft);
                return output;
            }else{
                left = left+1;
                reverseOFLeft = reverseLeft(left);
                output = String(left)+String(reverseOFLeft);
                // console.log(left,reverseOFLeft,numOfHalfEle)
                return output;
            }
        }
    }
};