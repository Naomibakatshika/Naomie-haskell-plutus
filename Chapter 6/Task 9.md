HC6T9: Map Implementation

---

### ✅ Haskell Code: Custom `map` Function

```haskell
-- Recursive implementation of map
myMap :: (a -> b) -> [a] -> [b]
myMap _ []     = []
myMap f (x:xs) = f x : myMap f xs

-- Main function to test myMap
main :: IO ()
main = do
    print $ myMap (*2) [1, 2, 3, 4]        -- [2,4,6,8]
    print $ myMap length ["hi", "hello"]   -- [2,5]
    print $ myMap toUpper "haskell"        -- "HASKELL"
  where
    toUpper c = if c >= 'a' && c <= 'z'
                then toEnum (fromEnum c - 32)
                else c
```

---

### 🏃 How to Run:

1. Save the file as `MyMap.hs`
2. Compile and run:

```bash
ghc MyMap.hs -o mymap
./mymap
```

---

### 🧾 Expected Output:

```
[2,4,6,8]
[2,5]
"HASKELL"
```
