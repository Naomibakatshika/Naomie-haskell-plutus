HC9T10: Binary Search Tree Data Type

---

### ✅ Haskell Code

```haskell
-- Define the BST data type
data BST a
  = EmptyTree
  | Node a (BST a) (BST a)
  deriving (Show)

-- Example BST of Ints
exampleBST :: BST Int
exampleBST =
  Node 10
    (Node 5 EmptyTree EmptyTree)
    (Node 15 EmptyTree EmptyTree)

-- Main function to print the example BST
main :: IO ()
main = print exampleBST
```

---

### 🧪 Sample Output

```
Node 10 (Node 5 EmptyTree EmptyTree) (Node 15 EmptyTree EmptyTree)
```
