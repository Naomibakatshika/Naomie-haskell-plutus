HC16T1: Reverse a String

```haskell
-- Function to reverse a string
reverseString :: String -> String
reverseString = reverse

-- Main function to demonstrate usage
main :: IO ()
main = do
  putStrLn "Enter a string to reverse:"
  input <- getLine
  putStrLn $ "Reversed string: " ++ reverseString input
```
