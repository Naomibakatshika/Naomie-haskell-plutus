HC15T7: Velocity Calculation with Optionals and Parsing Handling

* Reads distance and time from the user as strings.
* Uses `readMaybe` to safely parse inputs into `Double`.
* Uses `Maybe` to handle optional values (parsing may fail).
* Calculates velocity = distance / time if both inputs are valid and time is non-zero.
* Handles errors like invalid input or division by zero gracefully.

---

### ✅ Running code:

```haskell
import Text.Read (readMaybe)

-- Safe division returning Maybe Double
safeDiv :: Double -> Double -> Maybe Double
safeDiv _ 0 = Nothing
safeDiv x y = Just (x / y)

-- Calculate velocity safely from input strings
calculateVelocity :: String -> String -> Maybe Double
calculateVelocity distStr timeStr = do
  dist <- readMaybe distStr :: Maybe Double
  time <- readMaybe timeStr :: Maybe Double
  safeDiv dist time

main :: IO ()
main = do
  putStrLn "Enter distance (meters):"
  distInput <- getLine
  putStrLn "Enter time (seconds):"
  timeInput <- getLine
  case calculateVelocity distInput timeInput of
    Just v  -> putStrLn $ "Velocity: " ++ show v ++ " m/s"
    Nothing -> putStrLn "Error: Invalid input or division by zero."
```

---

### How it works:

* `calculateVelocity` uses the Maybe monad (`do` notation) to chain parsing and safe division.
* If any parsing fails or time is zero, result is `Nothing`.
* `main` prints velocity or error message accordingly.

---
