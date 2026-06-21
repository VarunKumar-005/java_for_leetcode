# Leetcode 1903
## Approach 
- iterate from the last of the string
- if the last digit is odd then it is the largest odd number
## Code
```java
class Solution {
    public String largestOddNumber(String num) {
        for(int i=num.length()-1;i>=0;i--){
            int a = num.charAt(i) - '0';
            if(a%2==1){
                return num.substring(0,i+1);
            }   
        }
        return "";
    }
}
```
