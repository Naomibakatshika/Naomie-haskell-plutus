HC19T6: repeatEffect with forever

```haskell
-- repeatEffect.hs
import Control.Monad (forever)

-- Define the repeatEffect function
repeatEffect :: IO () -> IO ()
repeatEffect action = forever action

-- Example usage in main
main :: IO ()
main = do
  putStrLn "This program will repeatedly ask for input. Press Ctrl+C to exit."
  repeatEffect $ do
    putStrLn "Enter something:"
    input <- getLine
    putStrLn $ "You entered: " ++ input
```

### How It Works:

* `forever action` runs the provided `IO ()` action infinitely.
* `repeatEffect` is a wrapper for this behavior.
* In `main`, the program repeatedly asks for input and echoes it back.

### To Run:

Save it as `repeatEffect.hs`, compile or run it using:

```bash
runhaskell repeatEffect.hs
```

It will continue until you terminate it with `Ctrl+C`.
