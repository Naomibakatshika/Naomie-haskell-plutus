HC15T1: Handle Exceptions for File Reading and Velocity Calculation

* Reads a file (e.g., containing distance as a number).
* Asks the user for a time input.
* Calculates velocity = distance / time.
* Handles exceptions gracefully (file errors, invalid input, division by zero).

---

### ✅ Full running code (`VelocityCalc.hs`)

```haskell
import Control.Exception (catch, IOException)
import System.IO.Error (isDoesNotExistError)
import Text.Read (readMaybe)

main :: IO ()
main = do
  putStrLn "Enter the filename containing the distance:"
  filename <- getLine
  distanceResult <- safeReadFile filename

  case distanceResult of
    Left err -> putStrLn $ "Error reading file: " ++ err
    Right distStr ->
      case readMaybe distStr :: Maybe Double of
        Nothing -> putStrLn "File does not contain a valid number."
        Just distance -> do
          putStrLn "Enter time (in seconds):"
          timeInput <- getLine
          case readMaybe timeInput :: Maybe Double of
            Nothing -> putStrLn "Invalid time input."
            Just time ->
              if time == 0
                then putStrLn "Time cannot be zero (division by zero)."
                else do
                  let velocity = distance / time
                  putStrLn $ "Velocity = " ++ show velocity ++ " units/sec"

-- Safe file read with exception handling
safeReadFile :: FilePath -> IO (Either String String)
safeReadFile path =
  catch
    (Right <$> readFile path)
    handler
  where
    handler e
      | isDoesNotExistError e = return $ Left "File does not exist."
      | otherwise = return $ Left $ "Some other IO error: " ++ show e
```

---

### How to run

1. Create a text file, e.g., `distance.txt`, containing a single number (e.g., `100`).
2. Run the program and input the filename (`distance.txt`) and a time value.

---

### Sample session

```
Enter the filename containing the distance:
distance.txt
Enter time (in seconds):
10
Velocity = 10.0 units/sec
```

---
