# Selection Sort
### Analysis
- Selection sort is O(n<sup>2</sup>)
- Appropriate only for small n
- **Only uses n-1 swaps in worst case**
- **Could be a good choice when data moves are costly but comparisons are not**
  - For example: when each data item is large but sort key is short

## Implementation (C++)

```
template <class ItemType>
void selectionSort(ItemType theArray[], int n)
{
  // last = index of the last item in the subarray of items yet to be sorted
  // largest = index of the largest item found
  for (int last = n -1; last >= 1; last--)
  {
    // At this point, theArray[last+1..n-1] is sorted, and its entries are greater than those in theArray[0..last]
    // Select the largest entry in theArray[0..last]
    int largest = findIndexOfLargest(theArray, last+1);

    // Swap the largest entry, theArray[largest], with
    // theArray[last]
    std::swap(theArray[largest], theArray[last]);
  } // end for
} // end selectionSort

template <class ItemType>
int findIndexOfLargest(const ItemType theArray[, int size])
{
  int indexSoFar = 0; // Index of the largest entry found so far
  for (int currentIndex = 1; ccurentIndex < size; currentIndex++)
  {
    // At this point, theArray[indexSoFar] >= all entries in theArray[0..currentIndex-1]
    if (theArray[currentIndex] > theArray[indexSoFar])
      indexSoFar = currentIndex;
  } // end for

return indexSoFar; // Index of the largest entry
} // end findIndexOfLargest
```
