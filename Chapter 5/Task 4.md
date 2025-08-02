HC5T4: Using Lambda Functions

---

### ✅ Haskell Code: Lambda Version of `biggerThan10`

```haskell
-- Using a lambda function to define biggerThan10
biggerThan10 :: Int -> Bool
biggerThan10 = \x -> x > 10

-- Main function to test biggerThan10
main :: IO ()
main = do
    print $ biggerThan10 5    -- False
    print $ biggerThan10 10   -- False
    print $ biggerThan10 15   -- True
```

---

### 🏃 How to Run:

1. Save this as `BiggerThan10.hs`
2. Compile and run:

```bash
ghc BiggerThan10.hs -o bigger
./bigger
```

---

### 🧾 Expected Output:

```
False
False
True
```
