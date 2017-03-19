**447**. Number of Boomerangs  
Given n points in the plane that are all pairwise distinct, a "boomerang" is a tuple of points (i, j, k) such that the distance between i and j equals the distance between i and k (the order of the tuple matters).  
> [link](https://leetcode.com/problems/number-of-boomerangs/#/description)

```
public class Solution {
    public int numberOfBoomerangs(int[][] points) {
        int ans=0;
        HashMap<Integer, Integer> cal = new HashMap<Integer, Integer>();

        for(int[] i : points){
            for(int[] j : points){
                int dis = (i[1]-j[1])*(i[1]-j[1])+(i[0]-j[0])*(i[0]-j[0]);
                cal.put(dis,cal.containsKey(dis)?cal.get(dis)+1:1);
            }
            for(int val : cal.values()){
                ans+=val*(val-1);
            }
            cal.clear();
        }
        return ans;
    }
}

```
