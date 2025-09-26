HC15T4: Exception Handler for Traffic Light

---

### ✅ Full running code (`TrafficLightHandler.hs`)

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

-- Exception handler function
handler :: TrafficLightException -> IO ()
handler ex = putStrLn $ "Caught a traffic light exception: " ++ show ex

main :: IO ()
main = do
  putStrLn "Enter the traffic light color (Red, Yellow, Green):"
  input <- getLine
  parseLight input >>= \light -> putStrLn ("Traffic Light: " ++ show light) >> putStrLn ("AI Car Reaction: " ++ carReaction light)
    `catch` handler
```

---

### Explanation:

* The `handler` function handles `TrafficLightException` and prints a friendly message.
* The main action tries to parse and react to the traffic light, catching exceptions with `catch handler`.
* This is a clean way to separate normal logic and exception handling.

---

### Sample run:

```
Enter the traffic light color (Red, Yellow, Green):
purple
Caught a traffic light exception: InvalidTrafficLight "Invalid traffic light color: purple"
```

---
