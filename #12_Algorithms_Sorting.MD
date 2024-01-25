<h1 align="center">Algorithms: Sorting</h1>

### Section overview

* **[Sorting Introduction](#introduction-to-algorithms)**
* **[Bubble Sort](#bubble-sort)**
* **[Selection Sort](#selection-sort)**
* **[Insertion Sort](#insertion-sort)**
* **[Merge Sort and O(n log n)](#merge-sort)**


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


#
**[Back to The TOP](#section-overview)**