HC6T2: Fibonacci (Recursive)

---

### ✅ Haskell Code: Recursive Fibonacci

```haskell
-- Recursive Fibonacci function
fibonacci :: Integer -> Integer
fibonacci 0 = 0
fibonacci 1 = 1
fibonacci n
    | n > 1     = fibonacci (n - 1) + fibonacci (n - 2)
    | otherwise = error "Fibonacci is not defined for negative numbers"

-- Main function to test fibonacci
main :: IO ()
main = do
    print $ fibonacci 0    -- 0
    print $ fibonacci 1    -- 1
    print $ fibonacci 5    -- 5
    print $ fibonacci 10   -- 55
```

---

### 🏃 How to Run:

1. Save as `Fibonacci.hs`
2. Compile and run:

```bash
ghc Fibonacci.hs -o fibonacci
./fibonacci
```

---

### 🧾 Expected Output:

```
0
1
5
55
```
