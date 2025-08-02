HC12T5: Palindrome Checker

```haskell
-- Define the isPalindrome function
isPalindrome :: String -> Bool
isPalindrome str = cleaned == reverse cleaned
  where
    cleaned = map toLower (filter isAlphaNum str)

-- Required imports
import Data.Char (toLower, isAlphaNum)

-- Main function to get input and check for palindrome
main :: IO ()
main = do
    putStrLn "Enter a string to check if it's a palindrome:"
    input <- getLine
    if isPalindrome input
        then putStrLn "Yes, it's a palindrome!"
        else putStrLn "No, it's not a palindrome."
```

### How it works:

* `isPalindrome` cleans the input (removing non-alphanumeric characters and converting to lowercase) and compares it to its reverse.
* `main` reads input from the user and prints whether it is a palindrome.

### Example usage:

```
Enter a string to check if it's a palindrome:
Madam
Yes, it's a palindrome!
```
