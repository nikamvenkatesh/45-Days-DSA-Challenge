#Problem 27 --KKQuestions

Link : https://www.geeksforgeeks.org/problems/rotation4723/1

Name :Find Kth rotation

Description : We have to return the index value of the element from which the array is rotated.

Difficulty : GFG Easy

Complexity : O(Log N)

```java
class Solution {
    public int findKRotation(List<Integer> arr) {
        // Code here
        return pivot(arr)+1;
    }
    static int pivot(List<Integer> arr){
        int start = 0;
        int end = arr.size()-1;
        while(start<=end){
            int mid = start + (end - start)/2;
            if(mid<end && arr.get(mid) >= arr.get(mid+1)){
                return mid;
            }
            if(mid> start && arr.get(mid) < arr.get(mid-1)){
                return mid-1;
            } else if (arr.get(start)>=arr.get(mid)) {
                end = mid-1;
            }else{
                start = mid+1;
            }
        }
        return -1;
    }
}
```

#Problem 28 --KKQuestions

Link : https://leetcode.com/problems/find-minimum-in-rotated-sorted-array/

Name : Find Minimum in rotated Sorted array.

Description : Well the array is rotated, so the minimum value of the array will be next to the pivot element, So all we have to do is to return the pivot elements next index value.

Difficulty : Leetcode Medium

Complexity : O(Log N)

```java
class Solution {
    public int findMin(int[] nums) {
        int pivot = findPivot(nums);
        return nums[pivot+1];
    }
    static int findPivot(int [] nums){
        int start = 0;
        int end = nums.length-1;
        while(start <= end){
            int mid = start + (end-start)/2;
            if(mid<end && nums[mid]> nums[mid+1]){
                return mid;
            }else if(mid>start && nums[mid]< nums[mid-1]){
                return mid-1;
            }else if(nums[start]>= nums[mid]){
                end = mid-1;
            }else{
                start = mid+1;
            }
        }
        return -1;
    }
}
```