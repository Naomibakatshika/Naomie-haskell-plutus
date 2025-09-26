HC20T19: Writer Monad-based Logging System

---

### ✅ Full Haskell Code (Writer Logging System)

```haskell
{-# LANGUAGE GeneralizedNewtypeDeriving #-}

module Main where

import Control.Monad.Writer

-- | A custom type alias for the log
type Log = [String]

-- | A function that logs its call and argument, then returns the squared value
square :: Int -> Writer Log Int
square x = do
    tell ["square called with " ++ show x]
    return (x * x)

-- | A function that logs addition
add :: Int -> Int -> Writer Log Int
add x y = do
    tell ["add called with " ++ show x ++ " and " ++ show y]
    return (x + y)

-- | A function that chains calls and logs the full trace
compute :: Int -> Int -> Writer Log Int
compute x y = do
    sx <- square x
    sy <- square y
    add sx sy

-- | Entry point that runs the computation and prints the log
main :: IO ()
main = do
    let (result, logOutput) = runWriter (compute 3 4)
    putStrLn $ "Result: " ++ show result
    putStrLn "Log:"
    mapM_ putStrLn logOutput
```

---

### 🧪 Output Example

```bash
$ runhaskell Main.hs
Result: 25
Log:
square called with 3
square called with 4
add called with 9 and 16
```

---

### 🔍 Explanation

* `Writer Log a` is used to carry a list of log messages (`[String]`) alongside computations.
* `tell` appends log messages.
* `runWriter` returns both the result and the log.
* Functions like `square` and `add` are pure but produce logs describing their actions.

---
