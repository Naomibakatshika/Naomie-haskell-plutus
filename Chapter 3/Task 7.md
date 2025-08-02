HC3T7 - Advanced Task 7: Determine the season based on the month using guards

* Defines the function `season :: Int -> String` using **guards (`|`)**
* Maps each month number to a **season**:

  * `12, 1, 2` → `"Winter"`
  * `3, 4, 5` → `"Spring"`
  * `6, 7, 8` → `"Summer"`
  * `9, 10, 11` → `"Autumn"`
* Tests the function with `season 3`, `season 7`, and `season 11`.

---

### ✅ Full Haskell Code

```haskell
-- Function to return the season for a given month
season :: Int -> String
season month
    | month == 12 || month == 1 || month == 2 = "Winter"
    | month == 3  || month == 4 || month == 5 = "Spring"
    | month == 6  || month == 7 || month == 8 = "Summer"
    | month == 9  || month == 10 || month == 11 = "Autumn"
    | otherwise = "Invalid month"

-- Main function to test season
main :: IO ()
main = do
    putStrLn $ "season 3  = " ++ season 3    -- Spring
    putStrLn $ "season 7  = " ++ season 7    -- Summer
    putStrLn $ "season 11 = " ++ season 11   -- Autumn
```

---

### 🏃 How to Run:

1. Save this file as `Season.hs`
2. Compile and run:

```bash
ghc Season.hs -o season
./season
```

---

### 🧾 Expected Output:

```
season 3  = Spring
season 7  = Summer
season 11 = Autumn
```

