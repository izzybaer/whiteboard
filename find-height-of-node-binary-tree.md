calculate the height of a node in a binary tree and return an integer representing the number of edges on the longest downward path

```javascript

// FUNCTIONAL APPROACH

class BinaryTree{
  constructor(value){
    this.value = value;
    this.left = null;
    this.right = null;
  }
}

let one = new BinaryTree(1);
let two = new BinaryTree(2);
let three = new BinaryTree(3);
let four = new BinaryTree(4);
let five = new BinaryTree(5);
let six = new BinaryTree(6);
let seven = new BinaryTree(7);
let eight = new BinaryTree(8);
let nine = new BinaryTree(9);

four.left = two;
four.right = six;

two.left = one;
two.right = three;

six.left = five;
six.right = eight;

eight.left = seven;
eight.right = nine;

const nodeHeight = (node) => {
  if(!(node instanceof BinaryTree)) return null;

  let left = node.left ? nodeHeight(node.left) : null;
  let right = node.right ? nodeHeight(node.right) : null;

  return (left == null && right == null) ? 0 :
    Math.max(left, right) + 1;
}

nodeHeight(four); // returns 3 (height of tree)

```
