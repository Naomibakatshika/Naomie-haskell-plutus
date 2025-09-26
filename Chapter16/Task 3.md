HC16T3: Factorial

```haskell
-- Recursive factorial function
factorial :: Integer -> Integer
factorial 0 = 1
factorial n
  | n > 0     = n * factorial (n - 1)
  | otherwise = error "Factorial is not defined for negative numbers."

-- Main function to demonstrate usage
main :: IO ()
main = do
  putStrLn "Enter a non-negative integer to calculate its factorial:"
  input <- getLine
  let n = read input :: Integer
  print $ factorial n
```
