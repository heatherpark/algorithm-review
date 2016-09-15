## binary search

**method:**
  * a binary search function takes a sorted list and a target number as its inputs
  * set your guess to the middle number and compare with the target
  * if necessary, eliminate half the numbers and repeat

**time complexity:** O(log n) because in the worst case, you have to check log n (where n is the size of the input list) elements.  so, if you have a list of 8 elements, you have to check 3 elements, at most, because log base 2 of 8 is equal to 3.

#### implementation

```javascript
function binarySearch(array, target) {
  // indicate lowest and highest values with variables
  var low = 0;
  var high = array.length - 1;

  // run while loop until search has been narrowed down to one element
  while (low <= high) {
    // find middle index of current search
    // our guess will be number at middle index in array
    var mid = Math.floor((low + high) / 2);
    var guess = array[mid];

    // if our guess is equal to target, return middle index
    if (guess === target) return mid;

    // if our guess is greater than target,
    // rule out all numbers greater than middle number
    // otherwise, rule out all numbers less than middle number
    if (guess > target) {
      high = mid - 1;
    } else {
      low = mid + 1;
    }
  }

  // if target is not found in array, return -1
  return -1;
}
```
