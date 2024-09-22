#Problem 15

Link : https://leetcode.com/problems/binary-search/description/

Name : Binary Search

Description : Implementation of Binary Search.

Difficulty : Leetcode easy

Complexity : O(LogN)

```java
class Solution {
    public int search(int[] nums, int target) {
        int s=0,e=nums.length-1;
        while(s<=e){
            int mid = s+(e-s)/2;
            if(nums[mid]==target){
                return mid;
            }else if(nums[mid]<target){
                s=mid+1;
            }else{
                e=mid-1;
            }
            
        }
        return -1;
        
    }
}
```

#Problem 16

Link : https://www.geeksforgeeks.org/problems/floor-in-a-sorted-array-1587115620/1?track=DSASP-Searching&amp%253BbatchId=154

Name : Floor in a Sorted Array

Description : To find the index value of the target value or if not found return its floor index.

Difficulty : GFG Easy

Complexity : O(Log N)

```java
class Solution {

    // Function to find floor of x
    // arr: input array
    // n is the size of array
    static int findFloor(long arr[], int n, long x) {
        int s =0;
        int e =n-1;
        int floorIndex = -1;
        while(s<=e){
            int mid = s+(e-s)/2;
            if(arr[mid] == x){
                
                return mid;
            }
            if(arr[mid]<x){
                floorIndex = mid;
                s = mid+1;
                
            }else
                e = mid-1;
                
        }
        return floorIndex;
    }
}
```