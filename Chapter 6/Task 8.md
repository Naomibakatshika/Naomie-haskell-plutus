HC6T8: Filter Even Numbers

---

### ✅ Haskell Code: Filter Even Numbers

```haskell
-- Function to filter even numbers from a list
filterEven :: [Int] -> [Int]
filterEven = filter even

-- Main function to test filterEven
main :: IO ()
main = do
    print $ filterEven [1, 2, 3, 4, 5, 6]  -- [2,4,6]
    print $ filterEven [7, 9, 11]           -- []
    print $ filterEven []                    -- []
```

---

### 🏃 How to Run:

1. Save as `FilterEven.hs`
2. Compile and run:

```bash
ghc FilterEven.hs -o filtereven
./filtereven
```

---

### 🧾 Expected Output:

```
[2,4,6]
[]
[]
```
