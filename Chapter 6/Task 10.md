HC6T10: Digits of a Number (Recursive)

---

### ✅ Haskell Code: Recursive Digit Extraction

```haskell
-- Function to extract digits of a number recursively
digits :: Int -> [Int]
digits n
    | n < 10    = [n]
    | otherwise = digits (n `div` 10) ++ [n `mod` 10]

-- Main function to test digits
main :: IO ()
main = do
    print $ digits 12345   -- [1,2,3,4,5]
    print $ digits 0       -- [0]
    print $ digits 987654  -- [9,8,7,6,5,4]
```

---

### 🏃 How to Run:

1. Save as `Digits.hs`
2. Compile and run:

```bash
ghc Digits.hs -o digits
./digits
```

---

### 🧾 Expected Output:

```
[1,2,3,4,5]
[0]
[9,8,7,6,5,4]
```
