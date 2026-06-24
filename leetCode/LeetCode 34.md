# LeetCode - 34
## Approach
- first use the ordinary Binary search
- if mid is found then we have to move left so store the ans then use **'right = m-1'**
- simlarly do for right then return ans

## Code
```java
class Solution {
    public int[] searchRange(int[] nums, int target) {
           int li =  binary(nums,target,true);
           int ri = binary(nums,target,false);
           int[] arr = {li,ri};
           return arr;
        }
            int binary(int[] nums,int target,boolean hi){
        int left =0;
        int right = nums.length -1;
        int mid  =0;
        int li =-1;
        while(left<= right ){
             mid = left + (right-left)/2;
            if(nums[mid] == target){
                li = mid;
                if(hi){
                    right = mid -1;
                }
                else{
                    left = mid+1;
                }
            }
            else if(nums[mid]<target){
                left = mid +1;
            }
            else{
                right = mid -1;
            }
            
        }
        return li;
    }
}

```
