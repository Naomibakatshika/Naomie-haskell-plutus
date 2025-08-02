HC9T8: Recursive Sequence Data Type

---

### ✅ Haskell Code

```haskell
-- Define the recursive Sequence data type
data Sequence a
  = EmptySeq
  | Node a (Sequence a)
  deriving (Show)

-- Example: a sequence of integers
seqExample :: Sequence Int
seqExample = Node 1 (Node 2 (Node 3 EmptySeq))

-- Main function to print the example sequence
main :: IO ()
main = print seqExample
```

---

### 🧪 Sample Output

```
Node 1 (Node 2 (Node 3 EmptySeq))
```
