# Two Pointer Pattern Notes

---

# 1. How to Identify Two Pointer Problems?

Think about Two Pointers when:

- Array or String is involved
- Need to process elements efficiently in `O(n)`
- Need comparison between:
  - two elements
  - both ends
  - current window/range

## Problem asks for:

- pair/triplet
- longest/shortest substring
- remove duplicates
- in-place modification
- palindrome checking
- cycle detection

---

## Common Clues

| Clue in Question | Possible Pattern |
|---|---|
| sorted array | opposite pointers |
| pair sum | left & right |
| longest substring | sliding window |
| remove duplicates | slow & fast |
| linked list cycle | fast & slow |
| in-place modification | write/read pointers |
| palindrome | opposite direction |

---

# 2. Categories of Two Pointer Problems

---

## A. Opposite Direction Pointers

### Movement

```text
left → ← right
```

### Used In

- Pair Sum in Sorted Array
- Palindrome
- Container With Most Water
- 3Sum

### Key Idea

Move pointers based on condition:

- sum too small → `left++`
- sum too large → `right--`

---

## B. Same Direction Pointers

### Movement

```text
slow → fast →
```

### Used In

- Remove Duplicates
- Move Zeroes
- Partition Array

### Key Idea

- `fast` explores array
- `slow` maintains correct position/output

---

## C. Sliding Window

### Movement

```text
expand → shrink
```

### Used In

- Longest Substring Without Repeating Characters
- Minimum Size Subarray Sum
- Maximum Sum Subarray

### Key Idea

Maintain a valid window:

- expand window
- shrink when condition breaks

---

## D. Fast and Slow Pointers

### Movement

```text
slow += 1
fast += 2
```

### Used In

- Linked List Cycle
- Middle Node
- Happy Number

### Key Idea

Different speeds help detect:

- cycle
- middle point

---

# 3. Key Concepts Based on Problem Type

| Problem Type | Pointer Usage |
|---|---|
| Pair Sum | move from both ends |
| Remove Duplicates | slow writes unique values |
| Move Zeroes | slow stores non-zero positions |
| Sliding Window | maintain valid range |
| Palindrome | compare left/right chars |
| Cycle Detection | fast catches slow |
| Merge Arrays | compare two indices |

---

# 4. Important Tips

## Tip 1

Sorted array → always think Two Pointers first.

---

## Tip 2

Need `O(1)` extra space?

Two pointers are often useful.

---

## Tip 3

Two pointers usually reduce:

```text
O(n²) → O(n)
```

---

## Tip 4

Sliding Window is also a Two Pointer technique.

---

## Tip 5

Always ask:

- What does each pointer represent?
- When should pointer move?
- Which condition breaks validity?

---

# 5. Common Template Thinking

---

## Opposite Direction Template

```java
for(int right=0 ; right <n ; right++){

    if(condition){
        // answer
    }
    else if(need bigger){
        left++;
    }
    else{
        right--;
    }
}
```

---

## Sliding Window Template

```java
while(right < n){

    // expand window

    while(window invalid){

        // shrink window
        left++;
    }

    right++;
}
```

---

# 6. Common Mistakes

| Mistake | Problem |
|---|---|
| forgetting pointer movement | infinite loop |
| wrong while condition | incorrect answer |
| moving wrong pointer | logic fails |
| not sorting when needed | pair sum fails |
| shrinking window incorrectly | sliding window bug |

---

# 7. Famous Problems List

| Category | Problems |
|---|---|
| Opposite Pointers | Two Sum II, 3Sum |
| Same Direction | Move Zeroes, Remove Duplicates |
| Sliding Window | Longest Substring Without Repeating Characters |
| Fast & Slow | Linked List Cycle, Middle of Linked List |

---

# 8. Simple Mental Framework

| Situation | Pattern |
|---|---|
| compare ends | opposite pointers |
| maintain window | sliding window |
| modify in-place | slow & fast |
| detect cycle | fast & slow |
| sorted pair search | left/right pointers |


