
### Array challenges
  ## reverse a string
    ```
    /* reverse a string */

    let string = "hello world how are you?"

    let arryString = string.split("",);
    console.log(arryString);
    /* ["h", "e", "l", "l", "o", " ", "w", "o", "r", "l", …] */
    /* ...........reversing the string  */

    arryString.reverse() 
    /* ["?", "u", "o", "y", " ", "e", "r", "a", " ", "w", …] */
    let reverseString = arryString.join("");
    console.log(reverseString);
    /* ? u o y   e r a   w o h   d l r o w   o l l e h  */

    ```

   ## Palindrome
 ```
     * palindrome   */
/* palindrome is a word or a phrase which read same even reserved. */

function checkPalindrome(string){
  console.log(string)
  let checkString = string.split("").join("").toLowerCase();
   console.log(checkString);
 const reverseString = string.split("").reverse().join("").toLowerCase();
 console.log(reverseString);
 if(reverseString == checkString){
   return true;
 }
 else {
   return false;
 }
}
console.log(checkPalindrome("Do geese see God".replace(/ /g,"")))

 ```
    
    
