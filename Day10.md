#Problem 19
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

#Problem 20
Link : 
Name : 
Description : 
Difficulty : 
Complexity : 
```java

```