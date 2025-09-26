HC15T6: Safe Input Parsing with readMaybe

---

### ✅ Running code:

```haskell
import Text.Read (readMaybe)

main :: IO ()
main = do
  putStrLn "Enter a number:"
  input <- getLine
  case readMaybe input :: Maybe Int of
    Just n  -> putStrLn $ "You entered: " ++ show n
    Nothing -> putStrLn "Invalid input! Please enter a valid number."
```

---

### Explanation:

* `readMaybe` tries to parse a `String` to the requested type (`Int` here).
* Returns `Just` parsed value or `Nothing` if parsing fails.
* Using `case` to handle both possibilities gracefully.

---
