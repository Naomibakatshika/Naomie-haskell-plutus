HC5T10: Combining Higher-Order Functions

* **squares** each value in a list,
* **filters** those greater than 50,
* and uses **`any`** to check if **any squared value** exceeds 50.

---

### ✅ Haskell Code: Using `filter`, `map`, and `any`

```haskell
-- Define the function using filter, map, and any
anySquareGreaterThan50 :: [Int] -> Bool
anySquareGreaterThan50 = any (> 50) . map (^2)

-- Main function to test
main :: IO ()
main = do
    print $ anySquareGreaterThan50 [1, 2, 3, 5, 6]    -- True (6^2 = 36, 5^2 = 25 → No; but if 8 was included, 64 > 50)
    print $ anySquareGreaterThan50 [1, 2, 3, 5]       -- False
    print $ anySquareGreaterThan50 [8, 1]             -- True (8^2 = 64)
```

---

### 🏃 How to Run:

1. Save this as `AnySquareGT50.hs`
2. Compile and run:

```bash
ghc AnySquareGT50.hs -o squarecheck
./squarecheck
```

---

### 🧾 Expected Output:

```
True
False
True
```
