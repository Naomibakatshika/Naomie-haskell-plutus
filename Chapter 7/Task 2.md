HC7T2: Implement an Ord Instance for a Custom Data Type

```
Red   < Green < Blue
```

---

### ✅ Haskell Code: `Color` with `Ord` and `Eq`

```haskell
-- Define the Color data type
data Color = Red | Green | Blue

-- Implement Eq type class for equality
instance Eq Color where
    Red   == Red   = True
    Green == Green = True
    Blue  == Blue  = True
    _     == _     = False

-- Implement Ord type class for ordering
instance Ord Color where
    compare Red   Red   = EQ
    compare Red   _     = LT
    compare Green Red   = GT
    compare Green Green = EQ
    compare Green Blue  = LT
    compare Blue  Blue  = EQ
    compare Blue  _     = GT

-- Optional: implement Show for easier printing
instance Show Color where
    show Red   = "Red"
    show Green = "Green"
    show Blue  = "Blue"

-- Main function to test ordering
main :: IO ()
main = do
    print (Red < Green)     -- True
    print (Green < Blue)    -- True
    print (Blue > Red)      -- True
    print (Red > Blue)      -- False
    print (compare Green Red)  -- GT
```

---

### 🏃 How to Run

1. Save the code to a file called `ColorOrd.hs`
2. Compile and run:

```bash
ghc ColorOrd.hs -o colorord
./colorord
```

---

### 🧾 Expected Output

```
True
True
True
False
GT
```
