# LeetCode -205
## Approach
- Initialise a hashmap for both variable
- put both the values of each index in fist one s1 , s2
- and make reverse filling like s2 , s1

### Code
```java
class Solution {
    public boolean isIsomorphic(String s, String t) {
        if(s.length() != t.length()) return false;
        HashMap<Character,Character> a = new HashMap<>();
        HashMap<Character,Character> b = new HashMap<>();
        for(int i=0;i<s.length();i++){
            char c1 =s.charAt(i);
            char c2 =t.charAt(i);
            
            if(a.containsKey(c1)){
                if(a.get(c1)!=c2){
                    return false;
                }
            }
                else{
                    a.put(c1,c2);
                }
                

            if(b.containsKey(c2)){
                if(b.get(c2)!= c1){
                    return false;
                }
            }
            else{
                b.put(c2,c1);
            }    
           
            }
            return true;
        }
        
    }

```
