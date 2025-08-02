HC6T6: Element Exists in List

---

### ✅ Haskell Code: `elementExists`

```haskell
-- Function to check if an element exists in a list
elementExists :: Eq a => a -> [a] -> Bool
elementExists _ [] = False
elementExists e (x:xs)
    | e == x    = True
    | otherwise = elementExists e xs

-- Main function to test elementExists
main :: IO ()
main = do
    print $ elementExists 3 [1, 2, 3, 4, 5]    -- True
    print $ elementExists 'a' "haskell"        -- False
    print $ elementExists "hi" ["hello", "hi", "hey"] -- True
    print $ elementExists 10 []                 -- False
```

---

### 🏃 How to Run:

1. Save as `ElementExists.hs`
2. Compile and run:

```bash
ghc ElementExists.hs -o elementexists
./elementexists
```

---

### 🧾 Expected Output:

```
True
False
True
False
```
