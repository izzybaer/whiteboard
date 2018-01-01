balance a Binary Tree and return the balanced tree or false

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

const maxHeight = (node) => {
  node === null ? 0 : Math.max(maxHeight(node.left), maxHeight(node.right)) + 1;
};

const minHeight = (node) => {
  node === null ? 0 : Math.min(minHeight(node.left), minHeight(node.right)) + 1;
};

const height = (node) => {
  node === null ? 0 : Math.max(height(node.left), height(node.right)) + 1;
};

const isBalanced = (root) => {
  if(root === null) {
    return true;
  }

  let leftHeight = height(root.left);
  let rightHeight = height(root.right);

  let diff = Math.abs(leftHeight - rightHeight);

  diff <= 1 ? isBalanced(root.left) && isBalanced(root.right) : false;
}
```
