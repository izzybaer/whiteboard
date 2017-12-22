write a function to take in a tree and return an array with all of the leaves in binary tree

```javascript

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

one.left = two;
one.right = three;

three.left = four;
three.right = five;

const findLeaves = (tree) => {
  if(!(tree instanceof BinaryTree))
  let leaves = [];

  let reportLeaves = (tree) => {
    if(tree.left == null && tree.right == null) leaves.push(tree);
    if(tree.left !== null) reportLeaves(tree.left);
    if(tree.right !== null) reportLeaves(tree.right);


  }
  reportLeaves(tree);
  return leaves;
}

findLeaves(one)

// time is big O(n)
// space is big O(lg n) the height of the tree

```
