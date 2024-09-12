#Problem 1
Link:https://www.geeksforgeeks.org/problems/largest-element-in-array4009/0

Name: Largest Element in the Array

Description: Just to find the largest element in the unsorted array. We can solve it by using the simple Linear Search.

Difficulty: Very Easy.

Complexity : O(N)

```java
class Solution {
    public static int largest(int[] arr) {
        int max = arr[0];
        for(int i=0;i<arr.length;i++){
            if(arr[i]>=max)
                max=arr[i];
            
        }
        return max;
    }
}
```


#Problem 2
Link:https://www.geeksforgeeks.org/problems/second-largest3735/1

Name: Second Largest Element in the Array.

Description: Kind of similar to the previous one, just a little different cause we need the second largest so we compare the first largest and the array current element with it.

here, we can solve this question by two steps
1. Firstly i will find the largest element in the array. :: O(N) Complexity
2. Now i will compare every single element of the array to be smaller than the largest but again being the largest than the current second largest element(Interger.MIN_VALUE).

Follwoing is the optimised solution for the same.

Difficulty: Easy

Complexity: O(N)

```java
class Solution {
    public int print2largest(int[] arr) {
   
        int max1 = Integer.MIN_VALUE;
        int max2= Integer.MIN_VALUE;
        for (int i=0;i<arr.length;i++){
            if(arr[i]>max1){
                max2 = max1;
                max1 = arr[i];
            } else if(arr[i]>max2 && arr[i]<max1){
                max2 = arr[i];
            }
        }
        if(max2==Integer.MIN_VALUE)
            return -1;
        return max2;
    }
}
```