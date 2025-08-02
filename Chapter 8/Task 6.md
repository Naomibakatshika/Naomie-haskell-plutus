HC8T6: Record Syntax for Shape Variants

---

### ✅ Haskell Code

```haskell
-- Define the Shape type using record syntax for each constructor
data Shape
  = Circle { center :: (Float, Float), radius :: Float, color :: String }
  | Rectangle { width :: Float, height :: Float, color :: String }
  deriving (Show)

-- Create a Circle instance
circle1 :: Shape
circle1 = Circle { center = (0.0, 0.0), radius = 5.0, color = "Red" }

-- Create a Rectangle instance
rectangle1 :: Shape
rectangle1 = Rectangle { width = 10.0, height = 5.0, color = "Blue" }

-- Main function to print the shapes
main :: IO ()
main = do
  putStrLn "Circle:"
  print circle1
  putStrLn "\nRectangle:"
  print rectangle1
```

---

### 🧪 Sample Output

```
Circle:
Circle {center = (0.0,0.0), radius = 5.0, color = "Red"}

Rectangle:
Rectangle {width = 10.0, height = 5.0, color = "Blue"}
```
