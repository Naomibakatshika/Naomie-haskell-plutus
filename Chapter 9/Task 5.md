HC9T5: Parametric Data Type with Record Syntax

---

### ✅ Haskell Code

```haskell
-- Define the parametric Shape type
data Shape a
  = Circle { radius :: Float, color :: a }
  | Rectangle { width :: Float, height :: Float, color :: a }
  deriving (Show)

-- Example usage with String color
circle1 :: Shape String
circle1 = Circle { radius = 5.0, color = "Red" }

rectangle1 :: Shape String
rectangle1 = Rectangle { width = 10.0, height = 5.0, color = "Blue" }

-- Example usage with Int color code
circle2 :: Shape Int
circle2 = Circle { radius = 3.0, color = 123 }

-- Main function to print example shapes
main :: IO ()
main = do
  print circle1
  print rectangle1
  print circle2
```

---

### 🧪 Sample Output

```
Circle {radius = 5.0, color = "Red"}
Rectangle {width = 10.0, height = 5.0, color = "Blue"}
Circle {radius = 3.0, color = 123}
```
