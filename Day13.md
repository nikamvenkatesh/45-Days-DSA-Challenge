#Problem 25 --KKQuestions

Link : https://www.geeksforgeeks.org/problems/number-of-occurrence2259/1

Name :Find the number of occurance.

Description : all we have to do is to find the occurance of the number in the array. we can calculate that by finding the first occurance index value and last occurance index value and then returning it.

Difficulty : GFG Medium

Complexity : O(Log N)

```java

class Solution {
    int count(int[] arr, int n, int x) {
        if (x < arr[0] || x > arr[n - 1]) 
            return 0;

        int first = FindFirst(arr, n, x);
        if (first == -1)  // If x is not found, return 0
            return 0;

        int last = FindLast(arr, n, x);
        return (last - first + 1); 
    }
    int FindFirst(int [] arr, int n, int x){
        int s =0;
        int e =n-1;
        int ans = -1;
        while(s<=e){
            int mid = s+(e-s)/2;
            if(arr[mid] == x){
                ans =mid;
                e =mid-1;
            }else if(arr[mid]<x)
                s =mid+1;
            else
                e =mid-1;
        }
        return ans;
    }
    int FindLast(int [] arr, int n, int x){
        int s =0;
        int e =n-1;
        int ans = -1;
        while(s<=e){
            int mid = s+(e-s)/2;
            if(arr[mid] == x){
                ans =mid;
                s =mid+1;
            }else if(arr[mid]<x)
                s =mid+1;
            else
                e =mid-1;
        }
        return ans;
    }
}
```

#Problem 25 --KKQuestions

Link : https://leetcode.com/problems/search-in-rotated-sorted-array/description/

Name : Search in Rotated Sorted Array

Description : To search for the target value in the rotated sorted array. We can simply find the index value of the pivot element and then search for the target in either part of the array(either left or right side of the pivot element).

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