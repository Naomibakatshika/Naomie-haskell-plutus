HC12T2: Add Two Numbers

```haskell
-- Define the function to add two numbers
addTwoNumbers :: Int -> Int -> Int
addTwoNumbers x y = x + y

-- Main function to call addTwoNumbers and print the result
main :: IO ()
main = do
    let result = addTwoNumbers 5 7  -- You can change 5 and 7 to any numbers
    putStrLn $ "The sum is: " ++ show result
```

### How to run:

1. Save this code in a file named `AddTwo.hs`.
2. Compile it using GHC:

   ```bash
   ghc AddTwo.hs
   ```
3. Run the output:

   ```bash
   ./AddTwo
   ```

It will output:

```
The sum is: 12
```
