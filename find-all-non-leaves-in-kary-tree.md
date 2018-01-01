find all of the non leaves in k-ary tree and return an array with all the values or nodes

Run on repl: https://repl.it/repls/LimeNocturnalWhippoorwill

```js
// OBJECT ORIENTED APPROACH

class KAryNode {
  constructor(value, children = []) {
    this.value = value;
    this.children = children;
  }
}

class KAryTree {
  constructor() {
    this.root = null;
  }

  getNonLeafValues() {
    let nodes = this.getNonLeafNodes();
    return nodes.map(node => node.value);
  }

  getNonLeafNodes() {
    let accumulator = [];
    this._getNonLeafNodes(this.root, accumulator);
    return accumulator;
  }

  _getNonLeafNodes(node, accumulator) {
    if (!node) {
      return;
    }
    if (node.children.length === 0) {
      // leaf node
      return
    }
    accumulator.push(node);
    node.children.forEach(node => this._getNonLeafNodes(node, accumulator));
  }
}

tree = new KAryTree();
tree.root = new KAryNode(12, [
  new KAryNode(8, [
    new KAryNode(7, [
      new KAryNode(4)
    ]),
    new KAryNode(6)
  ]),
  new KAryNode(10),
  new KAryNode(14, [
    new KAryNode(99)
  ])
]);

console.log("values:", tree.getNonLeafValues());
```

Run on repl: https://repl.it/@izabellabaer/findNonLeavesKAryTree
```javascript
// FUNCTIONAL APPROACH

class kAryTree{
  constructor(value){
    this.value = value;
    this.children = [];
  }
}

let one = new kAryTree(1);
let two = new kAryTree(2);
let three = new kAryTree(3);
let four = new kAryTree(4);
let five = new kAryTree(5);
let six = new kAryTree(6);

one.children.push(two);
one.children.push(three);
one.children.push(six);
three.children.push(four);
three.children.push(five);
six.children.push(five);

const findNonLeaves = (tree) => {
  if(!(tree instanceof kAryTree)) return null;
  let nodes = [];

  const traverse = (tree) => {
    if(tree.children.length >= 1) {
      nodes.push(tree);
      tree.children.forEach(node => {
      traverse(node);
      });
    }
  };
  traverse(tree);
  return nodes;
};

findNonLeaves(one); // returns 1, 3, 6 (non leaves)
```
