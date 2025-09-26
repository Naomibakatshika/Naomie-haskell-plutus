HC16T2: Palindrome Checker

```haskell
-- Function to check if a string is a palindrome
isPalindrome :: String -> Bool
isPalindrome s = s == reverse s

-- Main function to demonstrate usage
main :: IO ()
main = do
  putStrLn "Enter a string to check for palindrome:"
  input <- getLine
  if isPalindrome input
    then putStrLn "It's a palindrome!"
    else putStrLn "Not a palindrome."
```
