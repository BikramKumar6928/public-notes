#competetive #problem #array 
## Problem
Given an `int` array `a[]` and a number `x`, find a pair of numbers having sum equal to `x`.

GFG Link:- https://practice.geeksforgeeks.org/problems/key-pair5616/1

## Solution

Add all the numbers into a Hashed Set for quick reference.

Check if the number `x - a[i]` is present in the set.

If the said number is found, then the number `x -a[i]` and `a[i]` are the 2 numbers in the array whose sum is `x`.

### Special case
If the check for number present is done before adding the number to the Set, we can ensure that the same number is not being considered for both the numbers in the pair.

If we want to not take same number as both the numbers in the pair, we can use a Map instead of a Set. The Map will contain the number and the frequency of the number. 

If the number is present more than once, then we can successfully take the number twice. Otherwise, the current number cannot be taken in the pair.

## Code

```Java
// { Driver Code Starts
//Initial Template for Java

import java.util.*;
import java.io.*;

public class Main {

    public static void main(String[] args) throws Exception {
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        int tc = Integer.parseInt(br.readLine().trim());
        while (tc-- > 0) {
            String[] inputLine;
            inputLine = br.readLine().trim().split(" ");
            int n = Integer.parseInt(inputLine[0]);
            int x = Integer.parseInt(inputLine[1]);
            int[] arr = new int[n];
            inputLine = br.readLine().trim().split(" ");
            for (int i = 0; i < n; i++) {
                arr[i] = Integer.parseInt(inputLine[i]);
            }

            boolean ans = new Solution().hasArrayTwoCandidates(arr, n, x);
            System.out.println(ans ? "Yes" : "No");
        }
    }
}
// } Driver Code Ends


//User function Template for Java


class Solution {
    boolean hasArrayTwoCandidates(int arr[], int n, int x) {
        Set<Integer> set = new HashSet<>();
        for(int number : arr){
            if(set.contains(x-number)){
                return true;
            }
            set.add(number);
        }
        return false;
    }
}
```