HC7T10: Function with Multiple Type Class Constraints

---

### ✅ Haskell Code: `DescribeAndCompare.hs`

```haskell
-- Define the Shape data type
data Shape = Circle Double | Rectangle Double Double
    deriving (Show, Eq)

-- Ord instance for Shape based on area
instance Ord Shape where
    compare (Circle r1) (Circle r2) = compare (pi * r1 * r1) (pi * r2 * r2)
    compare (Rectangle w1 h1) (Rectangle w2 h2) = compare (w1 * h1) (w2 * h2)
    compare (Circle r) (Rectangle w h) = compare (pi * r * r) (w * h)
    compare (Rectangle w h) (Circle r) = compare (w * h) (pi * r * r)

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

-- describeAndCompare function
describeAndCompare :: (Describable a, Ord a) => a -> a -> String
describeAndCompare x y = describe (max x y)

-- Main function for testing
main :: IO ()
main = do
    putStrLn $ describeAndCompare True False
    putStrLn $ describeAndCompare (Circle 3.0) (Rectangle 4.0 5.0)
    putStrLn $ describeAndCompare (Rectangle 2 2) (Circle 1)
```

---

### 💡 How It Works

* `Shape` is ordered by area using a custom `Ord` instance.
* `describeAndCompare` uses `max` to select the larger of the two and applies `describe`.

---

### 🧪 Sample Output

```
This is true.
A rectangle with width 4.0 and height 5.0
A rectangle with width 2.0 and height 2.0
```
