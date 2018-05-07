```js
class BinarySearchTree {
  constructor(value) {
    this.value = value;
    this.left = null;
    this.right = null;
  }

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
        if (seen[keey] === maxOccur) results.push(parseInt([key]))
    })
    return results;
}

findMode()
```