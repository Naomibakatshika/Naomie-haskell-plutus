HC7T8: Parse a Value from a String Using Read

---

### ✅ Haskell Code: `parseShape.hs`

```haskell
import Text.Read (readMaybe)

-- Define Shape data type
data Shape = Circle Double | Rectangle Double Double
    deriving (Show, Read)

-- Function to safely parse a Shape from String
parseShape :: String -> Maybe Shape
parseShape = readMaybe

-- Main function to test parseShape
main :: IO ()
main = do
    print $ parseShape "Circle 5.0"               -- Just (Circle 5.0)
    print $ parseShape "Rectangle 3.0 4.0"        -- Just (Rectangle 3.0 4.0)
    print $ parseShape "Triangle 3.0 4.0"         -- Nothing
    print $ parseShape "Rectangle three four"     -- Nothing
```

---

### 🏃 How to Run

1. Save as `parseShape.hs`
2. Compile and run:

```bash
ghc parseShape.hs -o parseshape
./parseshape
```

---

### ✅ Expected Output

```
Just (Circle 5.0)
Just (Rectangle 3.0 4.0)
Nothing
Nothing
```
