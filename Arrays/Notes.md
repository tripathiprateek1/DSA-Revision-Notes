# Arrays

## What is an Array?

An array is a collection of elements stored in contiguous memory locations.

Example:
```java
int[] arr = {1, 2, 3, 4, 5};
```

---

# When to Think About Arrays

Questions involving:
- Traversal
- Maximum / Minimum
- Prefix Sum
- Subarray
- Sorting
- Searching
- Frequency counting

---

# Common Array Patterns

| Pattern | Use Case |
|----------|----------|
| Traversal | Basic iteration |
| Prefix Sum | Range sum problems |
| Sliding Window | Contiguous subarray |
| Two Pointers | Sorted arrays |
| Hashing | Frequency/count |

---

# Important Questions

## 1. Two Sum
Pattern: HashMap

### Brute Force
TC: O(n²)

### Optimized
TC: O(n)

```java
class Solution {
    public int[] twoSum(int[] nums, int target) {

        HashMap<Integer, Integer> map = new HashMap<>();

        for(int i = 0; i < nums.length; i++){

            int complement = target - nums[i];

            if(map.containsKey(complement)){
                return new int[]{map.get(complement), i};
            }

            map.put(nums[i], i);
        }

        return new int[]{};
    }
}
```

---

## 2. Maximum Subarray (Kadane’s Algorithm)

Pattern: Running Sum

### Optimized
TC: O(n)

```java
class Solution {
    public int maxSubArray(int[] nums) {

        int currentSum = 0;
        int maxSum = nums[0];

        for(int num : nums){

            if(currentSum < 0){
                currentSum = 0;
            }

            currentSum += num;

            maxSum = Math.max(maxSum, currentSum);
        }

        return maxSum;
    }
}
```

---

## 3. Best Time to Buy and Sell Stock

Pattern: Minimum Tracking

```java
class Solution {
    public int maxProfit(int[] prices) {

        int minPrice = Integer.MAX_VALUE;
        int maxProfit = 0;

        for(int price : prices){

            minPrice = Math.min(minPrice, price);

            maxProfit = Math.max(maxProfit, price - minPrice);
        }

        return maxProfit;
    }
}
```

---

# Important Observations

## If question contains:
- subarray
- contiguous
- longest
- shortest

Think:
- Sliding Window
- Prefix Sum

---

# Time Complexities

| Operation | Complexity |
|-----------|-------------|
| Traversal | O(n) |
| Access | O(1) |
| Search | O(n) |
| Insert at end | O(1) |
| Insert at beginning | O(n) |

---

# Revision Notes

- Arrays are index-based
- Contiguous memory allocation
- Most interview problems start from arrays
- Learn patterns instead of memorizing problems
