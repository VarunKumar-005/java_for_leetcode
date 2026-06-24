# LeetCode -14
## Approach
- first initalise a prefix variable to the first element
- compare with **'startsWith'** function if false
- shrink the prefix

---

## Code
```java
class Solution {
    public String longestCommonPrefix(String[] strs) {
        String pre = strs[0];
        for(int i =1;i<strs.length;i++){
            while(!strs[i].startsWith(pre)){
                pre = pre.substring(0,pre.length()-1);
                if(pre.isEmpty())return "";
            }
        }
        return pre;
    }
}
```
