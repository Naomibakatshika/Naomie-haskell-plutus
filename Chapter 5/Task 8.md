HC5T8: Point-Free Style

---

### ✅ Haskell Code: Point-Free `addFive`

```haskell
-- Point-free style version of addFive
addFive :: Int -> Int
addFive = (+ 5)

-- Main function to test addFive
main :: IO ()
main = do
    print $ addFive 3    -- 8
    print $ addFive 0    -- 5
    print $ addFive (-2) -- 3
```

---

### 🏃 How to Run:

1. Save this as `AddFivePointFree.hs`
2. Compile and run:

```bash
ghc AddFivePointFree.hs -o addfive
./addfive
```

---

### 🧾 Expected Output:

```
8
5
3
```

In point-free style, you define the function without explicitly mentioning its argument (`x`). The expression `(+ 5)` is itself a function that adds 5 to its input.
