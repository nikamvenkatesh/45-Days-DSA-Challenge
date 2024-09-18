#Problem 11
Link : https://leetcode.com/problems/max-consecutive-ones/description/

Name : Max Consecutives Ones

Description : To count the max amount of ones from the given arr.
what i did is, if the arr value is 1 we raise the count and then if we reach to 0 we add that count value in the arraylist. but their was one issue for the last subarray of ones as we cannot add the count in the arraylist, solution was to add that value at the end of the loop.

My solution :
```java
class Solution {
    public int findMaxConsecutiveOnes(int[] nums) {
        ArrayList <Integer> list = new ArrayList<>();
        int count = 0;
        for(int i=0; i<nums.length; i++){
            if(nums[i]== 1){
                count ++;
            }else{
                list.add(count);
                count = 0;
            }
        }
        list.add(count);
        return Collections.max(list);
    }
}
```

Difficulty : Leetcode Easy

Complexity : O(N)
```java

```

#Problem 12
Link : https://leetcode.com/problems/single-number/submissions/1393909100/

Name : Single Number

Description : Well all we have to do is catch the odd man out, which means the one that one number whose pair does not exist in the arr.
can be done by XOR -ing all the elements of arr and one with no pair well be remained alone.

Difficulty : Leetcode Easy

Complexity : O(N)

```java
class Solution {
    public int singleNumber(int[] nums) {
        int xor =0;
        for(int i=0; i<nums.length; i++){
            xor = xor ^ nums[i];
        }
        return xor;
    }
}
```