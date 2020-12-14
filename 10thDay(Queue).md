```javascript

/* Queues */
/* based on fifo */

/* method */

/* enqueue */
/* this Method add a element at the end of the queue */

/* dequeue */
/* This method remove the element from the front of the queue */

/* peek */
/* this method return the element which was first added into the queue and will be removed first */

/* size */

/* isEmpty */

/* class */

class Queue {
  constructor() {
    this.count = 0;
    this.lowestCount = 0;
    this.items = {};
  }
  enqueue(element) {
    this.items[this.count] = element;
    this.count++;
  }
  dequeue() {
    if (this.isEmpty()) {
      return undefined;
    }
    const result = this.items[this.lowestCount];
    delete this.items[this.lowestCount];
    this.lowestCount++;
    return result;
  }
  peek() {
    if (this.isEmpty()) {
      return undefined;
    }
    return this.items[this.lowestCount];
  }
  isEmpty() {
    return this.size === 0;
  }
  size() {
    return this.count - this.lowestCount;
  }
  clear() {
    this.items = {};
    this.count = 0;
    this.lowestCount = 0;
  }
  toString() {
    let items = [];
    for (let i = this.lowestCount ; i < this.count; i++) {
      items.push(this.items[i]);
    }
    return items.join(",");
  }
}
const bankLine = new Queue();
bankLine.enqueue("avinash"); /* avinash join the queue */
bankLine.enqueue("Vipin"); /* vipin join the queue after avinash */
bankLine.enqueue("Kunal"); /* Kunal join the queue after vipin and avinash */
bankLine.enqueue("Mohit"); /* Kunal join the queue after vipin and avinash */

console.log(bankLine);

/* 
0: "avinash"
1: "Vipin"
2: "Kunal"
3: "Mohit"
*/

/* dequeue */

let firstPerson = bankLine.dequeue();
console.log(firstPerson);
/* avinash */
console.log(bankLine);
/* 
1: "Vipin"
2: "Kunal"
3: "Mohit
*/

/* peek */

console.log(bankLine.peek());
/* Vipin  */

/* size */

console.log(bankLine.size());
/*  3 */

/* isEmpty */

console.log(bankLine.isEmpty());
/* false */

/* toString */
console.log(bankLine.toString());
console.log(bankLine);

/*vipin,kunal,mohit */


```
