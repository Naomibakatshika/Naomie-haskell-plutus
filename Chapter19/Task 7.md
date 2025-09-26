HC19T7: conditionalPrint with when

```haskell
-- conditionalPrint.hs
import Control.Monad (when)

-- Define the conditionalPrint function
conditionalPrint :: Bool -> String -> IO ()
conditionalPrint condition message = when condition (putStrLn message)

-- Example usage in main
main :: IO ()
main = do
  putStrLn "Should we print the message? (yes/no)"
  input <- getLine
  let shouldPrint = input == "yes"
  conditionalPrint shouldPrint "This message is printed because the condition was True!"
```

### How it works:

* The `conditionalPrint` function uses `when` to run `putStrLn message` **only if** `condition` is `True`.
* In `main`, it asks the user for input to decide whether to print the message.

### How to Run:

Save this code to a file (e.g. `conditionalPrint.hs`) and run it using:

```bash
runhaskell conditionalPrint.hs
```
