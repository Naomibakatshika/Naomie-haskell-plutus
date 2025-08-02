HC4T8 - Task 8: Extract Values from Tuples

---

### ✅ Haskell Code: `describeTuple`

```haskell
-- Function to extract and describe values from a 2-tuple
describeTuple :: (Show a, Show b) => (a, b) -> String
describeTuple (x, y) = "The first value is " ++ show x ++ " and the second value is " ++ show y ++ "."

-- Main function to test describeTuple
main :: IO ()
main = do
    putStrLn $ describeTuple (42, "apples")
    putStrLn $ describeTuple ("hello", True)
    putStrLn $ describeTuple (3.14, 100)
```

---

### 🏃 How to Run:

1. Save the file as `DescribeTuple.hs`
2. Compile and run it:

```bash
ghc DescribeTuple.hs -o describe
./describe
```

---

### 🧾 Example Output:

```
The first value is 42 and the second value is "apples".
The first value is "hello" and the second value is True.
The first value is 3.14 and the second value is 100.
```

---
