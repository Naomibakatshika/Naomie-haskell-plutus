HC15T8: Division with Either for Detailed Errors

---

### ✅ Running code:

```haskell
safeDiv :: (Eq a, Fractional a, Show a) => a -> a -> Either String a
safeDiv _ 0 = Left "Error: Division by zero is not allowed."
safeDiv x y = Right (x / y)

-- Example usage in main
main :: IO ()
main = do
  putStrLn "Enter numerator:"
  numInput <- getLine
  putStrLn "Enter denominator:"
  denInput <- getLine
  case (readEither numInput, readEither denInput) of
    (Right num, Right den) ->
      case safeDiv num den of
        Left err -> putStrLn err
        Right result -> putStrLn $ "Result: " ++ show result
    (Left err, _) -> putStrLn $ "Invalid numerator: " ++ err
    (_, Left err) -> putStrLn $ "Invalid denominator: " ++ err

-- Helper function using readEither from Text.Read
readEither :: Read a => String -> Either String a
readEither s = case reads s of
  [(val, "")] -> Right val
  _           -> Left "Not a valid number."
```

---

### Explanation:

* `safeDiv` returns `Left` with error message if dividing by zero.
* `readEither` safely parses strings to values or returns an error message.
* `main` reads input, parses safely, and performs division with detailed error feedback.

---
