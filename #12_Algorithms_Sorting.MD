<h1 align="center">Algorithms: Sorting</h1>

### Section overview

* **[Sorting Introduction](#introduction-to-algorithms)**
* **[Bubble Sort](#bubble-sort)**
* **[Selection Sort](#selection-sort)**
* **[Insertion Sort](#insertion-sort)**
* **[Merge Sort and O(n log n)](#merge-sort)**
* **[Quick Sort](#quick-sort)**



* **[Stable VS Unstable Algorithms](https://www.udemy.com/course/master-the-coding-interview-data-structures-algorithms/learn/lecture/12406632#overview)**




Sorting algorithms are fundamental in computer science and play a crucial role in various applications. 

Here are some commonly used sorting algorithms and examples of tech companies that may use them:

**Bubble Sort**:
- **Description**: Bubble Sort repeatedly steps through the list, compares adjacent elements, and swaps them if they are in the wrong order.
- **Tech Companies**: While less common in large-scale applications, Bubble Sort might be used in smaller-scale systems or educational contexts.

**Insertion Sort**:
- **Description**: Insertion Sort builds the sorted array one element at a time by repeatedly taking elements from the input data and inserting them into their correct position.
- **Tech Companies**: Amazon and Oracle might use Insertion Sort for small datasets or in scenarios where simplicity is prioritized.

**Selection Sort**:
- **Description**: Selection Sort is a simple sorting algorithm that works by repeatedly finding the minimum element from the unsorted part of the array and putting it at the beginning. 

**Mergesort**:
- **Description**: Heapsort uses a binary heap data structure to build a sorted array in-place.
- **Tech Companies**: Apple and Amazon may use Heapsort for its constant space complexity.

**Quicksort**:
- **Description**: Quicksort is a divide-and-conquer algorithm that partitions an array and recursively sorts sub-arrays.
- **Tech Companies**: Google, LinkedIn, and Microsoft often use Quicksort due to its efficiency on average.
#
**[Back to The TOP](#section-overview)**

### Bubble Sort

**JavaScript example**:

```
const numbers = [99, 44, 6, 2, 1, 5, 63, 87, 283, 4, 0];

function bubbleSort(array) {
  const length = array.length;
  for (let i = 0; i < length; i++) {
    for (let j = 0; j < length; j++) { 
      if(array[j] > array[j+1]) {
        //Swap the numbers
        let temp = array[j]
        array[j] = array[j+1];
        array[j+1] = temp;
      }
    }        
  }
}

bubbleSort(numbers);
console.log(numbers);
```
**[Core Link](https://github.com/aneagoie/ztm-master-the-coding-interview-ds-algo/blob/main/09_sorting/bubbleSort.js)**
#
**[Back to The TOP](#section-overview)**

### Selection Sort

**JavaScript example**:
```
const numbers = [99, 44, 6, 2, 1, 5, 63, 87, 283, 4, 0];

function selectionSort(array) {
    const length = array.length;

    for (let i = 0; i < length - 1; i++) {
        // Set current index as minimum
        let min = i;
        let temp = array[i];

        for (let j = i + 1; j < length; j++) {
            if (array[j] < array[min]) {
                // Update minimum if current is lower that what we had previously
                min = j;
            }
        }

        array[i] = array[min];
        array[min] = temp;
    }

    return array;
}

console.log(selectionSort(numbers));
```
**[Core Link](https://github.com/aneagoie/ztm-master-the-coding-interview-ds-algo/blob/main/09_sorting/selectionSort.js)**
#
**[Back to The TOP](#section-overview)**

### Insertion Sort

**JavaScript example**:
```
const numbers = [99, 44, 6, 2, 1, 5, 63, 87, 283, 4, 0];

function insertionSort(array) {
    const length = array.length;

    for (let i = 0; i < length; i++) {
        if (array[i] < array[0]) {
            // Move number to the first position
            array.unshift(array.splice(i, 1)[0]);
        } else {
            // Find where number should go
            for (let j = 1; j < i; j++) {
                if (array[i] > array[j - 1] && array[i] < array[j]) {
                    // Move number to the right spot
                    array.splice(j, 0, array.splice(i, 1)[0]);
                }
            }
        }
    }

    return array;
}

console.log(insertionSort(numbers));
```

#
**[Back to The TOP](#section-overview)**

### <a name="merge-sort">Merge Sort and O(n log n)</a>

**JavaScript Example**:
```
const numbers = [99, 44, 6, 2, 1, 5, 63, 87, 283, 4, 0];

function mergeSort(array) {
    if (array.length === 1) {
        return array;
    }

    // Split Array in into right and left
    const length = array.length;
    const middle = Math.floor(length / 2);
    const left = array.slice(0, middle);
    const right = array.slice(middle);

    return merge(mergeSort(left), mergeSort(right));
}

function merge(left, right) {
    const result = [];
    let leftIndex = 0;
    let rightIndex = 0;

    while (leftIndex < left.length && rightIndex < right.length) {
        if (left[leftIndex] < right[rightIndex]) {
            result.push(left[leftIndex]);
            leftIndex++;
        } else {
            result.push(right[rightIndex]);
            rightIndex++;
        }
    }

    return result.concat(left.slice(leftIndex)).concat(right.slice(rightIndex));
}

const answer = mergeSort(numbers);
console.log(answer);
```
#
**[Back to The TOP](#section-overview)**

### Quick Sort

**JavaScript Example**:
```
const numbers = [99, 44, 6, 2, 1, 5, 63, 87, 283, 4, 0];

function quickSort(array, left, right) {
    const len = array.length;
    let pivot;
    let partitionIndex;

    if (left < right) {
        pivot = right;
        partitionIndex = partition(array, pivot, left, right);

        // Sort left and right
        quickSort(array, left, partitionIndex - 1);
        quickSort(array, partitionIndex + 1, right);
    }

    return array;
}

function partition(array, pivot, left, right) {
    let pivotValue = array[pivot];
    let partitionIndex = left;

    for (let i = left; i < right; i++) {
        if (array[i] < pivotValue) {
            swap(array, i, partitionIndex);
            partitionIndex++;
        }
    }

    swap(array, right, partitionIndex);

    return partitionIndex;
}

function swap(array, firstIndex, secondIndex) {
    let temp = array[firstIndex];

    array[firstIndex] = array[secondIndex];
    array[secondIndex] = temp;
}

function quickSortMine(array, left, right) {
    if (array.length <= 1) {
        return array;
    }

    let indexCounter = 0;

    for (let i = 0; i < array.length; i++) {
        if (array[i - indexCounter] > array[right - indexCounter]) {
            array.push(array.splice(i - indexCounter, 1)[0]);
            indexCounter++;
        }
    }

    let leftArray = array.slice(left, right - indexCounter);
    let rightArray = array.slice(right - indexCounter + 1, array.length);

    return quickSort(leftArray, 0, leftArray.length - 1).concat(array[right - indexCounter]).concat(quickSort(rightArray, 0, rightArray.length - 1));
}


//Select first and last index as 2nd and 3rd parameters
const answer = quickSort(numbers, 0, numbers.length - 1);
console.log(answer);
```
#
**[Back to The TOP](#section-overview)**