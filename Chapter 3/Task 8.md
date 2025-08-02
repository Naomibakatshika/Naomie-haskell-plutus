HC3T8 - Advanced Task 8: Calculate BMI and return category using where

* Defines the function `bmiCategory :: Float -> Float -> String`
* Uses a `where` clause to calculate BMI as `weight / height^2`
* Uses **guards** (`|`) to classify the BMI:

  * `< 18.5` → `"Underweight"`
  * `18.5 to 24.9` → `"Normal"`
  * `25 to 29.9` → `"Overweight"`
  * `≥ 30` → `"Obese"`
* Tests the function with:

  * `bmiCategory 70 1.75`
  * `bmiCategory 90 1.8`

---

### ✅ Full Haskell Code

```haskell
-- Function to classify BMI
bmiCategory :: Float -> Float -> String
bmiCategory weight height
    | bmi < 18.5 = "Underweight"
    | bmi < 25   = "Normal"
    | bmi < 30   = "Overweight"
    | otherwise  = "Obese"
    where
        bmi = weight / height ^ 2

-- Main function to test bmiCategory
main :: IO ()
main = do
    putStrLn $ "bmiCategory 70 1.75 = " ++ bmiCategory 70 1.75  -- Normal
    putStrLn $ "bmiCategory 90 1.8  = " ++ bmiCategory 90 1.8   -- Overweight
```

---

### 🏃 How to Run:

1. Save it as `BMICategory.hs`
2. Compile and run:

```bash
ghc BMICategory.hs -o bmi
./bmi
```

---

### 🧾 Expected Output:

```
bmiCategory 70 1.75 = Normal
bmiCategory 90 1.8  = Overweight
```

