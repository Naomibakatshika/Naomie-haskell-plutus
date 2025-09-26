HC18T3: incrementTreeValues Function

```haskell
-- Define the binary tree data type
data Tree a = Empty
            | Node a (Tree a) (Tree a)
            deriving (Show, Eq)

-- Functor instance for Tree
instance Functor Tree where
  fmap _ Empty = Empty
  fmap f (Node x left right) = Node (f x) (fmap f left) (fmap f right)

-- incrementTreeValues adds 1 to every value in the tree
incrementTreeValues :: Num a => Tree a -> Tree a
incrementTreeValues = fmap (+1)

-- Example usage
main :: IO ()
main = do
  let tree = Node 1 (Node 2 Empty Empty) (Node 3 Empty Empty)
  putStrLn $ "Original tree: " ++ show tree
  let incrementedTree = incrementTreeValues tree
  putStrLn $ "Incremented tree: " ++ show incrementedTree
```

---

### Output:

```
Original tree: Node 1 (Node 2 Empty Empty) (Node 3 Empty Empty)
Incremented tree: Node 2 (Node 3 Empty Empty) (Node 4 Empty Empty)
```
