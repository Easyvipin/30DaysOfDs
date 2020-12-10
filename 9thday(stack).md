## stack object 

```
/* create a object stack */

class Stack {
  constructor() {
    this.count = 0;
    this.items = {};
  }
  push(element) {
    this.count++;
    this.items[this.count] = element;
  }
  pop(element) {
    if (this.count > 0) {
      let delItem = this.items[this.count];
      delete this.items[this.count];
      this.count--;
      return delItem;
    } else {
      console.log("No element to pop");
    }
  }
  peek() {
    if (this.count > 0) {
      return this.items[this.count];
    } else {
      console.log("Stack is empty add a item with push method");
    }
  }
  size() {
    return this.count;
  }
  isEmpty() {
    return this.count === 0;
  }
  clear() {
    this.count = 0;
    this.item = {};
  }
}

let stack = new Stack();
stack.push("deer");
stack.push("dog");
stack.push("donkey");
console.log(stack);

/* count: 3 */
/* items: Object
1: "deer"
2: "dog"
3: "donkey" */

stack.pop();

/* count: 2
items: Object
1: "deer"
2: "dog" */

let top = stack.peek();
console.log(top);

console.log(stack.isEmpty());

/* dog 
false */




```
