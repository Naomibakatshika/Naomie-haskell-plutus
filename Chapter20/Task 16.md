HC20T16: retryIO with IO Monad

---

### ✅ Full Haskell Code:

```haskell
import Control.Exception (SomeException, try)
import Control.Monad (when)

-- | Retry an IO operation up to a given number of attempts
retryIO :: Int -> IO a -> IO (Maybe a)
retryIO 0 _ = return Nothing
retryIO attempts action = do
    result <- try action
    case result of
        Right val -> return (Just val)
        Left (_ :: SomeException) -> do
            putStrLn $ "Attempt failed. Remaining attempts: " ++ show (attempts - 1)
            retryIO (attempts - 1) action

-- | Example IO action that may fail randomly
import System.Random (randomRIO)
failingAction :: IO Int
failingAction = do
    n <- randomRIO (1, 10)
    putStrLn $ "Generated number: " ++ show n
    if n > 7
        then return n
        else error "Number too small, failing!"

main :: IO ()
main = do
    putStrLn "Trying to perform failingAction with retries..."
    result <- retryIO 5 failingAction
    case result of
        Just value -> putStrLn $ "Success! Got value: " ++ show value
        Nothing    -> putStrLn "All attempts failed."
```

---

### 🔧 How it works:

* `retryIO` takes an integer `attempts` and an IO action.
* It uses `try` to catch exceptions.
* If the action succeeds, it returns `Just a`.
* If it fails, it prints a message and retries, decrementing the attempt count.
* After all retries, it returns `Nothing`.

---

### 💡 Example Output (varies due to randomness):

```
Trying to perform failingAction with retries...
Generated number: 3
Attempt failed. Remaining attempts: 4
Generated number: 2
Attempt failed. Remaining attempts: 3
Generated number: 9
Success! Got value: 9
```

---
