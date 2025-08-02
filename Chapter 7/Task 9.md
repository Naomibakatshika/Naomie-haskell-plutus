HC7T9: Type Class with Multiple Instances

---

### ✅ Haskell Code: `Describable.hs`

```haskell
-- Define the Shape data type
data Shape = Circle Double | Rectangle Double Double
    deriving (Show)

-- Define the Describable type class
class Describable a where
    describe :: a -> String

-- Instance for Bool
instance Describable Bool where
    describe True  = "This is true."
    describe False = "This is false."

-- Instance for Shape
instance Describable Shape where
    describe (Circle r) = "A circle with radius " ++ show r
    describe (Rectangle w h) = "A rectangle with width " ++ show w ++ " and height " ++ show h

-- Test the describe function
main :: IO ()
main = do
    putStrLn $ describe True
    putStrLn $ describe False
    putStrLn $ describe (Circle 5.0)
    putStrLn $ describe (Rectangle 3.0 4.0)
```

---

### 🏃 How to Run

1. Save as `Describable.hs`.
2. Compile and run:

```bash
ghc Describable.hs -o describable
./describable
```

---

### 🧾 Expected Output

```
This is true.
This is false.
A circle with radius 5.0
A rectangle with width 3.0 and height 4.0
```
