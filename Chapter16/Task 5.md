HC16T5: Uppercase String

```haskell
import Data.Char (toUpper)

-- Function to convert a string to uppercase
toUpperCase :: String -> String
toUpperCase = map toUpper

-- Main function to demonstrate usage
main :: IO ()
main = do
  putStrLn "Enter a string:"
  input <- getLine
  let upper = toUpperCase input
  putStrLn "Uppercase version:"
  putStrLn upper
```

### How it works:

* `map toUpper` applies `toUpper` to each character in the string.
* The `main` function reads input from the user, converts it, and prints the result.
