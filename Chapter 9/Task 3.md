HC9T3: Function to Add Values in a Box

---

### ✅ Haskell Code

```haskell
-- Define the Box data type
data Box a = Empty | Has a
  deriving (Show)

-- Function to add a number to the value inside the Box (if present)
addN :: Num a => a -> Box a -> Box a
addN _ Empty    = Empty
addN n (Has x)  = Has (n + x)

-- Example usage
box1 :: Box Int
box1 = Empty

box2 :: Box Int
box2 = Has 10

-- Main function to demonstrate addN
main :: IO ()
main = do
  print $ addN 5 box1     -- Should print: Empty
  print $ addN 5 box2     -- Should print: Has 15
```

---

### 🧪 Sample Output

```
Empty
Has 15
```
