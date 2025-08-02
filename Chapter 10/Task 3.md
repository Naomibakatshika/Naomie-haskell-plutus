HC10T3: Comparable Type Class

1. Defines a custom data type `Blockchain`.
2. Defines a **type class** `Comparable` with a method `compareWith :: a -> a -> Ordering`.
3. Implements an **instance of `Comparable` for `Blockchain`**.

---

### ✅ Haskell Code

```haskell
-- Define the Blockchain type
data Blockchain = Blockchain
  { name        :: String
  , blockHeight :: Int
  } deriving (Show)

-- Define the Comparable type class
class Comparable a where
  compareWith :: a -> a -> Ordering

-- Implement Comparable for Blockchain
instance Comparable Blockchain where
  compareWith b1 b2 = compare (blockHeight b1) (blockHeight b2)

-- Example usage
main :: IO ()
main = do
  let chain1 = Blockchain "Bitcoin" 900000
  let chain2 = Blockchain "Ethereum" 950000

  putStrLn $ "Comparing chains: " ++ show (compareWith chain1 chain2)
```

---

### 🧪 Sample Output

```
Comparing chains: LT
```
