#Problem 19 -- KKQuestions

Link : https://leetcode.com/problems/best-time-to-buy-and-sell-stock/description/

Name : Best Time to buy and sell the stock.

Description : we have to find the max profit that we can earn from the stock buying (on a particular day) and selling (after buying always).

Difficulty : Leetcode Easy

Complexity : O(N)

```java
class Solution {
    public int maxProfit(int[] prices) {
       int min_price = prices[0];
       int max_profit = 0;
       for(int i=0;i<prices.length;i++){
           min_price = Math.min(min_price,prices[i]);
           max_profit = Math.max(max_profit,prices[i]-min_price);
       }
       return max_profit;
    }
}
```

#Problem 20 : VERY IMPORTANT QUESTION : REMAINING TO WATCH THE OPTIMAL SOLUTION.

Link : https://www.geeksforgeeks.org/problems/longest-sub-array-with-sum-k0809/1

Name : Longest Subarray with sum k (Positives and negatives)

Description : to find the longest consecutive subarray with sum k in the given array.
Approch:

    1. We can do check the sum value with k and have the maxLen varible checked with O(N*N*N)

    ```java
    for(int i=0;i<n;i++){
        int sum =0;
        for(int j=i;j<n;j++){
            for(k = j;k<n;k++){
                sum +=arr[k];
            }
            if(sum == target){
                maxLen = Math.max(maxLen, j-i+1);
            }
        }
    }
    ```
    2. We can reduce the inner loop and have the solution in O(N*N)

    ```java 
    for(int i=0;i<n;i++){
        int sum =0;
        for(int j=i;j<n;j++){
            sum +=arr[j];

            if(sum == k){
                maxLen = Math.max(maxLen, j-i+1);
            }
        }
    }
    ```

    3. The final approch in which we use the same methed we used in the 2Sum Question COMPLEMENT.
    and we stored the values in the hashMap. So, for every iteration we check for the component in the hashmap.

Difficulty : GFG Medium

Complexity : O(N)
```java
class Solution {
    // Function for finding maximum and value pair
    public static int lenOfLongSubarr(int A[], int N, int K) {
        HashMap<Integer, Integer> prefsum = new HashMap<>();
        
        int sum = 0;
        int maxLen = 0;
        for (int i = 0; i < N; i++) {
            sum += A[i];
            
            // If the sum equals K, update maxLen to i + 1
            if (sum == K) {
                maxLen = i + 1;
            }
            
            // Check if (sum - K) exists in prefsum
            int rem = sum - K;
            if (prefsum.containsKey(rem)) {
                int len = i - prefsum.get(rem);
                maxLen = Math.max(maxLen, len);
            }
            
            // Add current sum to prefsum if not already present
            if (!prefsum.containsKey(sum)) {
                prefsum.put(sum, i);
            }
        }
        return maxLen;
    }
}
```