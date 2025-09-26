HC15T2: Self-Driving AI Car System

* Reads a traffic light color from user input.
* Reacts accordingly: Stop, Ready, Go, or Unknown.

---

### ✅ Full running code (`SelfDrivingCar.hs`)

```haskell
module Main where

import Data.Char (toLower)

-- Data type for traffic light colors
data TrafficLight = Red | Yellow | Green | Unknown deriving (Show, Eq)

-- Parse string to TrafficLight (case insensitive)
parseLight :: String -> TrafficLight
parseLight str = case map toLower str of
  "red"    -> Red
  "yellow" -> Yellow
  "green"  -> Green
  _        -> Unknown

-- Car reaction based on traffic light
carReaction :: TrafficLight -> String
carReaction Red     = "Stop the car!"
carReaction Yellow  = "Get ready to move."
carReaction Green   = "Go ahead!"
carReaction Unknown = "Unknown light! Proceed with caution."

main :: IO ()
main = do
  putStrLn "Enter the traffic light color (Red, Yellow, Green):"
  input <- getLine
  let light = parseLight input
  putStrLn $ "Traffic Light: " ++ show light
  putStrLn $ "AI Car Reaction: " ++ carReaction light
```

---

### How to run

```bash
runhaskell SelfDrivingCar.hs
```

---

### Sample interaction

```
Enter the traffic light color (Red, Yellow, Green):
Red
Traffic Light: Red
AI Car Reaction: Stop the car!
```

---
