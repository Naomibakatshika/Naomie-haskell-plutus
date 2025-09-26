HC20T17: validatePassword with Either Monad

---

### ✅ Full Haskell Code

```haskell
module Main where

import Data.Char (isDigit, isLower, isUpper)

-- | Validate a password using a series of checks.
--   Returns either a validation error or success.
validatePassword :: String -> Either String String
validatePassword pwd = do
    checkLength pwd
    checkUpperCase pwd
    checkLowerCase pwd
    checkDigit pwd
    return "Password is valid!"

-- | Check that password has at least 8 characters
checkLength :: String -> Either String ()
checkLength pwd
    | length pwd >= 8 = Right ()
    | otherwise       = Left "Password must be at least 8 characters long."

-- | Check that password has at least one uppercase letter
checkUpperCase :: String -> Either String ()
checkUpperCase pwd
    | any isUpper pwd = Right ()
    | otherwise       = Left "Password must contain at least one uppercase letter."

-- | Check that password has at least one lowercase letter
checkLowerCase :: String -> Either String ()
checkLowerCase pwd
    | any isLower pwd = Right ()
    | otherwise       = Left "Password must contain at least one lowercase letter."

-- | Check that password has at least one digit
checkDigit :: String -> Either String ()
checkDigit pwd
    | any isDigit pwd = Right ()
    | otherwise       = Left "Password must contain at least one digit."

-- | Main function to test the validator
main :: IO ()
main = do
    putStrLn "Enter a password to validate:"
    pwd <- getLine
    case validatePassword pwd of
        Right msg  -> putStrLn msg
        Left error -> putStrLn $ "Validation error: " ++ error
```

---

### 🔍 Example Output:

```
Enter a password to validate:
password
Validation error: Password must contain at least one uppercase letter.
```

```
Enter a password to validate:
Password1
Password is valid!
```

---
