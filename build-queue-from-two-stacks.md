build a queue using two stacks, DO NOT create an array inside of the Queue class

// method 1 - make enQueue operation costly
// this method makes sure that oldest entered element is always at the top of stack 1, so that deQueue operation just pops from stack1
// to put the element at the top of stack1, stack2 is used

// method 2 - make deQueue operation costly (better method)
// in enQueue operation the new element is entered at top of stack1
// in deQueue operation, if stack2 is empty then all the elements are moved to stack2 and finally the top of stack2 is returned

method 1 moves all the elements twice in enQueue operation, while method 2 (in deQueue operation) moves the elements once and moves elements only if stack2 empty.



```javascript
class Stack {
  constructor() {
    this.data = [];
  }

  push(record) {
    this.data.push(record);
  }

  pop() {
    return this.data.pop();
  }

  peek() {
    return this.data[this.data.length -1];
  }
}

class Queue {
  constructor() {
    this.first = new Stack();
    this.second = new Stack();
  }

  add(data) {
    this.first.push(data);
  }

  remove() {
    while(this.first.peek()) {
      this.second.push(this.first.pop());
    }

    let data = this.second.pop();

    while(this.second.peek()) {
      this.first.push(this.second.pop())
    }

    return data;
  }

  peek() {
    while(this.first.peek()) {
      this.second.push(this.first.pop());
    }

    let data = this.second.peek();

    while(this.second.peek()) {
      this.first.push(this.second.pop());
    }

    return data;
  }
}

let queue = new Queue();

queue.add(5);
queue.add(6);
queue.add(8);
queue.add(10);

console.log('peeking at: ', queue.peek());
console.log('removing: ', queue.remove());
console.log('peeking at: ', queue.peek());
console.log('removing: ', queue.remove());
console.log('peeking at: ', queue.peek());
console.log('removing: ', queue.remove());
console.log('queue', queue);
```
