HC9T2: Implement a Parametric Data Type

---

### ✅ Haskell Code

```haskell
-- Define the Box data type
data Box a = Empty | Has a
  deriving (Show)

-- Example usage
box1 :: Box Int
box1 = Empty

box2 :: Box String
box2 = Has "Hello, world!"

-- Main function to print example boxes
main :: IO ()
main = do
  print box1
  print box2
```

---

### 🧪 Sample Output

```
Empty
Has "Hello, world!"
```
