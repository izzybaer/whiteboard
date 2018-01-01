write a function to take in a tree and return an array with all of the leaves in a binary tree

```javascript
// OBJECT ORIENTED APPROACH

class TreeNode {
  constructor(value, left, right){
    this.value = value;
    this.left = left;
    this.right = right;
  }

  toString() {
    return this.value;
  }
}

class BinaryTree {
  constructor() {
    this.root = null;
  }

  toString() {
    return this._toString(this.root)
  }

  // recursive helper function that starts at the root
  // if no node, return empty string
  // else return this._toString(node.left) RECURSION
  // this._toString(node.left) goes back up to the top of the function


  _toString(node) {
    if(!node) {
      return '';
    }
    let leftStr = this._toString(node.left);
    let rightStr = this._toString(node.right);
    return leftStr + ' ' + node.value + ' ' + rightStr;
  }

  // always pass in this.root as the starting point
  // this public function invokes the private function

  findLeaves() {
    let leaves = [];
    this._findLeaves(this.root, leaves);
    return leaves;
  }

  // _ signifies private vs. line 37 which is public, and calls _findLeaves()
  _findLeaves(node, leaves) {
      if(!node) {
        return;
      } else if (!node.left && !node.right) {
        leaves.push(node);
      } else {
        this._findLeaves(node.left, leaves);
        this._findLeaves(node.right, leaves);
      }
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

// always start at the middle
// for us the middle between 1 and 7 is 4

four.left = two;
two.left = one;
two.right = three;

four.right = six;
six.left = five;
six.right = seven;

tree.root = four;

console.log('tree: ' + tree);
console.log('leaves: ' + tree.findLeaves());

// time is big O(n)
// space is big O(lg n) the height of the tree

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

one.left = two;
one.right = three;

three.left = four;
three.right = five;

const findLeaves = (tree) => {
  if(!(tree instanceof BinaryTree)) return null;
  let leaves = [];

  let reportLeaves = (tree) => {
    if(tree.left == null && tree.right == null) leaves.push(tree);
    if(tree.left !== null) reportLeaves(tree.left);
    if(tree.right !== null) reportLeaves(tree.right);


  }
  reportLeaves(tree);
  return leaves;
}

findLeaves(one); // returns 2, 4, 5

// time is big O(n)
// space is big O (lg n) the height of the tree
```
