HC5T5: Partial Application

---

### ✅ Haskell Code: `multiplyByFive` (Partial Application)

```haskell
-- Define multiplyByFive using partial application
multiplyByFive :: Int -> Int
multiplyByFive = (5 *)

-- Main function to test multiplyByFive
main :: IO ()
main = do
    print $ multiplyByFive 2     -- 10
    print $ multiplyByFive 10    -- 50
    print $ multiplyByFive (-4)  -- -20
```

---

### 🏃 How to Run:

1. Save this code as `MultiplyByFive.hs`
2. Compile and run:

```bash
ghc MultiplyByFive.hs -o multiply
./multiply
```

---

### 🧾 Expected Output:

```
10
50
-20
```
