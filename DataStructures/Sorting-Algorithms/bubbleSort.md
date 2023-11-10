# Bubble Sort
- Compares adjacent items
  - Exchanges them if out of order
  - Requires several passes over the data
- When ordering successive pairs
  - Largest item bubbles to the end of the array
### Analysis
- Worst case O(n<sup>2</sup>)
- Best case (array already in order) is O(n)
### Good for
- Small sequence
- Nearly Sorted data
- Special Situations where an adjacent swap is preferred (data stored on tape or in linked list)
## Implementation (C++)
```
template <class ItemType>
void bubbleSort(ItemType theArray[], int n)
{
  bool sorted = false; // False when swaps occur
  int pass = 1;
  while (!sorted && (pass < n))
  {
    // At this point, theArray[n+1-pass..n-1] is sorted
    // and all of its entries are > the entries in theArray[0..n-pass]
    sorted = true; // Assume sorted
    for (int index = 0; index < n - pass; index++)
    {
      // At this point all entries in theArray[0...index-1]
      // are <= theArray[index]
      int nextIndex = index + 1;
      if (theArray[index] > theArray[nextIndex])
      {
        // Exchange entries
        std::swap(theArray[index], theArray[nextIndex]);
        sorted = false; // Signal exchange
      } // end if
    } // end for
    // Assertion: theArray[0..n-pass-1] < theArray[n-pass]

    pass++;
  } // end while
} // end bubbleSort
```
