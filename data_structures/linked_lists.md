# Linked lists

For when you don't want the overhead of having to reallocate and copying of arrays when they surpass their original
capacity, you can use a linked list. They allow for effectively as many inserts as needed without overhead with the cost
of having access taking linear time.

There are many types of linked lists. They can be:

- **Circular**, where the last node's next point back to the first
- **Singly-linked**, where the nodes have a pointer to the next
- **Doubly-linked**, where the nodes have a pointer to the next and to the previous

## Structure

```cpp
struct ListNode {
  int val;
  ListNode *next;
  ListNode() : val(0), next(nullptr) {}
  ListNode(int x) : val(x), next(nullptr) {}
  ListNode(int x, ListNode *next) : val(x), next(next) {}
};
```

## Traversal

A traversal of a non-circular singly-linked list.

```cpp
void traverse(ListNode *root, vector<int>& traversed) {
  if (!root)
    return;
  
  traversed.push_back(root->val);
  traverse(root->next, traversed);
}

vector<int> traverse(ListNode* root) {
  vector<int> traversed;
  traverse(root, traversed);
  return traversed;
}
```