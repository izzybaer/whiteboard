```js
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


const findMode = (tree) => {
    let seen = {};
    let results = [];
    let maxOccur = 0;

    const traverse = (tree) => {
        if (tree.left) traverse(tree.left)
        if (tree.right) traverse(tree.right)

        seen[tree.val] ? seen[tree.val]++ : seen[tree.val] = 1;

        if (maxOccur < seen[tree.val]) maxOccur = seen[tree.val];
    }

    Object.keys(seen).forEach(key => {
        if (seen[key] === maxOccur) results.push(parseInt([key]))
    })
    return results;
}

findMode()
```