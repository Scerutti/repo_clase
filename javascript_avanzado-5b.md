## Ejemplo de AVL (es una alternativa a BST)

### Que es AVL?
Un árbol AVL es un tipo especial de árbol binario ideado por los matemáticos soviéticos Adelson-Velskii y Landis. Fue el primer árbol de búsqueda binario auto-balanceable que se ideó

```javascript
function createAVLTreeNode(value) {
  return {
    value,
    left: null,
    right: null,
    height: 1,
  };
}

function getHeight(node) {
  return node ? node.height : 0;
}

function balanceFactor(node) {
  return getHeight(node.left) - getHeight(node.right);
}

function rotateLeft(node) {
  const newRoot = node.right;
  node.right = newRoot.left;
  newRoot.left = node;
  node.height = Math.max(getHeight(node.left), getHeight(node.right)) + 1;
  newRoot.height = Math.max(getHeight(newRoot.left), getHeight(newRoot.right)) + 1;
  return newRoot;
}

function rotateRight(node) {
  const newRoot = node.left;
  node.left = newRoot.right;
  newRoot.right = node;
  node.height = Math.max(getHeight(node.left), getHeight(node.right)) + 1;
  newRoot.height = Math.max(getHeight(newRoot.left), getHeight(newRoot.right)) + 1;
  return newRoot;
}

function insertAVLTree(root, value) {
  if (!root) {
    return createAVLTreeNode(value);
  }

  if (value < root.value) {
    root.left = insertAVLTree(root.left, value);
  } else if (value > root.value) {
    root.right = insertAVLTree(root.right, value);
  } else {
    return root;
  }

  root.height = Math.max(getHeight(root.left), getHeight(root.right)) + 1;

  const balance = balanceFactor(root);

  if (balance > 1 && value < root.left.value) {
    return rotateRight(root);
  }
  if (balance < -1 && value > root.right.value) {
    return rotateLeft(root);
  }
  if (balance > 1 && value > root.left.value) {
    root.left = rotateLeft(root.left);
    return rotateRight(root);
  }
  if (balance < -1 && value < root.right.value) {
    root.right = rotateRight(root.right);
    return rotateLeft(root);
  }

  return root;
}

// Ejemplo de uso
let avlTreeRoot = null;
avlTreeRoot = insertAVLTree(avlTreeRoot, 10);
avlTreeRoot = insertAVLTree(avlTreeRoot, 5);
avlTreeRoot = insertAVLTree(avlTreeRoot, 20);
```

## Binary Search Tree (Árbol Binario de Búsqueda)

### Que es BTS?
Un Binary Search Tree (BST) es una variante de un árbol binario donde los valores se organizan de manera que los valores menores están a la izquierda y los valores mayores están a la derecha. 

```javascript
function createBSTNode(value) {
  return {
    value,
    left: null,
    right: null,
  };
}

function insertBST(root, value) {
  if (!root) {
    return createBSTNode(value);
  }

  if (value < root.value) {
    root.left = insertBST(root.left, value);
  } else if (value > root.value) {
    root.right = insertBST(root.right, value);
  }

  return root;
}

// Ejemplo de uso
let bstRoot = null;
bstRoot = insertBST(bstRoot, 10);
bstRoot = insertBST(bstRoot, 5);
bstRoot = insertBST(bstRoot, 20);
```
