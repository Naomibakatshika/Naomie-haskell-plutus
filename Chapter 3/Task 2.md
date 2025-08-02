HC3T2 - Task 2: Determine the grade based on a score using guards

* Defines the function `grade :: Int -> String` using **guards** (`|`) to classify scores into letter grades.
* Tests the function with `grade 95`, `grade 72`, and `grade 50`.

---

### ✅ Full Haskell Code

```haskell
-- Function to assign letter grades based on score
grade :: Int -> String
grade score
    | score >= 90 = "A"
    | score >= 80 = "B"
    | score >= 70 = "C"
    | score >= 60 = "D"
    | otherwise   = "F"

-- Main function to test grade
main :: IO ()
main = do
    putStrLn $ "grade 95 = " ++ grade 95
    putStrLn $ "grade 72 = " ++ grade 72
    putStrLn $ "grade 50 = " ++ grade 50
```

---

### 🏃 How to Run:

1. Save the file as `Grade.hs`
2. Compile and run:

```bash
ghc Grade.hs -o grade
./grade
```

---

### 🧾 Expected Output:

```
grade 95 = A
grade 72 = C
grade 50 = F
```
