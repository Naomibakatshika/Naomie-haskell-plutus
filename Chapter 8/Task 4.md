HC8T4: Record Syntax for Employee
---

### ✅ Haskell Code

```haskell
-- Define the Employee type using record syntax
data Employee = Employee
  { name :: String
  , experienceInYears :: Float
  } deriving (Show)

-- Create an employee named Richard
richard :: Employee
richard = Employee { name = "Richard", experienceInYears = 7.5 }

-- Main function to print Richard's details
main :: IO ()
main = do
  putStrLn $ "Employee Name: " ++ name richard
  putStrLn $ "Experience: " ++ show (experienceInYears richard) ++ " years"
```

---

### 🧪 Output

```
Employee Name: Richard
Experience: 7.5 years
```
