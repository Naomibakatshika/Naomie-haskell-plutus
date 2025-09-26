HC16T4: Filter Even Numbers

```haskell
-- Function to filter even numbers
filterEvens :: [Int] -> [Int]
filterEvens = filter even

-- Main function to demonstrate usage
main :: IO ()
main = do
  putStrLn "Enter a list of integers separated by spaces:"
  input <- getLine
  let numbers = map read (words input) :: [Int]
  let evens = filterEvens numbers
  putStrLn "Even numbers:"
  print evens
```

### Example:

**Input:**

```
Enter a list of integers separated by spaces:
1 2 3 4 5 6 7
```

**Output:**

```
Even numbers:
[2,4,6]
```
