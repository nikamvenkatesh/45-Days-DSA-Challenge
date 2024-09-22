#Problem 21

Link : https://www.geeksforgeeks.org/problems/floor-in-a-sorted-array-1587115620/1?track=DSASP-Searching&amp%253BbatchId=154

Name : Floor in a Sorted Array.

Description : we are given with an target value, we have to return the index of the target value from the array, but if target is not found then return the floor of the target value.

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

#Problem 22 - kkQuestions

Link : https://leetcode.com/problems/search-in-rotated-sorted-array/

Name : Search in Rotated Sorted Array

Description : we have to search for the target element value in the sorted array but the twist is that the array is rotated.

Difficulty : Leetcode Medium

Complexity : O(Log N)

```java
class Solution {
    public int search(int[] nums, int target) {
        int pivot = pivot(nums);
        if(pivot == -1){
            return search (nums, target, 0, nums.length-1);
        }
        if(nums[pivot] == target){
            return pivot;
        }
        if(target >= nums[0]){
            return search(nums, target, 0, pivot-1);
        }else {
            return search(nums, target, pivot+1, nums.length-1);
        }
    }
    static int pivot(int []arr){
        int start = 0;
        int end = arr.length-1;
        while(start<=end){
            int mid = start + (end - start)/2;
            if(mid<end && arr[mid] >= arr[mid + 1]){
                return mid;
            }
            if(mid> start && arr[mid] < arr[mid-1]){
                return mid-1;
            } else if (arr[start]>=arr[mid]) {
                end = mid-1;
            }else{
                start = mid+1;
            }
        }
        return -1;
    }

    static int search(int  arr[], int target, int start, int end){
        while(start <= end){
            int mid = start + (end - start)/2;
            if(arr[mid] == target){
                return mid;
            } else if (arr[mid] > target) {
                end = mid-1;
            }else {
                start = mid + 1;
            }
        }
        return -1;
    }
}
```



To solve the medium and hard level problems of different data structures you need to have knowledge of different small concepts- like hashmap, sliding window, hashtable, two pointers, bit operations.