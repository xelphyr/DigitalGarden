---
title: Mergesort
draft: false
tags:
  - ZP
---
This is a divide-and-conquer recursive sorting algorithm.

## Steps 
(assume we are sorting an array in ascending order):
- We recursively split the array into two halves until we reach the smallest possible array (where the number of elements is 1)
- Then, at each step we rejoin them in the following fashion:
	- Take the first two elements of the split arrays (the smallest element in each array)
	- Remove the smaller of them from their respective array, and add it to the end of the new array.
	- Keep repeating this process until both arrays are empty.
- Return the new array

## Example

Take the array \[8,9,5,3,2,0,4]

![[Merge Sort 2024-05-26 14.50.56.excalidraw]]

The method you split odd-numbered arrays is up to user discretion, but in the above example the first half gets the middle term in the odd-numbered arrays.
# Related Notes

