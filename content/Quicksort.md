---
title: Quicksort
firstDate: 15th Jun, 2024
draft: true
tags:
  - "#ZP"
---
This is a [[divide-and-conquer]] [recursive](Recursion) sorting algorithm. Runs in O($n^2$) time but in $\theta (n \log n)$ time
## Steps
(assume the array is being sorted in ascending order, and all elements are distinct)
- Choose a 'pivot' point (position in an array (usually the first one, but we'll get to that later), to which all other values will be compared to)
- Split the array into two new parts, with values smaller and bigger than the pivot like this:
	- create a variable pointing to the splitting point between the larger and smaller array and set it to the beginning (for now, call it `pivotPos`)
	- Search the array
		- If you encounter a value larger than the pivot, keep it as-is
		- If you find a value smaller than the pivot, swap that value with the value located at `pivotPos`, then increment `pivotPos`
		- Finally, the pivot value will be at the end. Swap the last element (aka the pivot) with the value at `pivotPos` (aka some value larger than pivot). 
		- Now you have an array split into two parts - numbers less than the pivot in indices <`pivotPos`, numbers larger than pivot in indices > `pivotPos`
- Recursively call the function on those two halves until you have arrays of size 1
- Then, while [[Unwinding]], we merge the arrays as follows:
	- Take the first two elements of the split arrays, which would be the smallest in each array
	- Remove the smaller of them from their respective array, and add it to the end of the new array.
	- Repeat until both the arrays are empty
- Return the new array

## Complexity
This takes $\theta (n \log n)$ time, but in the worst-case scenario (the array is sorted in descending order), it would take O($n^2$) time. However, we can reduce this complexity by taking a random pivot using RNG to choose an index and swapping that value with the first index's. This ensures that it's much rarer to get the O($n^2$) case.

## Code
```python
# Precondition: a has distinct elements
def quicksort(a):
	pivotPos = 0
	for i in range(len(a)):
		if a[i] < a[pivotPos]:
			temp = a[i]
			a[i] = a[pivotPos]
			a[pivotPos] = temp
			pivotPos += 1
		arr1 = quicksort(a[:pivotPos])
		arr2 = quicksort(a[(pivotPos+1):])
		retArr = []
		while arr1 and arr2:
			if arr1[0] < arr2[0]:
				retArr.append(arr1.pop(0))
			else:
				retArr.append(arr2.pop(0))
		retArr.extend(arr1+arr2)
		return retArr
```
# Related Notes
[[Mergesort]]

# Literary (Further Reading)
