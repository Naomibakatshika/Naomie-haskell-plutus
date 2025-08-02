HC6T3: Sum of Elements Using foldr

---

### ✅ Haskell Code: Sum Using `foldr`

```haskell
-- Sum function using foldr
sumList :: [Int] -> Int
sumList = foldr (+) 0

-- Main function to test sumList
main :: IO ()
main = do
    print $ sumList [1, 2, 3, 4, 5]   -- 15
    print $ sumList []                -- 0
    print $ sumList [10, -5, 7]      -- 12
```

---

### 🏃 How to Run:

1. Save as `SumFoldr.hs`
2. Compile and run:

```bash
ghc SumFoldr.hs -o sumfoldr
./sumfoldr
```

---

### 🧾 Expected Output:

```
15
0
12
```
