HC20T13: fibonacciMemo with State Monad

```haskell
{-# LANGUAGE TupleSections #-}

import Control.Monad.State
import qualified Data.Map as Map

-- Type alias for the memoization state
type Memo = Map.Map Int Integer

-- Memoized Fibonacci using the State monad
fibonacciMemo :: Int -> State Memo Integer
fibonacciMemo 0 = return 0
fibonacciMemo 1 = return 1
fibonacciMemo n = do
    memo <- get
    case Map.lookup n memo of
        Just val -> return val
        Nothing -> do
            fib1 <- fibonacciMemo (n - 1)
            fib2 <- fibonacciMemo (n - 2)
            let result = fib1 + fib2
            modify (Map.insert n result)
            return result

-- Run the memoized Fibonacci with initial empty state
runFibonacci :: Int -> Integer
runFibonacci n = evalState (fibonacciMemo n) Map.empty

-- Main function to test
main :: IO ()
main = do
    putStrLn "Enter the nth Fibonacci number to compute:"
    input <- getLine
    let n = read input :: Int
    let result = runFibonacci n
    putStrLn $ "Fibonacci number at position " ++ show n ++ " is: " ++ show result
```

### How it works:

* Uses `State Memo` to store already-computed Fibonacci values.
* Recursively computes values while memoizing the results to avoid redundant computation.
* The `main` function allows you to test it by entering a number in the terminal.
