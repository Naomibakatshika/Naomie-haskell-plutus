HC10T6: Mutual Recursion in Eq for Blockchain

1. Defines a `Blockchain` data type.
2. Implements the `Eq` type class **manually** using **mutual recursion** between `(==)` and `(/=)`.

---

### ✅ Haskell Code

```haskell
-- Define the Blockchain data type
data Blockchain = Block String Blockchain | Genesis
  deriving Show

-- Implement Eq with mutual recursion between (==) and (/=)
instance Eq Blockchain where
  x == y = not (x /= y)
  x /= y = not (x == y)

-- To break the mutual recursion, we define helper functions
eqBlock :: Blockchain -> Blockchain -> Bool
eqBlock Genesis Genesis = True
eqBlock (Block d1 rest1) (Block d2 rest2) = d1 == d2 && eqBlock rest1 rest2
eqBlock _ _ = False

-- Redefine (==) and (/=) to use helper to avoid infinite loop
instance Eq Blockchain where
  x == y = eqBlock x y
  x /= y = not (eqBlock x y)

-- Example usage
main :: IO ()
main = do
  let chain1 = Block "Block1" (Block "Block2" Genesis)
  let chain2 = Block "Block1" (Block "Block2" Genesis)
  let chain3 = Block "Block1" (Block "BlockX" Genesis)

  print (chain1 == chain2)  -- True
  print (chain1 /= chain3)  -- True
```

---
