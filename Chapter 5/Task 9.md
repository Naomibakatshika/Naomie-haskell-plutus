HC5T9: Higher-Order Function to Transform a List

---

### ✅ Haskell Code: `transformList`

```haskell
-- Define transformList: applies a function twice to each element in a list
transformList :: (a -> a) -> [a] -> [a]
transformList f = map (f . f)

-- Example function to test with
square :: Int -> Int
square x = x * x

-- Main function to test transformList
main :: IO ()
main = do
    let numbers = [1, 2, 3, 4]
    putStrLn "Applying square twice to each element:"
    print $ transformList square numbers
    -- For example: square (square 2) = square 4 = 16
```

---

### 🏃 How to Run:

1. Save this as `TransformList.hs`
2. Compile and run:

```bash
ghc TransformList.hs -o transform
./transform
```

---

### 🧾 Expected Output:

```
Applying square twice to each element:
[1,16,81,256]
```

Because `square (square 2)` is `square 4 = 16`, and so on.
