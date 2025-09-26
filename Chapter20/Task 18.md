HC20T18: MaybeT Monad Transformer for User Input

---

### ✅ Full Haskell Code

```haskell
{-# LANGUAGE LambdaCase #-}

module Main where

import Control.Monad.Trans.Maybe
import Control.Monad.IO.Class
import Text.Read (readMaybe)

-- | Ask the user for their age and validate it using MaybeT IO
getValidAge :: MaybeT IO Int
getValidAge = do
    liftIO $ putStrLn "Enter your age:"
    input <- liftIO getLine
    age <- MaybeT . return $ readMaybe input        -- Parse string to Int
    if age > 0
        then return age
        else MaybeT $ return Nothing                -- Reject non-positive numbers

-- | Main function that runs the MaybeT computation
main :: IO ()
main = do
    result <- runMaybeT getValidAge
    case result of
        Just age  -> putStrLn $ "Your age is: " ++ show age
        Nothing   -> putStrLn "Invalid input. Please enter a positive number."
```

---

### 🧪 Example Usage

```bash
$ runhaskell Main.hs
Enter your age:
twenty
Invalid input. Please enter a positive number.

$ runhaskell Main.hs
Enter your age:
-5
Invalid input. Please enter a positive number.

$ runhaskell Main.hs
Enter your age:
25
Your age is: 25
```

---

### 🧠 Notes

* `MaybeT IO` lets us **gracefully handle failure** (invalid input) without crashing.
* `liftIO` is used to lift `IO` actions into the `MaybeT` context.
* `MaybeT . return $ readMaybe input` attempts to parse the string safely.
