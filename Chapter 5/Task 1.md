HC5T1: Using applyTwice

* a function `(Int -> Int)`
* an integer `Int`

and applies the function **three times** to that integer.

---

### ✅ Haskell Code: `applyThrice`

```haskell
-- Function that applies a given function three times to an integer
applyThrice :: (Int -> Int) -> Int -> Int
applyThrice f x = f (f (f x))

-- Example function to use: double the number
double :: Int -> Int
double x = x * 2

-- Main function to test applyThrice
main :: IO ()
main = do
    print $ applyThrice double 1      -- 1 → 2 → 4 → 8
    print $ applyThrice (+1) 5        -- 5 → 6 → 7 → 8
    print $ applyThrice (*3) 2        -- 2 → 6 → 18 → 54
```

---

### 🏃 How to Run:

1. Save the file as `ApplyThrice.hs`
2. Compile and run it:

```bash
ghc ApplyThrice.hs -o applythrice
./applythrice
```

---

### 🧾 Example Output:

```
8
8
54
