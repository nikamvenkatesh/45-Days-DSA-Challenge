#Problem 29 

Link : https://www.geeksforgeeks.org/problems/lcm-and-gcd4516/1

Name :LCM and GCD

Description : we have to calculate the lcm and gcd of two numbers a,b;

Difficulty : GFG Easy

Complexity : O(Log (min(a,b)))

```java
class Solution {
    static Long[] lcmAndGcd(Long A , Long B) {
        // code here
        Long [] ans = new Long[2];
        // Euclidean method, 
        Long temp1 = A;
        Long temp2 = B;
        while(temp2 !=0){
            Long temp = temp2;
            temp2 = temp1 % temp2;
            temp1 = temp;
        }
        ans[1] = temp1;
        
        ans[0] = (A*B)/ans[1];
        
        return ans;
    }
};
```

#Problem 30 

Link : https://www.geeksforgeeks.org/problems/sum-of-all-divisors-from-1-to-n4738/1

Name : Sum of all divisors from 1 to n.

Description : Please visit the question description for better understanding.

Difficulty : GFG Easy(although medium)

Complexity : O(N)

```java
//User function Template for Java
class Solution {
    static long sumOfDivisors(int N) {
        // long totalSum = 0;
        // for(int i=1;i<=N;i++){
        //     totalSum += sum(i);
        // }
        // return totalSum;
        /*/long totalSum = 0;
        long[] divisorSum = new long[N + 1]; // Array to store sum of divisors for each number

        // Loop through each integer from 1 to N
        for (int i = 1; i <= N; i++) {
            // For each number i, add it to all of its multiples
            for (int j = i; j <= N; j += i) {
                divisorSum[j] += i; // Add i to the sum of divisors for j
            }
        }

        // Sum all the divisor sums
        for (int i = 1; i <= N; i++) {
            totalSum += divisorSum[i];
        }

        return totalSum;
        */
        long totalSum = 0;

        // Loop through each integer from 1 to N
        for (int i = 1; i <= N; i++) {
            // For each number i, add it to all of its multiples
            totalSum += (long) i * (N / i); // i contributes to all multiples of i up to N
        }

        return totalSum;
    }
    
    // static long sum(int num){
    //     long sum = 0;
    //     for (int i = 1; i * i <= num; i++) {
    //         if (num % i == 0) {
    //             sum += i;
    //             if (i != num / i) { // Add the corresponding divisor if it's different from i
    //                 sum += num / i;
    //             }
    //         }
    //     }
    //     return sum;
    // }
}

```