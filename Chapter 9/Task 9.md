HC9T9: Check for Element in a Sequence

---

### ✅ Haskell Code

```haskell
-- Define the recursive Sequence data type
data Sequence a
  = EmptySeq
  | Node a (Sequence a)
  deriving (Show)

-- Function to check if an element exists in the Sequence
elemSeq :: Eq a => a -> Sequence a -> Bool
elemSeq _ EmptySeq       = False
elemSeq x (Node y rest)
  | x == y    = True
  | otherwise = elemSeq x rest

-- Example sequence of integers
seqExample :: Sequence Int
seqExample = Node 1 (Node 2 (Node 3 EmptySeq))

-- Main function to test elemSeq
main :: IO ()
main = do
  print $ elemSeq 2 seqExample  -- Should print True
  print $ elemSeq 5 seqExample  -- Should print False
```

---

### 🧪 Sample Output

```
True
False
```
