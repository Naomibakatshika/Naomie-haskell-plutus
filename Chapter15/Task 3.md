HC15T3: Custom Exception for Traffic Light Errors

* Defines a custom exception type `TrafficLightException`.
* Throws this exception when an invalid traffic light color is given.
* Catches and handles the exception gracefully.

---

### ✅ Full running code (`TrafficLightException.hs`)

```haskell
{-# LANGUAGE DeriveDataTypeable #-}

import Control.Exception
import Data.Typeable
import Data.Char (toLower)

-- Define custom exception
data TrafficLightException = InvalidTrafficLight String
  deriving (Show, Typeable)

instance Exception TrafficLightException

data TrafficLight = Red | Yellow | Green deriving (Show, Eq)

-- Parse string to TrafficLight or throw exception if invalid
parseLight :: String -> IO TrafficLight
parseLight str = case map toLower str of
  "red"    -> return Red
  "yellow" -> return Yellow
  "green"  -> return Green
  invalid  -> throwIO (InvalidTrafficLight ("Invalid traffic light color: " ++ invalid))

carReaction :: TrafficLight -> String
carReaction Red    = "Stop the car!"
carReaction Yellow = "Get ready to move."
carReaction Green  = "Go ahead!"

main :: IO ()
main = do
  putStrLn "Enter the traffic light color (Red, Yellow, Green):"
  input <- getLine
  result <- try (parseLight input) :: IO (Either TrafficLightException TrafficLight)
  case result of
    Left ex -> putStrLn $ "Error: " ++ show ex
    Right light -> do
      putStrLn $ "Traffic Light: " ++ show light
      putStrLn $ "AI Car Reaction: " ++ carReaction light
```

---

### Explanation:

* The `TrafficLightException` type derives `Exception` and `Typeable` for exception support.
* `parseLight` throws `InvalidTrafficLight` exception if input is invalid.
* `main` uses `try` to catch exceptions and print error messages instead of crashing.

---

### Run example:

```
Enter the traffic light color (Red, Yellow, Green):
blue
Error: InvalidTrafficLight "Invalid traffic light color: blue"
```

---
