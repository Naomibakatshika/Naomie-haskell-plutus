HC20T3: Writer Monad Logging Calculator

```haskell
import Control.Monad.Writer

-- Define a type alias for the Writer monad with a list of strings as the log
type Logger = Writer [String]

-- Addition with logging
add :: Int -> Int -> Logger Int
add x y = writer (x + y, ["Added " ++ show x ++ " and " ++ show y])

-- Subtraction with logging
subtract' :: Int -> Int -> Logger Int
subtract' x y = writer (x - y, ["Subtracted " ++ show y ++ " from " ++ show x])

-- Multiplication with logging
multiply :: Int -> Int -> Logger Int
multiply x y = writer (x * y, ["Multiplied " ++ show x ++ " and " ++ show y])

-- Division with logging (integer division)
divide :: Int -> Int -> Logger (Maybe Int)
divide _ 0 = writer (Nothing, ["Attempted division by zero"])
divide x y = writer (Just (x `div` y), ["Divided " ++ show x ++ " by " ++ show y])

-- Example complex calculation using do-notation
calcExample :: Logger (Maybe Int)
calcExample = do
  a <- add 10 5
  b <- subtract' a 3
  c <- multiply b 4
  divide c 2

main :: IO ()
main = do
  let (result, log) = runWriter calcExample
  putStrLn "Calculation Log:"
  mapM_ putStrLn log
  putStrLn $ "Result: " ++ show result
```

---

### What this does

* Uses `Writer [String]` to accumulate logs of operations.
* Defines arithmetic functions (`add`, `subtract'`, `multiply`, `divide`) that produce logged results.
* Runs a sample calculation in `calcExample`.
* Prints the logs and the final result in `main`.

---

### Run it

Save to `LoggingCalculator.hs` and run with:

```bash
runhaskell LoggingCalculator.hs
```

---
