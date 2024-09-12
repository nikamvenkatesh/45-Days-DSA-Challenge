# Problem 3
Link : https://leetcode.com/problems/check-if-array-is-sorted-and-rotated/description/

Name : Check if the array is sorted or not.

Description : Honestly, i was stuck in this question for really a long time.
only was able to find the easy and brute force solution like to compare the first element of the array with the second element and check if its smaller than the previous one.

But, then i remembered the concept of "Circular Queue" taught by "Kunal" where we do use MODULO for accessing the other fields also.

Difficulty : Leetcode easy

Complexity : O(N)

```java
class Solution {
    public boolean check(int[] nums) {
        int count = 0;
        for(int i=0; i< nums.length; i++){
            if(nums[i] > nums[(i+1) % nums.length])
                count++;
            if(count > 1)
                return false;
        }
        return true;
        
    }
}
```

#Problem 4
Link : https://leetcode.com/problems/remove-duplicates-from-sorted-array/description/

Name : Remove Duplicates from sorted array.

Description : Just to remove the dulpicate element from the sorted array.

Difficulty : Easy Leetcode

Complexity : O(N)

```java
class Solution {
    public int removeDuplicates(int[] nums) {
        int i=0,j=1;
        while(j<nums.length){
            if(nums[i]!=nums[j]){
                nums[i+1] = nums[j];
                i++;
            }
            j++;
        }
        return i+1;
    }
}
```