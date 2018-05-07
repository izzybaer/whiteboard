```js
class BinaryTree {
    constructor(value) {
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

const findCommon = (root, p, q) => {
    if (p.value === root.value || q.value === root.value) return root.value;
    if (p.value < root.value && q.value > root.value) return root.value;
    if (p.value < root.value && q.value < root.value) return findCommon(root.left, p, q);
    if (p.value > root.value && q.value > root.value) return findCommon(root.right, p, q);
}
// O(log n - 1)

console.log(findCommon(four, two, three))
```