HC6T1: Factorial (Recursive)

---

### ✅ Haskell Code: Recursive Factorial

```haskell
-- Recursive factorial function
factorial :: Integer -> Integer
factorial 0 = 1
factorial n
    | n > 0     = n * factorial (n - 1)
    | otherwise = error "Factorial is not defined for negative numbers"

-- Main function to test factorial
main :: IO ()
main = do
    print $ factorial 0    -- 1
    print $ factorial 5    -- 120
    print $ factorial 10   -- 3628800
```

---

### 🏃 How to Run:

1. Save as `Factorial.hs`
2. Compile and run:

```bash
ghc Factorial.hs -o factorial
./factorial
```

---

### 🧾 Expected Output:

```
1
120
3628800
```
