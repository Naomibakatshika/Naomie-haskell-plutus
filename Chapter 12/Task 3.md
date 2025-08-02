HC12T3: Factorial Function

```haskell
-- Define the factorial function using recursion
factorial :: Integer -> Integer
factorial 0 = 1
factorial n
  | n > 0     = n * factorial (n - 1)
  | otherwise = error "Only positive integers allowed"

-- Main function to demonstrate factorial calculation
main :: IO ()
main = do
    putStrLn "Enter a positive integer:"
    input <- getLine
    let number = read input :: Integer
    if number < 0
        then putStrLn "Factorial is only defined for non-negative integers."
        else putStrLn $ "Factorial of " ++ show number ++ " is " ++ show (factorial number)
```

### How it works:

* Prompts the user for a positive integer.
* Reads and converts the input.
* Computes the factorial using recursion.
* Handles negative input with an appropriate message.

### Example Run:

```
Enter a positive integer:
5
Factorial of 5 is 120
```
