# Technical Writing Assignment

For guidance on setting up and submitting this assignment, refer to the Marcy lab School Docs How-To guide for [Working with Short Response and Coding Assignments](https://marcylabschool.gitbook.io/marcy-lab-school-docs/fullstack-curriculum/how-tos/working-with-assignments#how-to-work-on-assignments).

## Prompt 1

Imagine you are giving a brief lesson on Recursion to a relatively new programmer. In your lesson make sure to include the following:

* A formal definition of recursion (feel free to quote an official source like MDN)
* An example in code.
* An explanation of the code example.
* An explanation of the kinds of functions that are best solved using recursion.

### Response 1

## Prompt 2

Imagine you are giving a brief lesson on the Tree data structure to a relatively new programmer. In your lesson make sure to include the following:

* A formal definition of a Tree (feel free to quote an official source like MDN)
* Definitions for key terms like **root**, **leaf**, **depth**, and **height** as they relate to Trees
* An example in code.
* An explanation of the code example.

### Response 2

## Prompt 3

Any iterative function can be written recursively. Provide an example of an iterative function and the same function written recursively. Then, explain the benefits and/or drawbacks of each approach.

### Response 3

 > An example of a Iterative Function

```js
    function Iterative(n) {
        let result = 1;

        for (let i = 1; i <= n; i++) {
        result *= i;
    }
        return result;
    }
```

> An example of a Recursive Function

```js
function Recursive(n) {
  if (n === 0 || n === 1) {
    return 1;
  } else {
    return n * Recursive(n - 1);
  }
}
```

### Pros & Cons for a Iterative approach 
#### Pros:
- Better for performance and memory usage.

- Safer for large inputs. No risk of exceeding call stack size.

- Often preferred in production code for efficiency.

  #### Cons: 
- Can be less elegant, especially for problems like recursion-based algorithms like tree traversal and backtracking.

### Pros & Cons for a Recursive approach
#### Pros
  - Cleaner and more readable, especially for problems that are naturally recursive.

  - Great for divide-and-conquer, tree/graph traversal, etc.
#### Cons 
  - Call stack grows with each function call—JavaScript has limited stack size, so doing something like Recursive(100000) will crash.

  - Slight performance hit due to function call overhead.

## Prompt 4

Depth-first-search is an algorithm of traversing through a tree that explores as far as possible along a single branch before backtracking and exploring other branches. The three approaches for depth-first-search are "inorder", "preorder", and "postorder". 

Using this tree as an example, explain the differences between these three approaches, providing implementations of each (recursive or iterative, its up to you but one of them is definitely cleaner).

```
    A
   / \
  B   C
 / \   \
D   E   F
```

### Response 4

#### Inorder Traversal
* Inorder Traversal (Left → Root → Right)
* Traverse the left subtree first, then visit the current node, then the right subtree.
* In binary search trees, this gives nodes in sorted order.
* Traveral order: D B E A C F

>Implementation of Inorder Traversal

```js

function inorder(node) {
  if (node) {
    inorder(node.left);
    console.log(node.val);
    inorder(node.right);
  }
}
```

#### Preorder Traversal
* Preorder Traversal (Root → Left → Right)
* Visit the current node first, then traverse the left subtree, and finally the right subtree.
* A comparison I came saw that I liked was "Deal with current first, then children."
* Traversal Order: A B D E C F

>Implemetation of Preorder Traversal 

```js 

function preorder(node) {
  if (node) {
    console.log(node.val);
    preorder(node.left);
    preorder(node.right);
  }
}
```

### Postorder Traveral
* Postorder Traversal (Left → Right → Root)
* Traverse the left subtree first, then the right subtree, and finally visit the current node.
* Useful for operations where you need to deal with child nodes before the parent (e.g., deleting tree nodes).
* Traversal Order: D E B F C A


>Implementation of Postorder raversal 

```js 

function postorder(node) {
  if (node) {
    postorder(node.left);
    postorder(node.right);
    console.log(node.val);
  }
}
```