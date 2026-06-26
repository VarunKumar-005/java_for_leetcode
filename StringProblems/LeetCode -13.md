# LeetCode -13
## Approach
- Put all the charectars in a HashMap and assign the values mannually
- now use the `get` method and the `string.charAt()` method to find the integer assigned to particual charectar
- now  `if(curent chars value < next charectar vaue)` then reduce the i th char value
- `else` increment the ith value to the resulatant variable

---

## Code
```java
class Solution {
    public int romanToInt(String s) {
        HashMap<Character,Integer> m = new HashMap<>();
        m.put('I',1);
        m.put('V',5);
        m.put('X',10);
        m.put('L',50);
        m.put('C',100);
        m.put('D',500);
        m.put('M',1000);
        int res =0 ;
        for(int i =0;i<s.length()-1;i++){
            if(m.get(s.charAt(i)) < m.get(s.charAt(i+1))){
                res -= m.get(s.charAt(i));
            }
            else{
                res +=m.get(s.charAt(i)); 
            }
        }
         return res + m.get(s.charAt(s.length()-1));
    }
}
```
