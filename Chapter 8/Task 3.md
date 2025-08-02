HC8T3: Algebraic Data Types and Functions

---

### ✅ Haskell Code

```haskell
-- Define the Shape type
data Shape = Circle Float | Rectangle Float Float
  deriving (Show)

-- Define the area function
area :: Shape -> Float
area (Circle r) = pi * r * r
area (Rectangle w h) = w * h

-- Main function to test area calculations
main :: IO ()
main = do
  let c = Circle 5
  let r = Rectangle 10 5
  putStrLn $ "Area of circle with radius 5: " ++ show (area c)
  putStrLn $ "Area of rectangle 10x5: " ++ show (area r)
```

---

### 🧪 Expected Output

```
Area of circle with radius 5: 78.53982
Area of rectangle 10x5: 50.0
```
