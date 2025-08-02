HC10T4: Eq Instance for Box

1. Defines a **parameterized type** `Box a` with constructors `Empty` and `Has a`.
2. Makes `Box a` an **instance of `Eq`**, allowing equality comparison.

---

### ✅ Haskell Code

```haskell
-- Define the parameterized type Box
data Box a = Empty | Has a deriving (Show)

-- Make Box an instance of Eq
instance Eq a => Eq (Box a) where
  Empty   == Empty   = True
  Has x   == Has y   = x == y
  _       == _       = False

-- Example usage
main :: IO ()
main = do
  let box1 = Has 5
  let box2 = Has 5
  let box3 = Has 10
  let box4 = Empty

  print (box1 == box2) -- True
  print (box1 == box3) -- False
  print (box1 == box4) -- False
  print (box4 == Empty) -- True
```

---

### 🧪 Sample Output

```
True
False
False
True
```
