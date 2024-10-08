#Problem 17 --KKQuestions

Link : https://leetcode.com/problems/search-insert-position/description/

Name : Search Insert Position.

Description : To find the target value if not found, return the index value were it should be inserted.

Difficulty : Leetcode Easy.

Complexity : O(Log N)

```java
class Solution {
    public int searchInsert(int[] nums, int target) {
       int start=0;
       int end=nums.length-1;
       int mid =(start+(end-start)/2);
        if(target <nums[start]){
            return start;
        }
        if(target > nums[end]){
            return end+1;
        }
       while(start<=end){
           mid =(start+(end-start)/2);
           if(nums[mid]==target){
            return mid;
           }
           else if(target>nums[mid]){
               start=mid+1;
           }
           else{
               end=mid-1;
           }

        } 
       
        return start;

    }
}
```

#Problem 18 --KKQuestions

Link : https://leetcode.com/problems/find-first-and-last-position-of-element-in-sorted-array/

Name : Find First and Last Position of element in sorted array.

Description : the target value may be repeated so, we have to return the index values of its first and last occurence in the array.

Difficulty : Leetcode Medium

Complexity : O(Log N)

```java
class Solution {
    public int[] searchRange(int[] nums, int target) {
        int ans[] = {-1, -1};
        ans[0] = search(nums, target, true);
        if(ans[0]!=-1){
            ans[1] = search(nums, target, false);
        }
        return ans;
    }
    static int search(int nums[], int target, boolean startIndex){

        int ans = -1;

        int start = 0;
        int end = nums.length-1;
        while(start<= end){
            int mid = start + (end - start)/2;
            if(target > nums[mid]){
                start = mid+1;
            }else if(target < nums[mid]){
                end = mid-1;
            }else {
                ans = mid;
                if(startIndex){
                    end = mid -1;
                }else {
                    start = mid +1;
                }
            }

        }
        return ans;
    }
}
```