# Leet code Problems on Strings
## 1) LeetCode-1021
### Approach
- use an depth variable from 0 and an Sting Builder
- if the depth var > 0 then it is in the inner brackets
- increase depth count on '(' and decrease it on ')'
### Code
```java
class Solution {
    public String removeOuterParentheses(String s) {
        StringBuilder sc = new StringBuilder();
        int depth =0;
        for(int i =0;i<s.length();i++){
            char c = s.charAt(i);
            if(c=='('){
              if(depth>0) sc.append(c);
              depth++;  
            }
            else{
                depth--;
                if(depth>0) sc.append(c);  
            }
        }
        return sc.toString();
    }
}
```
