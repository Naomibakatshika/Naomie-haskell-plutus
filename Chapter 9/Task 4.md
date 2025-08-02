HC9T4: Extract a Value from a Box

---

### ✅ Haskell Code

```haskell
-- Define the Box data type
data Box a = Empty | Has a
  deriving (Show)

-- Function to extract value or return default if Empty
extract :: a -> Box a -> a
extract defaultVal Empty   = defaultVal
extract _          (Has x) = x

-- Example usage
box1 :: Box Int
box1 = Empty

box2 :: Box Int
box2 = Has 42

-- Main function to demonstrate extract
main :: IO ()
main = do
  print $ extract 100 box1  -- Should print: 100 (default)
  print $ extract 100 box2  -- Should print: 42 (inside box)
```

---

### 🧪 Sample Output

```
100
42
```
