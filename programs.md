# JavaScript Program to Reverse a String
<h6>Example 1: Reverse a String Using for Loop</h6>

```js
// program to reverse a string
function reverseString(str) {

    // empty string
    let newString = "";
    for (let i = str.length - 1; i >= 0; i--) {
        newString += str[i];
    }
    return newString;
}

// take input from the user
const string = prompt('Enter a string: ');

const result = reverseString(string);
console.log(result);
 ```
 
 <b>Output</b>
 
 ```js
 Enter a string: hello world
`dlrow olleh
 ```
 
 <h6>Example 2: Reverse a String Using built-in Methods</h6>
 
 ```js
 // program to reverse a string
function reverseString(str) {

    // return a new array of strings
    const arrayStrings = str.split("");
   
    // reverse the new created array elements
    const reverseArray = arrayStrings.reverse();
 
    // join all elements of the array into a string
    const joinArray = reverseArray.join("");
    
    // return the reversed string
    return joinArray;
}
 
// take input from the user
const string = prompt('Enter a string: ');

const result = reverseString(string);
console.log(result);
```

# Quick sort

```js
var items = [5,3,7,6,2,9];
function swap(items, leftIndex, rightIndex){
    var temp = items[leftIndex];
    items[leftIndex] = items[rightIndex];
    items[rightIndex] = temp;
}
function partition(items, left, right) {
    var pivot   = items[Math.floor((right + left) / 2)], //middle element
        i       = left, //left pointer
        j       = right; //right pointer
    while (i <= j) {
        while (items[i] < pivot) {
            i++;
        }
        while (items[j] > pivot) {
            j--;
        }
        if (i <= j) {
            swap(items, i, j); //sawpping two elements
            i++;
            j--;
        }
    }
    return i;
}

function quickSort(items, left, right) {
    var index;
    if (items.length > 1) {
        index = partition(items, left, right); //index returned from partition
        if (left < index - 1) { //more elements on the left side of the pivot
            quickSort(items, left, index - 1);
        }
        if (index < right) { //more elements on the right side of the pivot
            quickSort(items, index, right);
        }
    }
    return items;
}
// first call to quick sort
var sortedArray = quickSort(items, 0, items.length - 1);
console.log(sortedArray); //prints [2,3,5,6,7,9]
```

# Bubble Sort

```js
let bubbleSort = (inputArr) => {
    let len = inputArr.length;
    for (let i = 0; i < len; i++) {
        for (let j = 0; j < len; j++) {
            if (inputArr[j] > inputArr[j + 1]) {
                let tmp = inputArr[j];
                inputArr[j] = inputArr[j + 1];
                inputArr[j + 1] = tmp;
            }
        }
    }
    return inputArr;
};
```

# Fibonacci Series Up to n Terms

```js
const number = parseInt(prompt('Enter the number of terms: '));
let n1 = 0, n2 = 1, nextTerm;

console.log('Fibonacci Series:');

for (let i = 1; i <= number; i++) {
    console.log(n1);
    nextTerm = n1 + n2;
    n1 = n2;
    n2 = nextTerm;
}
```

# Convert multi dimentional array to single dimention (Array Flat) without using library function

```js
var a = [1, [2, 3], [4, 5], 6, [7, 8, [9, [10, 11]]]];

function flatten(arr){
    return arr.reduce((acc, item)=>{
      if(Array.isArray(item)){
        return acc.concat(flatten(item))
      }
      
      return acc.concat(item);
    }, []);
}

console.log("Result : ", flatten(a));
```

# Using Array.prototype.flat() (built-in function, ES2019+)
```js
const nestedArray = [1, [2, 3], [4, 5], 6, [7, 8, [9, [10, 11]]]];
const flatArray = nestedArray.flat(Infinity); // Infinity to flatten any depth
console.log(flatArray); 
```

<b>Output</b>


```js
Result :  [1, 2, 3, 4,  5, 6, 7, 8, 9, 10, 11]
```
