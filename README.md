# Merge Sort Algorithm

```Merge Sort``` uses ```Divide And Conquer``` strategy to solve the problem.

## Divide And Conquer
Divide and Conquer Strategy
Using the Divide and Conquer technique, we divide a problem into subproblems. When the solution to each subproblem is ready, we 'combine' the results from the subproblems to solve the main problem.

---
Suppose we had to sort an array A. A subproblem would be to sort a sub-section of this array starting at index p and ending at index r, denoted as A[p..r].

+ ### Divide
If q is the half-way point between p and r, then we can split the subarray A[p..r] into two arrays A[p..q] and A[q+1, r].

+ ### Conquer
In the conquer step, we try to sort both the subarrays A[p..q] and A[q+1, r]. If we haven't yet reached the base case, we again divide both these subarrays and try to sort them.

+ ### Combine
When the conquer step reaches the base step, and we get two sorted subarrays A[p..q] and A[q+1, r] for array A[p..r], we combine the results by creating a sorted array A[p..r] from two sorted subarrays A[p..q] and A[q+1, r].

---
## Merge Sort PseudoCode

### Divide And Conquer Strategy

```java
input: Array numbers[1...n]

mergeSort(int start, int end):
        
    int B[end - start + 1]
    if (start == end) return B[1] = numbers[start]
        
    int mid = (start + end) / 2
    int[] leftHalf  = mergeSort(start, mid)
    int[] rightHalf = mergeSort(mid + 1, end)

    mergeHalves(leftHalf, rightHalf, B)    
    return B
```

### Merge Halves!!
The merge step is the solution to the simple problem of merging two sorted lists(arrays) to build one large sorted list(array).
```java
mergeHalves(array leftHalf, array rightHalf, B):
    int l = 0, r = 0
    for k = 1 to len(B):
        if (l > len(lenfHalf)):
            B[k] = rightHalf[r]
            r++
        else if (r > len(rightHalf) || leftHalf[l] < rightHalf[r]):
            B[k] = leftHalf[l]  // also can use: B[k] = leftHalf[l++]
            l++
        else:
            B[k] = rightHalf[r] // also can use: B[k] = rightHalf[r++]
            r++
```

instead of above code you can use this code too:
```java
mergeHalves(array leftHalf, array rightHalf, B):
    int l = 0, r = 0
    for k = 1 to len(B):
        B[i] = (r >=  len(rightHalf) || (l < len(lenfHalf) && left[l] < right[r])) ? left[l++] : right[r++];
```

---
## Time Complexity
*Best Case Complexity:*&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**O(nlog n)**

*Worst Case Complexity:*&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**O(nlog n)**

*Average Case Complexity:* **O(nlog n)**

## Space Complexity
*The space complexity of merge sort is* **O(n)**.

---
Author: [Mohsen Gholami | iMohsen02](http://T.me/iMohsen02, "Mohsen.Telegram")

Yazd State University