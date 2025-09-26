HC18T2: Functor Instance for Tree

```haskell
-- Define the binary tree data type
data Tree a = Empty
            | Node a (Tree a) (Tree a)
            deriving (Show, Eq)

-- Functor instance for Tree
instance Functor Tree where
  fmap _ Empty = Empty
  fmap f (Node x left right) = Node (f x) (fmap f left) (fmap f right)

-- Example usage
main :: IO ()
main = do
  let tree = Node 10 (Node 5 Empty Empty) (Node 15 Empty Empty)
  putStrLn $ "Original tree: " ++ show tree
  let doubledTree = fmap (*2) tree
  putStrLn $ "Doubled tree: " ++ show doubledTree
```

---

### Explanation:

* The `Functor` instance applies the function `f` to every value stored in the nodes of the tree recursively.
* `Empty` remains `Empty` after mapping.

---

### Sample Output:

```
Original tree: Node 10 (Node 5 Empty Empty) (Node 15 Empty Empty)
Doubled tree: Node 20 (Node 10 Empty Empty) (Node 30 Empty Empty)
```
