#Problem 5
Link : https://leetcode.com/problems/rotate-array/submissions/1388894781/

Name : Rotate Array

Description : To rotate the array k times. from the right side.
Approch of mine
    1. I thought of the following solution which did solved the Question but had the Issue of "Time Limit Exceeding".

    Complexity: O(N*K)

```java
    k = k%nums.length;
        for (int i=0;i<k;i++){
            int temp = nums[nums.length-1];

            for(int j=nums.length-1;j>0;j--){
                nums[j] = nums[j-1];
            }
            nums[0] = temp;
        }
```


but, as always watched the solution.

Difficulty : Leetcode Medium

Complexity : O(N) - Max.

```java
class Solution {
    public void rotate(int[] nums, int k) {
        int n = nums.length;
        k = k % n;
        int[] temp = new int[k];
        
        for (int i = 0; i < k; i++) {
            temp[i] = nums[n - k + i];
        }
           
        for (int i = n - 1; i >= k; i--) {
            nums[i] = nums[i - k];
        }
        
        for (int i = 0; i < k; i++) {
            nums[i] = temp[i];
        }

    }
}
```

Another Most Optimal solution with...
Time Complexity : O(2N)
Space Complexity : O(1)
Firstly reverse the array from start index to kth index,
then from kth index to length-1 index and at last,
reverse the whole array all at once.

```java
class Solution {
    public void rotate(int[] nums, int k) {
        k = k % nums.length;  // Handle cases where k is larger than the array size
        reverse(nums, 0, nums.length - 1);  // Reverse the entire array
        reverse(nums, 0, k - 1);  // Reverse the first k elements
        reverse(nums, k, nums.length - 1);  // Reverse the remaining elements
    }

    private void reverse(int[] nums, int start, int end) {
        while (start < end) {
            int temp = nums[start];
            nums[start] = nums[end];
            nums[end] = temp;
            start++;
            end--;
        }
    }
}
```

#Problem 6
Link : https://leetcode.com/problems/move-zeroes/submissions/884361826/?source=submission-ac

Name : Move Zeroes

Description : To move all the Zeroes occuring in the array to the last of the array.

Difficulty: 

Complexity:

```java []
class Solution {
    public void moveZeroes(int[] nums) {
        int i=0,k=nums.length-1;
        while(k!=0){
            if(nums[i]==0){
                int j=i;
                while(j!=nums.length-1){
                    nums[j]=nums[j+1];
                    j++;
                }
                nums[nums.length-1]=0;
                
            }else{
                i++;
            }
            k--;
        }
        
    }
}
```