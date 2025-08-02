HC4T2 - Task 2: Define a dayType Function

* Defines `dayType :: String -> String`
* Uses **pattern matching** to classify the input day as:

  * `"Saturday"` or `"Sunday"` → `"It's a weekend!"`
  * `"Monday"` through `"Friday"` → `"It's a weekday."`
  * Any other input → `"Invalid day"`
* Includes test cases in the `main` function.

---

### ✅ Full Haskell Code

```haskell
-- Function to determine if the day is a weekday or weekend
dayType :: String -> String
dayType "Saturday" = "It's a weekend!"
dayType "Sunday"   = "It's a weekend!"
dayType "Monday"   = "It's a weekday."
dayType "Tuesday"  = "It's a weekday."
dayType "Wednesday"= "It's a weekday."
dayType "Thursday" = "It's a weekday."
dayType "Friday"   = "It's a weekday."
dayType _          = "Invalid day"

-- Main function to test dayType
main :: IO ()
main = do
    putStrLn $ "dayType \"Monday\"   = " ++ dayType "Monday"
    putStrLn $ "dayType \"Saturday\" = " ++ dayType "Saturday"
    putStrLn $ "dayType \"Sunday\"   = " ++ dayType "Sunday"
    putStrLn $ "dayType \"Funday\"   = " ++ dayType "Funday"
```

---

### 🏃 How to Run:

1. Save the file as `DayType.hs`
2. Compile and run:

```bash
ghc DayType.hs -o daytype
./daytype
```

---

### 🧾 Expected Output:

```
dayType "Monday"   = It's a weekday.
dayType "Saturday" = It's a weekend!
dayType "Sunday"   = It's a weekend!
dayType "Funday"   = Invalid day
```

