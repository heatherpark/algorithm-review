## selection sort

**what is it?**  selection sort is a sorting algorithm that uses in-place comparison sort.

**method:**
  * divide input list into two parts:
    1. the sublist of already sorted items
    2. the sublist of items remaining to be sorted
  * find smallest element in unsorted sublist
  * exchange that element with the leftmost unsorted element
  * move unsorted sublist's left boundary one element to the right
  * repeat with new sublist until all sublists have been sorted

**time complexity:** O(n^2), or quadratic time.

#### implementation

```javascript
function findSmallestIndex(array, min) {
  // initialize value of smallestIndex to value of min
  var smallestIndex = min;

  // iterate over array starting from index at min + 1
  for (var i = min + 1; i < array.length; i++) {
    // if the current item is smaller than the item at smallestIndex
    if (array[i] < array[smallestIndex]) {
      // reset value of smallestIndex with current loop index
      smallestIndex = i;
    }
  }

  return smallestIndex;
}

function selectionSort(array) {
  // loop through array
  for (var i = 0; i < array.length; i++) {
    // set left boundary for unsorted sublist to current iteration index
    var min = i;
    // findSmallestIndex will return smallest element of unsorted sublist
    // unsorted sublist is defined as current item plus all subsequent items
    var smallestIndex = findSmallestIndex(array, min);

    // switch smallest item of unsorted sublist with first item of unsorted sublist if they are not equal
    if (array[smallestIndex] !== array[min]) {
      var temp = array[min];
      array[min] = array[smallestIndex];
      array[smallestIndex] = temp;
    }
  }

  return array;
}
```
