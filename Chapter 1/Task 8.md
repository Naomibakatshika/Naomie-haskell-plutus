HC1T8 - Task 8: Higher-Order Functions

```haskell
-- Define a function that applies another function twice
applyTwice :: (a -> a) -> a -> a
applyTwice f x = f (f x)

-- Example function to test (e.g., increment by 1)
increment :: Int -> Int
increment x = x + 1

-- Main function to test applyTwice
main :: IO ()
main = do
    let input = 3
    putStrLn $ "Original value: " ++ show input
    putStrLn $ "After applying increment twice: " ++ show (applyTwice increment input)
```

---

### Output:

If `input = 3`, you'll get:

```
Original value: 3
After applying increment twice: 5
```

---

### How to Run:

1. Save the file as `ApplyTwice.hs`.
2. Compile and run:

```bash
ghc ApplyTwice.hs -o applytwice
./applytwice
```


