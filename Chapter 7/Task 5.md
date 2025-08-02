HC7T5: Function with Num Constraint

---

### ✅ Haskell Code: `squareArea`

```haskell
-- Define the squareArea function for any numeric type
squareArea :: Num a => a -> a
squareArea side = side * side

-- Main function to test squareArea
main :: IO ()
main = do
    print $ squareArea 4            -- Output: 16
    print $ squareArea 5.5          -- Output: 30.25
    print $ squareArea (3 :: Int)   -- Output: 9
```

---

### 🏃 How to Run

1. Save this code in a file named `SquareArea.hs`.
2. Compile and run it:

```bash
ghc SquareArea.hs -o squarearea
./squarearea
```

---

### 🧾 Expected Output

```
16
30.25
9
```
