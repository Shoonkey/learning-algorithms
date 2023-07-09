# Binary trees

**Binary trees** are data structures that build up on the idea of [linked lists](./linked_lists.md), but they help in storing data in a sorted way.

Every node has a value, a pointer to a left child and a pointer to a right child; the term "binary" tree comes from
that idea, that it can only go two directions from a given node. If you can go n directions from a given node, it
becomes a n-ary tree, which sounds super cool and honestly I think it is.

Binary trees in computing are usually represented with the root on top, so they kind of grow downwards instead of up! :D

- The main node, at the top of the tree, is called **root** node;
- All nodes but the root have a parent node, and may have child nodes.
- A node without children is naturally at the bottom of the tree, and is called a **leaf** node.

## Structure

```cpp
struct TreeNode {
  int val;
  TreeNode *left;
  TreeNode *right;
  TreeNode() : val(0), left(nullptr), right(nullptr) {}
  TreeNode(int x) : val(x), left(nullptr), right(nullptr) {}
  TreeNode(int x, TreeNode *left, TreeNode *right) : val(x), left(left), right(right) {}
}
```

## Traversal

There are three types of traversal (going through the tree): inorder, preorder and post order.
The traversal is usually recursive in nature, as we access a permutation of the order [node, left child, right child]
for every node of the tree.

- **Inorder** goes left -> root -> right, so it the first element is the leftmost leaf, then its root,
then its root's right child, then following the same logic for the root's root;

- **Preorder** goes root -> left -> right, following the same logic for all nodes as well;

### Using recursion

As usual with linked lists and by the nature of how they're constructed the traversal of trees is relatively
trivial with recursion. Here's an example of an inorder traversal in C++:

```cpp
void traverse(TreeNode *root, vector<int>& traversed) {
  if (!root)
    return;
  
  traverse(root->left, traversed);
  traversed.push_back(root->val);
  traverse(root->right, traversed);
}

vector<int> inorderTraversal(TreeNode* root) {
  vector<int> traversed;
  traverse(root, traversed);
  return traversed;
}
```

### Using iteration

Recursion takes more memory than iteration and is often slower than iteration, at least in imperative languages,
due to the overhead of allocating a stack frame and keeping in memory all the function calls.
To use less memory and potentially be faster, one might want to traverse iteratively. You could do that using a stack.

```cpp
vector<int> inorderTraversal(TreeNode* root) {
  vector<int> traversed;
  vector<TreeNode*> stack;
  TreeNode* curr = root;

  while (curr != NULL || !stack.empty()) {
    while (curr != NULL) {
      stack.push_back(curr);
      curr = curr->left;
    }

    curr = stack.back();
    stack.pop_back();
    traversed.push_back(curr->val);
    curr = curr->right;
  }

  return traversed;
}
```