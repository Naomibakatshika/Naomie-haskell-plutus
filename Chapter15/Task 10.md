HC15T10: Hybrid Error Handling with Either and IO

* **`Either`** for pure logic errors (like invalid inputs or division by zero).
* **`IO` exceptions** caught via `try` for handling file-related errors.

This program:

* Reads distance and time inputs from the user.
* Safely parses them using `Either`.
* Calculates velocity with detailed error messages.
* Then tries to write the result to a file, handling IO exceptions gracefully.

---

### ✅ Running code:

```haskell
import Text.Read (readMaybe)
import Control.Exception
import System.IO.Error (ioeGetErrorString)

-- Safe division using Either for error reporting
safeDiv :: Double -> Double -> Either String Double
safeDiv _ 0 = Left "Error: Division by zero."
safeDiv x y = Right (x / y)

-- Parse input using Either
parseInput :: String -> String -> Either String (Double, Double)
parseInput distStr timeStr = do
  dist <- maybeToEither "Invalid distance input." (readMaybe distStr)
  time <- maybeToEither "Invalid time input." (readMaybe timeStr)
  return (dist, time)

-- Helper: convert Maybe to Either with error message
maybeToEither :: e -> Maybe a -> Either e a
maybeToEither err Nothing  = Left err
maybeToEither _   (Just x) = Right x

-- Calculate velocity from strings using Either
calculateVelocity :: String -> String -> Either String Double
calculateVelocity distStr timeStr = do
  (dist, time) <- parseInput distStr timeStr
  safeDiv dist time

-- Write result to file, catching IO exceptions
writeResultToFile :: FilePath -> String -> IO ()
writeResultToFile path content = do
  result <- try (writeFile path content) :: IO (Either IOError ())
  case result of
    Left err -> putStrLn $ "Failed to write file: " ++ ioeGetErrorString err
    Right _  -> putStrLn $ "Result successfully written to " ++ path

main :: IO ()
main = do
  putStrLn "Enter distance (meters):"
  distInput <- getLine
  putStrLn "Enter time (seconds):"
  timeInput <- getLine

  case calculateVelocity distInput timeInput of
    Left err -> putStrLn err
    Right velocity -> do
      putStrLn $ "Calculated velocity: " ++ show velocity ++ " m/s"
      putStrLn "Enter filename to save the result:"
      filename <- getLine
      writeResultToFile filename ("Velocity: " ++ show velocity ++ " m/s")
```

---

### How it works:

* Uses `Either` to safely parse and calculate velocity with error messages.
* Uses `try` to catch any exceptions when writing to a file.
* Prints informative messages for both logic and IO errors.

---
