#Problem 9
Link : https://www.geeksforgeeks.org/problems/intersection-of-two-arrays2404/1

Name  : Intersection of two arrays.

Description : as the union its quite similar where we have to add only the comman element (a[i]==b[j]), other conditions we only have to increment the index ( for greater than or less than the value).

Complexity : O(N+M)

Difficulty : Easy gfg

```java
class Solution {
    // Function to return the count of the number of elements in
    // the intersection of two arrays.
    public static int NumberofElementsInIntersection(int a[], int b[], int n, int m) {
        // Your code here
        ArrayList<Integer> list = new ArrayList<>();
        int i = 0, j = 0;
        Arrays.sort(a);
        Arrays.sort(b);
        while (i < n && j < m) {
            // If arr1 element is smaller
            if (a[i] < b[j]) {
                if (list.size() == 0 || list.get(list.size() - 1) != a[i]) {
                    // list.add(arr1[i]);
                }
                i++;
            }
            // If arr2 element is smaller
            else if (b[j] < a[i]) {
                if (list.size() == 0 || list.get(list.size() - 1) != b[j]) {
                    // list.add(arr2[j]);
                }
                j++;
            }
            // If elements are equal, add either one and increment both pointers
            else {
                if (list.size() == 0 || list.get(list.size() - 1) != a[i]) {
                    list.add(a[i]);
                }
                i++;
                j++;
            }
        }
        
        return list.size();
    }
};
```

#Problem 10
Link : https://leetcode.com/problems/missing-number/
Name : Missing Number 
Description : we are given with an array consisting of the values ranging from 1 to n.
we have to find the element or value that is missing or not present over their.
Two Approches (OPTIMAL)
1. Sum method

```java
class Solution {
    public int missingNumber(int[] nums) {
        int n = nums.length;
        int sum1 = n * (n+1)/2;

        int sum2 =0 ;
        for(int i=0 ;i< n; i++){
            sum2 += nums[i];
        }
        return sum1 - sum2;
    }
}
```

2. XOR method : More optimal cause we are not calculating by a formula for some big input integer value.

```java
class Solution {
    public int missingNumber(int[] nums) {
        int xor1 = 0;
        int xor2 = 0;
        int n = nums.length;
        for(int i=0; i< n; i++){
            xor2 = xor2 ^ nums[i];
            xor1 = xor1 ^ (i);
        }
        xor1 = xor1 ^ n;
        return xor1 ^ xor2;
    }
}
```

Difficulty : Leetcode Easy
Complexity : O(N)