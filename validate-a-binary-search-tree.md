given a single node, validate the binary search tree ensuring that every nodes left child is less than the parent nodes value and that every nodes right child is greater than the parent

```javascript

// first method - recursion
// recurse through, call validate(node, min, max)

// set max to value of root node
// move left and compare value of root.left to value of root
// once we compare we move left or right
// and reset max each time
// when we move left we update the max value
// when we move right we update the min value
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

four.left = two;
four.right = six;

two.left = one;
two.right = three;

six.left = five;
six.right = seven;

const validate = (node, min = null, max = null) => {
  if(max !== null && node.value > max) {
    return false;
  }
  if(min !== null && node.value < min) {
    return false;
  }

  if(node.left && !validate(node.left, min, node.value)) {
    // if node.left exists and calling validate with node.left, min, and the value of the current node returns false then something went wrong and we return false
    return false;
  }
  if(node.right && !validate(node.right, node.value, max)) {
    return false
  }

  return true;
}
validate(three);
```
