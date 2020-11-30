## 4th Day 

## convert an array to string
  ### join()
  
  This function convert the array into string . We can pass a seperator symbol to join method like , -  
  
  ```
  let games = ["football" , "cricket" , "swimming"]
  games.join(',')
  //"football,cricket,swimming"
  ```
  
  ### toString does the same but we cannot pass seperator to the function
  
## Challenge
**Print the largest (maximum) hourglass sum found in array.**
 Sample Input
 
 ```
1 1 1 0 0 0
0 1 0 0 0 0
1 1 1 0 0 0
0 0 2 4 4 0
0 0 0 2 0 0
0 0 1 2 4 0
 
 ```
 output :19
 
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

process.stdin.on('end', _ => {
    inputString = inputString.replace(/\s*$/, '')
        .split('\n')
        .map(str => str.replace(/\s*$/, ''));

    main();
});

function readLine() {
    return inputString[currentLine++];
}

// Complete the hourglassSum function below.
function hourglassSum(arr) {
    let maxSum = [ ];
    let sum = 0
  for(let i = 1 ; i < arr.length-1 ; i++){
    for(let j = 1 ; j <arr.length-1 ; j++){
        console.log(`${i} , ${j} ---- `)
        sum= 0;
        sum+=arr[i][j];
         
        for(let k=i-1;k<=i+1;k++){
            if(k != i){
            for(let l = j-1 ; l <= j+1;l++){
             sum += arr[k][l]
            }
            }      
        } 
        maxSum.push(sum);
    }
  }
  function checkMaximum(a,b){
      if(a < b){
          return -1;
      }
      if(a > b){
          return 1;
      }
      return 0;
  }
  maxSum.sort(checkMaximum)
  console.log(maxSum);
  return maxSum[maxSum.length-1]
}

function main() {
    const ws = fs.createWriteStream(process.env.OUTPUT_PATH);

    let arr = Array(6);

    for (let i = 0; i < 6; i++) {
        arr[i] = readLine().split(' ').map(arrTemp => parseInt(arrTemp, 10));
    }

    let result = hourglassSum(arr);

    ws.write(result + "\n");

    ws.end();
}

  
  
  ```
