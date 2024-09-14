#Problem 7
Link : https://www.geeksforgeeks.org/problems/who-will-win-1587115621/1

Name : Linear Search 

Description : Bonus Question
very easy one.

```java
class Solution {
    static int searchInSorted(int arr[], int N, int K) {

        // Your code here
        for (int i=0; i<N; i++){
            if(arr[i] == K)
                return 1;
        }
        return -1;
    }
}
```

#Problem 8
Link : https://www.geeksforgeeks.org/problems/union-of-two-sorted-arrays-1587115621/1

Name : Union of Array

Description : to do the union of two given array.

Complexity : O(N+M)

Difficulty : Easy GFG

```java
class Solution
{
    public static ArrayList<Integer> findUnion(int arr1[], int arr2[], int n, int m)
    {
        ArrayList<Integer> list = new ArrayList<>();
        int i = 0, j = 0;

        while (i < n && j < m) {
            // If arr1 element is smaller
            if (arr1[i] < arr2[j]) {
                if (list.size() == 0 || list.get(list.size() - 1) != arr1[i]) {
                    list.add(arr1[i]);
                }
                i++;
            }
            // If arr2 element is smaller
            else if (arr2[j] < arr1[i]) {
                if (list.size() == 0 || list.get(list.size() - 1) != arr2[j]) {
                    list.add(arr2[j]);
                }
                j++;
            }
            // If elements are equal, add either one and increment both pointers
            else {
                if (list.size() == 0 || list.get(list.size() - 1) != arr1[i]) {
                    list.add(arr1[i]);
                }
                i++;
                j++;
            }
        }

        // Add remaining elements of arr1
        while (i < n) {
            if (list.get(list.size() - 1) != arr1[i]) {
                list.add(arr1[i]);
            }
            i++;
        }

        // Add remaining elements of arr2
        while (j < m) {
            if (list.get(list.size() - 1) != arr2[j]) {
                list.add(arr2[j]);
            }
            j++;
        }

        return list;
    }
}
```

