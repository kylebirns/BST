# BST
Practice with Traversing BST

## Basic BST Class

```javascript
class BST{
	constructor(value){
		this.value = value
		this.left = null
		this.right = null
	}
	insert(value){
	...
	}
}

```

Below are javascript implementations of Depth-First-Search (inorder, preorder, and postorder)

## Depth First Search

```
Example Tree:
        10
        / \
       5   15
      / \    \
     2   5    22
    /
   1
```

For depth first search we can use the call stack (recursion) or the stack ADT (LIFO). You can use an isVisited flag so that you do not end up in an infinite loop.

### Inorder
```javascript
//returns [1, 2, 5, 5, 10, 15, 22]
function inOrderTraverse(tree, array) {
	if(tree){
		inOrderTraverse(tree.left, array)
		array.push(tree.value)
		inOrderTraverse(tree.right, array)
	}
	return array
}
```

### Preorder
```javascript
//returns [10, 5, 2, 1, 5, 15, 22]
function preOrderTraverse(tree, array) {
	if(tree){
		array.push(tree.value)
		preOrderTraverse(tree.left, array)
		preOrderTraverse(tree.right, array)
	}
	return array
}
```

### Postorder
```javascript
//returns [1, 2, 5, 5, 22, 15, 10]
function postOrderTraverse(tree, array) {
	if(tree){
		postOrderTraverse(tree.left, array)
		postOrderTraverse(tree.right, array)
		array.push(tree.value)
	}
	return array
}
```

