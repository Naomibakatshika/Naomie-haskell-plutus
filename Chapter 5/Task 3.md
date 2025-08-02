HC5T3: Checking for Uppercase Letters

---

### ✅ Haskell Code: `anyUppercaseStart`

```haskell
import Data.Char (isUpper)

-- Function to check if any word starts with an uppercase letter
anyUppercaseStart :: [String] -> Bool
anyUppercaseStart = any startsWithUpper
  where
    startsWithUpper []     = False
    startsWithUpper (c:_)  = isUpper c

-- Main function to test anyUppercaseStart
main :: IO ()
main = do
    print $ anyUppercaseStart ["hello", "world"]        -- False
    print $ anyUppercaseStart ["hello", "World"]        -- True
    print $ anyUppercaseStart ["Apple", "banana"]       -- True
    print $ anyUppercaseStart []                        -- False
```

---

### 🏃 How to Run:

1. Save as `AnyUppercase.hs`
2. Compile and run:

```bash
ghc AnyUppercase.hs -o anyupper
./anyupper
```

---

### 🧾 Example Output:

```
False
True
True
False
```
