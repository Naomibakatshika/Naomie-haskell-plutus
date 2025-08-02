HC1T5 - Task 5: Laziness in Haskell

* Defines `infiniteNumbers`, an infinite list of numbers starting from 1.
* Extracts the first `n` elements using the `take` function.

```haskell
-- Define an infinite list of numbers starting from 1
infiniteNumbers :: [Integer]
infiniteNumbers = [1..]

-- Function to get the first n numbers from the infinite list
firstN :: Int -> [Integer]
firstN n = take n infiniteNumbers

-- Main function to test
main :: IO ()
main = do
    let n = 10
    putStrLn $ "First " ++ show n ++ " numbers from the infinite list:"
    print (firstN n)
```

---

### Output (when run with `n = 10`):

```
First 10 numbers from the infinite list:
[1,2,3,4,5,6,7,8,9,10]
```

### How to Run:

1. Save the file as `InfiniteNumbers.hs`.
2. Compile and run with:

```bash
ghc InfiniteNumbers.hs -o infinite
./infinite
```


