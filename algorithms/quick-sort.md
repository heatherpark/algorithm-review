## quick sort

**what is it?**  quick sort is an efficient sorting algorithm that uses comparison sort.

**method:**
  * pick an element -- what's known as the pivot -- from the array.
  * partition your elements:
    * reorder the array so that all elements with values less than the pivot come before the pivot and all elements with values
      greater than the pivot come after the pivot
    * the pivot is now at its final spot
  * recursively invoke quick sort on the subarray of smaller values and concatentate the resulting array with the pivot and the resulting
    array from invoking quick sort on the subarray of greater values

**time complexity:**
  * __worst case:__ O(n^2) -> happens if we touch every element in the array for every recursive case
  * __best/average case:__ O(n log n) -> if a random element is chosen as the pivot each time, the best case will be the average case.  at best,   we'd only need to have log n recursive calls

#### implementation

```javascript
function quickSort(array) {
  // base case -> if array length is 0 or 1, it's already sorted
  if (array.length < 2) {
    return array;
  } else {
    // find random index in array and use to determine pivot
    var random = Math.floor(Math.random() * array.length);
    var pivot = array[random];
    // partition using array filter method
    var less = array.filter(function(num) {
      return num < pivot;
    });
    var greater = array.filter(function(num) {
      return num > pivot;
    });
    // invoke quickSort on less and greater subarrays and concatenate with pivot
    return quickSort(less).concat(pivot, quickSort(greater));
  }
}
```
