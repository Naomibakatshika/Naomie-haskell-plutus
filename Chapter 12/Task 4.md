HC12T4: First 10 Fibonacci Numbers

```haskell
-- Recursive function to compute the nth Fibonacci number
fibonacci :: Int -> Int
fibonacci 0 = 0
fibonacci 1 = 1
fibonacci n = fibonacci (n - 1) + fibonacci (n - 2)

-- Main function to print the first 10 Fibonacci numbers
main :: IO ()
main = do
    putStrLn "First 10 Fibonacci numbers:"
    print [fibonacci n | n <- [0..9]]
```

### How it works:

* `fibonacci` recursively computes the nth Fibonacci number.
* The list comprehension `[fibonacci n | n <- [0..9]]` generates the first 10 numbers.
* `print` outputs the list to the terminal.

### Example Output:

```
First 10 Fibonacci numbers:
[0,1,1,2,3,5,8,13,21,34]
```
