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

```
template <class ItemType>
void bubbleSort(ItemType theArray[], int n)
{
  bool sorted = false; // False when swaps occur
  int pass = 1;
  while (!sorted && (pass < n))
```
