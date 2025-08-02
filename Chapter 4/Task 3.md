HC4T3 - Task 3: Define a gradeComment Function

* Defines `gradeComment :: Int -> String`
* Uses **guards** to classify a grade and return an appropriate comment:

  * `90–100` → `"Excellent!"`
  * `70–89` → `"Good job!"`
  * `50–69` → `"You passed."`
  * `0–49` → `"Better luck next time."`
  * Any other number → `"Invalid grade"`
* Includes test cases in the `main` function.

---

### ✅ Full Haskell Code

```haskell
-- Function to return a comment based on a numerical grade
gradeComment :: Int -> String
gradeComment grade
    | grade >= 90 && grade <= 100 = "Excellent!"
    | grade >= 70 && grade <= 89  = "Good job!"
    | grade >= 50 && grade <= 69  = "You passed."
    | grade >= 0  && grade <= 49  = "Better luck next time."
    | otherwise                   = "Invalid grade"

-- Main function to test gradeComment
main :: IO ()
main = do
    putStrLn $ "gradeComment 95  = " ++ gradeComment 95
    putStrLn $ "gradeComment 75  = " ++ gradeComment 75
    putStrLn $ "gradeComment 55  = " ++ gradeComment 55
    putStrLn $ "gradeComment 30  = " ++ gradeComment 30
    putStrLn $ "gradeComment 105 = " ++ gradeComment 105
```

---

### 🏃 How to Run:

1. Save the file as `GradeComment.hs`
2. Compile and run:

```bash
ghc GradeComment.hs -o gradecomment
./gradecomment
```

---

### 🧾 Expected Output:

```
gradeComment 95  = Excellent!
gradeComment 75  = Good job!
gradeComment 55  = You passed.
gradeComment 30  = Better luck next time.
gradeComment 105 = Invalid grade
```

