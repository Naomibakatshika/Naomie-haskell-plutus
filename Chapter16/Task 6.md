HC16T6: nth Fibonacci Number

```haskell
-- Recursive function to calculate the nth Fibonacci number
fibonacci :: Int -> Integer
fibonacci n
  | n < 0     = error "Negative index not allowed"
  | n == 0    = 0
  | n == 1    = 1
  | otherwise = fibonacci (n - 1) + fibonacci (n - 2)

-- Main function to demonstrate usage
main :: IO ()
main = do
  putStrLn "Enter the position n to find the nth Fibonacci number:"
  input <- getLine
  let n = read input :: Int
  print $ fibonacci n
```

### Example:

If the user inputs `10`, the program outputs `55`, which is the 10th Fibonacci number (indexing starts at 0).

### Notes:

* This version uses a **simple recursive implementation**, which is not optimized for large `n`.
* For better performance, you can use memoization or an iterative version. Let me know if you'd like that!
