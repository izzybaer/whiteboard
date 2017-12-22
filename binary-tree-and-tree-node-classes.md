Steve Geluso's approach to Trees and Nodes and BSTs


```javascript

class TreeNode {
  constructor(value, left, right) {
    this.value = value;
    this.left = left;
    this.right = right;
  }
}

class BinaryTree {
  constructor(){
    this.root = null;
  }
}


// this is a better approach then just doing...
// because we don't have to redundantly check if the node is a node or exists before recursively calling functions on it
class BinaryTree {
  constructor(value){
    this.value = value;
    this.left = null;
    this.right = null;
  }
}

```
