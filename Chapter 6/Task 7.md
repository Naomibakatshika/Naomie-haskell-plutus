HC6T7: List Length

---

### ✅ Haskell Code: Recursive Length Function

```haskell
-- Recursive function to calculate the length of a list
listLength :: [a] -> Int
listLength []     = 0
listLength (_:xs) = 1 + listLength xs

-- Main function to test listLength
main :: IO ()
main = do
    print $ listLength [1, 2, 3, 4, 5]  -- 5
    print $ listLength "haskell"         -- 7
    print $ listLength ([] :: [Int])     -- 0
```

---

### 🏃 How to Run:

1. Save as `ListLength.hs`
2. Compile and run:

```bash
ghc ListLength.hs -o listlength
./listlength
```

---

### 🧾 Expected Output:

```
5
7
0
```
