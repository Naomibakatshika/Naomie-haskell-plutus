HC7T7: Bounded and Enum

---

### ✅ Haskell Code: `nextColor.hs`

```haskell
-- Define the Color data type
data Color = Red | Green | Blue deriving (Show, Eq)

-- Define the nextColor function that wraps around
nextColor :: Color -> Color
nextColor Red   = Green
nextColor Green = Blue
nextColor Blue  = Red

-- Main function to test nextColor
main :: IO ()
main = do
    print $ nextColor Red    -- Output: Green
    print $ nextColor Green  -- Output: Blue
    print $ nextColor Blue   -- Output: Red
```

---

### 🏃 How to Run

1. Save the file as `nextColor.hs`.
2. Compile and run:

```bash
ghc nextColor.hs -o nextcolor
./nextcolor
```

---

### 🧾 Expected Output

```
Green
Blue
Red
```
