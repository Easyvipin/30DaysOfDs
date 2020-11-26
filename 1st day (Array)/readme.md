# ARRAY ---

### CONCEPTS
  #### refrence ,deep copy
    Whenever we copy arr2 = arr1 , the reference of arr1 is stored in arr2 . So any changes in arr2 will also reflect in arr1
    Example:
    ```
    let arr1 = [0, 3, 5, 8];
    let arr2 = arr1;
    arr2[0] = 1;

    console.log(arr1);
    /* [1, 3, 5, 8] */
    ```
    So to alter this behaviour we use deep copy.
    In Deep Copy we copy the reference of each index of array.
    
    ```
     let counts = [];
     let sameCounts = [];

        for (let i = 0; i < 200; i++) {
          counts[i] = i + 1;
             }
       function copy(counts, sameCounts) {
       for (let i = 0; i < counts.length; i++) {
       sameCounts[i] = counts[i];
        } 
        }
      copy(counts, sameCounts);
     counts[0] = 999;
     console.log(sameCounts);
     console.log(counts);
    
    ```
    
  #### accessor
   ##### .indexOf()
   ##### .lastIndexOf()
   ##### .splice()
   ##### .toString()
   ##### .concat()
  #### Mutator functions
   ##### .push()
   ##### .pop()
   ##### .shift()
   ##### .unshift()

### Challanges

1. Reverse Array

 INPUT : [2 ,3, 4 ,1]
 OUTPUT : [1 , 4 , 3 , 2]

```
'use strict';

const fs = require('fs');

process.stdin.resume();
process.stdin.setEncoding('utf-8');

let inputString = '';
let currentLine = 0;

process.stdin.on('data', inputStdin => {
    inputString += inputStdin;
});

process.stdin.on('end', function() {
    inputString = inputString.replace(/\s*$/, '')
        .split('\n')
        .map(str => str.replace(/\s*$/, ''));

    main();
});

function readLine() {
    return inputString[currentLine++];
}

// Complete the reverseArray function below.
function reverseArray(a) {

return a.reverse();
}

function main() {
    const ws = fs.createWriteStream(process.env.OUTPUT_PATH);

    const arrCount = parseInt(readLine(), 10);

    const arr = readLine().split(' ').map(arrTemp => parseInt(arrTemp, 10));

    const res = reverseArray(arr);

    ws.write(res.join(' ') + '\n');

    ws.end();
}

```
