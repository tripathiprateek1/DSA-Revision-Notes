# Sliding Window Pattern Notes

---

# 1. How to Identify Sliding Window Problems?

Think about Sliding Window when:

- Array or String is involved
- Need continuous subarray/substring
- Need optimized `O(n)` solution
- Question asks for:
  - longest
  - shortest
  - maximum
  - minimum
  - continuous range

---

## Common Clues

| Clue in Question | Possible Pattern |
|---|---|
| longest substring | variable window |
| smallest subarray | variable window |
| fixed size k | fixed window |
| continuous sequence | sliding window |
| maximum/minimum sum | sliding window |
| substring/subarray | sliding window |

---

# 2. Categories of Sliding Window Problems

---

## A. Fixed Size Window

### Window Size

```text
window size = k
```

### Used In

- Maximum Sum Subarray of Size K
- First Negative Number in Every Window
- Average of Subarrays

### Key Idea

- Maintain window of fixed size
- Add incoming element
- Remove outgoing element

---

## B. Variable Size Window

### Window Size

```text
expand → shrink
```

### Used In

- Longest Substring Without Repeating Characters
- Minimum Size Subarray Sum
- Longest Repeating Character Replacement

### Key Idea

- Expand window until invalid
- Shrink window to make it valid again

---

# 3. Key Concepts Based on Problem Type

| Problem Type | Window Behavior |
|---|---|
| Maximum Sum | maintain running sum |
| Longest Substring | expand while valid |
| Minimum Subarray | shrink aggressively |
| Distinct Characters | use HashMap/Set |
| Anagram Problems | frequency counting |
| Fixed Size K | slide one step at a time |

---

# 4. Important Tips

## Tip 1

Sliding Window works mainly on:

- arrays
- strings
- continuous ranges

---

## Tip 2

If question asks:

- longest
- shortest
- continuous
- substring
- subarray

→ Think Sliding Window first.

---

## Tip 3

Window usually has:

```text
left pointer
right pointer
```

---

## Tip 4

Most Sliding Window problems optimize:

```text
O(n²) → O(n)
```

---

## Tip 5

Always ask:

- What makes window valid?
- When should window shrink?
- What data structure is needed?
  - HashMap
  - HashSet
  - Frequency Array

---

# 5. Common Template Thinking

---

## Fixed Size Window Template

```java
int left = 0;

for(int right = 0; right < n; right++){

    // add current element

    if(right - left + 1 == k){

        // calculate answer

        // remove left element
        left++;
    }
}
```

---

## Variable Size Window Template

```java
int left = 0;

for(int right = 0; right < n; right++){

    // expand window

    while(window invalid){

        // shrink window
        left++;
    }

    // calculate answer
}
```

---

# 6. Common Mistakes

| Mistake | Problem |
|---|---|
| forgetting to shrink window | invalid answer |
| shrinking too early | missed answer |
| incorrect window size formula | bugs |
| not removing left element properly | wrong frequency |
| using wrong data structure | inefficient solution |

---

# 7. Famous Problems List

| Category | Problems |
|---|---|
| Fixed Window | Maximum Sum Subarray of Size K |
| Variable Window | Longest Substring Without Repeating Characters |
| Frequency Based | Find All Anagrams in a String |
| Shrinking Window | Minimum Window Substring |

---

# 8. Simple Mental Framework

| Situation | Pattern |
|---|---|
| fixed size k | fixed window |
| longest valid range | variable window |
| smallest valid range | shrinking window |
| substring/subarray | sliding window |
| frequency tracking | hashmap + window |

