HC19T5: applyEffects with <*>

```haskell
-- applyEffects.hs
main :: IO ()
main = do
  let action1 = do
        putStrLn "Enter first number:"
        readLn :: IO Int

  let action2 = do
        putStrLn "Enter second number:"
        readLn :: IO Int

  result <- applyEffects (action1, action2)
  putStrLn $ "Sum of the two numbers is: " ++ show result

-- Apply <*> to sum the results from two IO actions
applyEffects :: (IO Int, IO Int) -> IO Int
applyEffects (ioA, ioB) = (+) <$> ioA <*> ioB
```

### How It Works:

* The `applyEffects` function uses the Applicative `<*>` pattern to combine two `IO Int` actions and add their results.
* Each `IO Int` value is created by prompting the user for input using `readLn`.
* The sum is computed and printed afterward.

### Example Usage:

```
Enter first number:
5
Enter second number:
7
Sum of the two numbers is: 12
```
