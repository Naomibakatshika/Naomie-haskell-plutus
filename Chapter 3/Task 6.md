HC3T6 - Advanced Task 6: Check leap year using if-then-else

* Defines the function `isLeapYear :: Int -> Bool` using **`if-then-else`** logic.
* Implements the leap year rules:

  * Divisible by 400 → `True`
  * Divisible by 100 but **not** 400 → `False`
  * Divisible by 4 → `True`
  * Otherwise → `False`
* Tests the function with a few examples.

---

### ✅ Full Haskell Code

```haskell
-- Function to determine if a year is a leap year using if-then-else
isLeapYear :: Int -> Bool
isLeapYear year =
    if year `mod` 400 == 0 then True
    else if year `mod` 100 == 0 then False
    else if year `mod` 4 == 0 then True
    else False

-- Main function to test isLeapYear
main :: IO ()
main = do
    putStrLn $ "isLeapYear 2000 = " ++ show (isLeapYear 2000) -- True
    putStrLn $ "isLeapYear 1900 = " ++ show (isLeapYear 1900) -- False
    putStrLn $ "isLeapYear 2024 = " ++ show (isLeapYear 2024) -- True
    putStrLn $ "isLeapYear 2023 = " ++ show (isLeapYear 2023) -- False
```

---

### 🏃 How to Run:

1. Save the file as `LeapYear.hs`
2. Compile and run:

```bash
ghc LeapYear.hs -o leapyear
./leapyear
```

---

### 🧾 Expected Output:

```
isLeapYear 2000 = True
isLeapYear 1900 = False
isLeapYear 2024 = True
isLeapYear 2023 = False
```

