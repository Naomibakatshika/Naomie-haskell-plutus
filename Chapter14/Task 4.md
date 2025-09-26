HC14T4: TypeApplications Extension

* Enables the `TypeApplications` extension.
* Uses `read @Int` to explicitly specify the type when converting a `String` to an `Int`.

---

### ✅ `Main.hs`

```haskell
{-# LANGUAGE TypeApplications #-}

module Main where

import Text.Read (readMaybe)

-- Function to convert a String to an Int using TypeApplications
stringToInt :: String -> Maybe Int
stringToInt str = readMaybe @Int str

main :: IO ()
main = do
    putStrLn "Enter a number:"
    input <- getLine
    case stringToInt input of
        Just n  -> putStrLn $ "You entered: " ++ show n
        Nothing -> putStrLn "Invalid input. Please enter a valid integer."
```

---

### 💡 Explanation:

* `{-# LANGUAGE TypeApplications #-}` enables type-level specification like `read @Int`.
* `readMaybe @Int` safely attempts to parse a string into an `Int`, returning `Nothing` on failure.

---

### ✅ To Compile and Run:

```bash
ghc Main.hs -o app
./app
```
