HC7T1: Implement an Eq Instance for a Custom Data Type

---

### ✅ Haskell Code: `Color` with Manual `Eq` Implementation

```haskell
-- Define the Color data type
data Color = Red | Green | Blue

-- Implement the Eq type class for Color
instance Eq Color where
    Red   == Red   = True
    Green == Green = True
    Blue  == Blue  = True
    _     == _     = False

-- Show instance so we can print colors
instance Show Color where
    show Red   = "Red"
    show Green = "Green"
    show Blue  = "Blue"

-- Main function to test Color equality
main :: IO ()
main = do
    print (Red == Red)     -- True
    print (Green == Blue)  -- False
    print (Blue == Blue)   -- True
    print (Red == Green)   -- False
```

---

### 🏃 How to Run:

1. Save the file as `ColorEq.hs`
2. Compile and run:

```bash
ghc ColorEq.hs -o coloreq
./coloreq
```

---

### 🧾 Expected Output:

```
True
False
True
False
```
