#Problem 23 --KKQuestions

Link : https://www.naukri.com/code360/problems/ceiling-in-a-sorted-array_1825401?leftPanelTabValue=PROBLEM

Name :Ceil the Floor

Description : To find the Floor and the ceil of the target value.

Difficulty : Code360 codingNinja Moderate.

Complexity : O(Log N)

```java
import java.util.* ;
import java.io.*; 

public class Solution {
    public static int[] getFloorAndCeil(int[] a, int n, int x) {
      // Wriute your code here.
      int ans [] = {-1, -1};
      int s = 0;
      int e = n-1;
      while(s<=e){
        int mid = s+(e-s)/2;
        if(a[mid] == x){
          ans[0] = a[mid];
          ans[1] = a[mid];
          return ans;
        }
        else if(a[mid]> x){
          ans[1] = a[mid];
          e = mid-1;
        }else{
          ans[0] = a[mid];
          s = mid+1;
        }
      }
      return ans;
    }
    
}
```

#Problem 24 --KKQuestions

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