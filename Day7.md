#Problem 13
Link : https://leetcode.com/problems/two-sum/description/

Name : 2Sum

Description : we have to find two elements from the array which we add-up to give the sum equal to target value.

Difficulty : Leetcode Easy

Complexity : O(N*N)

```java
class Solution {
    public int[] twoSum(int[] nums, int target) {
        int ans[]=new int [2];

        for (int j=0;j<nums.length;j++){
            for(int i=j+1;i<nums.length;i++){
                if(nums[j]+nums[i]==target && i!=j){
                    ans[0]=j;
                    ans[1]=i;
                }
            }
        }
        return ans;
    }
}
```
Description : After discussing with sanskar we found the solution in O(N) complexity. here, we used the hashMap and stored the required complement of each element of the array with the target and simultaneously checked if the complement value of current index is equal to any element of the array.

```java
class Solution {
    public int[] twoSum(int[] nums, int target) {
        Map<Integer, Integer> numMap = new HashMap<>();
        int n = nums.length;

        for (int i = 0; i < n; i++) {
            int complement = target - nums[i];
            if (numMap.containsKey(complement)) {
                return new int[]{numMap.get(complement), i};
            }
            numMap.put(nums[i], i);
        }

        return new int[]{}; // No solution found
    }
}

```

#Problem 14
Link : https://leetcode.com/problems/majority-element/description/

Name : Majority Element 

Description : We have to find the element from the array that occures in the array more than (N/2) times.

Difficulty : Leetcode Easy

Complexity : O(N)

```java
class Solution {
    public int majorityElement(int[] nums) {
        int count=0;
        int ele=0;
        for(int i=0;i<nums.length;i++){
            if(count==0){
                ele=nums[i];
            }
            count=count + (nums[i]==ele?1:-1);
        }
        return ele;        
    }
}
```