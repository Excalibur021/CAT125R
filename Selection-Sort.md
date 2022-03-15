# Selection Sort
Selection Sort, as it name suggests, is one of the sorting algorithm, which aims to sort an array-like data structure to an specific order, usually ascending or descending.

---
## How it works

During the sort process, we treat the array as two part: a sorted subarray gradually built up at the front of array, and an unsorted subarray at the end. Initially the sorted subarray is empty and the unsorted subarray is the original array, as the table below shows.

| Iteration  | Sorted Subarray  | Unsorted Subarray|
|   :---:    | :---             |          ---:    |
|0           | ()               | (3, 5, 2, 1, 4)  |

Then, the algorithm goes through the unsorted subarray to find out the minimum/maximum (depending on sorting to ascending/descending) element in the unsorted subarray. You can see the details about finding maximum/minimum algorithm here [a link]. After the minimum/maximum is found, we swap it with the first element of unsorted subarray and move the boundary of subarrays an element right. This process is repeated until the unsorted subarray is empty. We can see this process as an example below:

|  ITERATION  |  SORTED SUBARRAY  |  UNSORTED SUBARRAY  |
|   :---:     | :---              |        ---:         |
|0|	() |	(3, 5, 2, 1, 4)|
|1|	(1)	|  (5, 2, 3, 4)|
|2|  (1, 2)	|  (5, 3, 4)|
|3|	(1, 2, 3)|  	(5, 4)|
|4|	(1, 2, 3, 4)|	(5)|
|5|	(1, 2, 3, 4, 5)|	()|

---
## Why this algorithm works

As stated in the last paragraph, the first part of array is always sorted, and we can easily see that during the i-th iteration, the first i element is sorted. Hence, for an array of length n, we can assure that after n iterations, first n elements ---- namely the entire array---- is sorted properly.

---
## Time Analysis

For the best case of the sorting algorithm, the array is sorted before algorithm. In this case, in i-th iteration, we need find the minimum/maximum in the unsorted subarray, which need (n-i) comparisons. Then, we do not need to do any swap operations. Hence, together we need $\sum_{i=1} ^{n}(n-i) = \cfrac{n(n-1)}{2}$ operations, which is $O(n^2)$

For the worst case, the array is totally unsorted, which means none of the element is on its position. In this case, in i-th iteration, we need find the minimum/maximum in the unsorted subarray, which need (n-i) comparisons. Then in every iteration we need to swap the element. Hence, together we need $\sum_{i=1} ^{n}(n-i+1) = \cfrac{n(n+1)}{2}$ operations, which is $O(n^2)$

For the average case, the probability of an element is on its correct position is 1/n, so averagely n/n=1 element is on its position. In this case, in i-th iteration, we need find the minimum/maximum in the unsorted subarray, which need (n-i) comparisons. Then in every iteration but one we need to swap the element. Hence, together we need $\sum_{i=1} ^{n}(n-i+1) - 1 = \cfrac{n(n+1)}{2} - 1$ operations, which is $O(n^2)$

---
[back to main page](https://excalibur021.github.io/CAT125R/)