HC6T4: Product of Elements Using foldl

---

### ✅ Haskell Code: Product Using `foldl`

```haskell
-- Product function using foldl
productList :: [Int] -> Int
productList = foldl (*) 1

-- Main function to test productList
main :: IO ()
main = do
    print $ productList [1, 2, 3, 4, 5]  -- 120
    print $ productList []               -- 1
    print $ productList [10, 0, 7]      -- 0
```

---

### 🏃 How to Run:

1. Save as `ProductFoldl.hs`
2. Compile and run:

```bash
ghc ProductFoldl.hs -o productfoldl
./productfoldl
```

---

### 🧾 Expected Output:

```
120
1
0
```
