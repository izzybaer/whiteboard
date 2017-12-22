write a function to take in a tree and return an array with all of the leaves in binary tree

```javascript

class TreeNode {
  constructor(value, left, right){
    this.value = value;
    this.left = left;
    this.right = right;
  }
}

class BinaryTree {
  constructor() {
    this.root = null;
  }
}

let tree = new BinaryTree();
let one = new TreeNode(1);
let two = new TreeNode(2);
let three = new TreeNode(3);
let four = new TreeNode(4);
let five = new TreeNode(5);
let six = new TreeNode(6);
let seven = new TreeNode(7);


// let one = new BinaryTree(1);
// let two = new BinaryTree(2);
// let three = new BinaryTree(3);
// let four = new BinaryTree(4);
// let five = new BinaryTree(5);

one.left = two;
one.right = three;

three.left = four;
three.right = five;

five.left = six;
five.right = seven;


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
