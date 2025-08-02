HC6T5: Reverse a List (Recursive)

---

### ✅ Haskell Code: Recursive List Reversal

```haskell
-- Recursive function to reverse a list
reverseList :: [a] -> [a]
reverseList []     = []
reverseList (x:xs) = reverseList xs ++ [x]

-- Main function to test reverseList
main :: IO ()
main = do
    print $ reverseList [1, 2, 3, 4, 5]       -- [5,4,3,2,1]
    print $ reverseList "haskell"             -- "lleksah"
    print $ reverseList ([] :: [Int])         -- []
```

---

### 🏃 How to Run:

1. Save as `ReverseList.hs`
2. Compile and run:

```bash
ghc ReverseList.hs -o reverselist
./reverselist
```

---

### 🧾 Expected Output:

```
[5,4,3,2,1]
"lleksah"
[]
```
