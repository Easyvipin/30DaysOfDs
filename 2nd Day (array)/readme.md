## 2nd Day 

### Es6 new array functions
  1. `for of  / for in` 
    for of loop iterate the values of the array where as for in iterate the keys or index;
    example:
    ```
    let no = [2,3,4,5]
    for ( let i in no ) {
      console.log(i)
      }
      // 2 ,3 ,4, 5 
      
    // for in
    for (let i in no){
     console.log(i)
     }
     // 0,1,2,3 
    ```
  
  2. `.enteries()`
     This function returns an iterable object which contains key:value pairs.
     
     ```
     let numbers = new Array(2, 3, 4, 5, 6);
     let aEnteries = numbers.entries();
     console.log(aEnteries.next().value);
     console.log(aEnteries.next().value);
     /* [0,2] [1,3] */

     ```
  3. `.keys / .values` does the same as enteries but keys return only keys and values return values.
  4. `.from()` 
      This method copies the array from another array without copying its refrence. So any alter to the copied array will not effect the original array.
      ```
        let count = [2, 4, 5, 6, 7, 8, 9, 13];

        let count2 = Array.from(count);
        count2[8] = 14;
        console.log(count); /* [2, 4, 5, 6, 7, 8, 9, 13]*/
        console.log(count2); /* [2, 4, 5, 6, 7, 8, 9, 13, 14] */ 
      
      ```
      
   5. `.fill()`
      ```
      let games = ["football", "basket ball", "swimming", "cricket"];
      games.fill("football");
      console.log(games);
      /* ["football", "football", "football", "football"] */
      /* we can also pass the index from where we want to start and end the filling(inclusive) */
      let games2 = ["football", "basket ball", "swimming", "cricket"];
      games2.fill("football", 2, 4);
      console.log(games2);
      /* ["football", "basket ball", "football", "football"] */
   
     
      ```
    6. `.copyWithin()`
    
      This method copies the sequence of elements from array and insert into in the same array with specified starting index.
      
      ```
      let noArray = [2, 3, 4, 5, 6];
      noArray.copyWithin(0, 2);
      console.log(noArray);

      /* [4, 5, 6, 5, 6] */
      
      ```
 
