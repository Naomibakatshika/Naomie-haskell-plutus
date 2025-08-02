HC1T1 - Task 1: Function Composition

```haskell
-- Define the double function
double :: Int -> Int
double x = x * 2

-- Define the increment function
increment :: Int -> Int
increment x = x + 1

-- Define doubleThenIncrement using function composition
doubleThenIncrement :: Int -> Int
doubleThenIncrement = increment . double

-- Main function to test
main :: IO ()
main = do
    let number = 5
    putStrLn $ "Original number: " ++ show number
    putStrLn $ "After double: " ++ show (double number)
    putStrLn $ "After increment: " ++ show (increment number)
    putStrLn $ "After doubleThenIncrement: " ++ show (doubleThenIncrement number)
```

### Explanation:

* `double x = x * 2` — multiplies the number by 2.
* `increment x = x + 1` — adds 1 to the number.
* `doubleThenIncrement = increment . double` — composes the two functions such that `double` is applied first, then `increment`.

### How to Run:

1. Save the code in a file, for example, `Main.hs`.
2. Compile and run it using GHC:

   ```bash
   ghc Main.hs -o main
   ./main
   ```


