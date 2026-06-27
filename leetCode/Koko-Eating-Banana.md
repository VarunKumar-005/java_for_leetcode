# Leetcode koko - Eating Banana 
## Approach
- Find the greatest element
- set the low eating rate to 1 at an hour
- set the max eating rate to max element at an hour
- now keep on finding **`ceil value`** so that you return the exact minimum rate at which koko eats an banana per hour
## Code
``` java
class Solution {
    public int minEatingSpeed(int[] piles, int h) {
         Arrays.sort(piles);
        int max = piles[piles.length-1];
        int min =1;
        int mid =0;
        while(min<=max){
            mid = min + (max-min)/2;
            if(hrs(piles,mid,h)) {max = mid -1;}
            else{ min = mid+1;} 
        }
        return min;
    }
    boolean hrs(int piles[],int mid ,int h){
        long hour =0;
        for(int pile:piles){
            hour += pile / mid;
            if(pile % mid != 0) hour++;
        }
        return hour<=h;
    }
}
```
