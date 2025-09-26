HC19T8: discardSecond with <*

```haskell
-- discardSecond.hs
-- This program demonstrates sequencing effects and discarding the second result

-- Define discardSecond using the Applicative operator <*
discardSecond :: Applicative f => f a -> f b -> f a
discardSecond = (<*)

main :: IO ()
main = do
  putStrLn "Running discardSecond..."
  result <- discardSecond
              (putStrLn "First action (kept result)" >> return "Result A")
              (putStrLn "Second action (discarded result)" >> return "Result B")
  putStrLn ("Final result: " ++ result)
```

### Explanation:

* `<*` is from the `Applicative` type class and runs both actions, **discarding the result of the second**.
* `discardSecond` just wraps `<*`, showing how to reuse existing Applicative behavior.
* The program prints both actions, but only returns the result from the first one.

### Sample Output:

```
Running discardSecond...
First action (kept result)
Second action (discarded result)
Final result: Result A
```

### Run it with:

```bash
runhaskell discardSecond.hs
```
