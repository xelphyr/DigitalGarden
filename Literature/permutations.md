---
id: 065ae92a-0f5c-4106-88a7-7e2b9f2893a0
---

# permutations
#Omnivore

[Read on Omnivore](https://omnivore.app/me/permutations-18e9896262f)
[Read Original](https://www.iarcs.org.in/inoi/online-study-material/topics/permutations.php)

## Highlights

> Begin from the right and keep moving left as long as the
> 	letters are increasing in value (where
> 	a<b<c<…<l).  In this case, start with
> 	a and scan past d, h, i, k.  Stop at c because c<k.
>       
> 
> 	Find the smallest value bigger than c in the sequence "k
> 	i h d a" after c and swap it with c.  In this case, this
> 	value is d, so rewrite the last 6 letters of the sequence
> 	as "d k i h c a".  Having done this, reverse the letters
> 	beyond d to get "d a c h i k".
>       
> 
> 	The new permutation that we want is thus
>       
> 
>                 f g j l b e d a c h i k
>       
> 
> 	Why does this work?  Given values a1<a2<...<ak,
> 	the smallest permutation is a1 a2 ... ak and the largest
> 	permutation is ak ... a2 a1.
>       
> 
> 	For the element we have identified in the current
> 	permutation, there is no way to increment the permutation
> 	keeping this element fixed because we have already
> 	identified the largest permutation to its right.  Thus,
> 	we have to increment the current element minimally, which
> 	is achieved by picking the next largest element to its
> 	right.
>       
> 
> 	How do we implement this?
>       
>  Initially, sort the elements to obtain the minimum
> 	  permutation.
>  Scan from the right to find which element to
> 	  increment.
>  We now scan back to the right to find the next
>           bigger element to replace this one.  Observe that the
>           sequence to the right is sorted in descending order, so
>           this can be done using binary search.
>  Finally, we have to reorder the elements to the
> 	  right in ascending order.  If at Step 3 we swap the new
> 	  value with the value we want to increment, the sequence
> 	  to the right remains in descending order.  We just have
> 	  to invert this sequence to put it in ascending order
> 	  --- no sorting is required. [⤴️](https://omnivore.app/me/permutations-18e9896262f#3742f356-b838-4d58-9d1d-e8f9ef3e20a0)  ^3742f356

