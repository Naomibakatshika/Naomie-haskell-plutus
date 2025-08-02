HC10T8: AdvancedEq Subclass of Eq

---

### ✅ Haskell Code

```haskell
-- Define AdvancedEq as a subclass of Eq
class Eq a => AdvancedEq a where
  compareEquality :: a -> a -> Bool

-- Example data type
data Color = Red | Green | Blue deriving (Eq, Show)

-- Make Color an instance of AdvancedEq
instance AdvancedEq Color where
  compareEquality x y = x == y  -- uses Eq's (==) internally

-- Test function
main :: IO ()
main = do
  print (compareEquality Red Red)     -- True
  print (compareEquality Red Green)   -- False
```

---

### 🧠 Explanation

* `AdvancedEq` **inherits** from `Eq` using the `Eq a =>` constraint.
* The `compareEquality` function can provide enhanced or alternative equality checks.
* `Color` is given a default implementation that delegates to `(==)` from `Eq`.

---
