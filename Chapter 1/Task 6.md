HC1T6 - Task 6: Using Type Signatures

```haskell
-- Define a function that adds two integers
addNumbers :: Int -> Int -> Int
addNumbers x y = x + y

-- Main function to test addNumbers
main :: IO ()
main = do
    let a = 5
        b = 7
    putStrLn $ "First number: " ++ show a
    putStrLn $ "Second number: " ++ show b
    putStrLn $ "Sum: " ++ show (addNumbers a b)
```

---

### How to Run:

1. Save it as `AddNumbers.hs`.
2. Compile and run it using GHC:

```bash
ghc AddNumbers.hs -o add
./add
```

---


