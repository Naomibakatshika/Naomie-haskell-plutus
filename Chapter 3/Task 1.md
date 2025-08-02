HC3T1 - Task 1: Check if a number is positive, negative, or zero

* Defines the function `checkNumber :: Int -> String` using an `if-then-else` expression.
* Returns `"Positive"`, `"Negative"`, or `"Zero"` based on the input.
* Tests it with `checkNumber 5`, `checkNumber (-3)`, and `checkNumber 0`.

---

### ✅ Full Haskell Code

```haskell
-- Function to check if a number is positive, negative, or zero
checkNumber :: Int -> String
checkNumber n =
    if n > 0 then "Positive"
    else if n < 0 then "Negative"
    else "Zero"

-- Main function to test checkNumber
main :: IO ()
main = do
    putStrLn $ "checkNumber 5 = " ++ checkNumber 5
    putStrLn $ "checkNumber (-3) = " ++ checkNumber (-3)
    putStrLn $ "checkNumber 0 = " ++ checkNumber 0
```

---

### 🏃 How to Run:

1. Save this code as `CheckNumber.hs`
2. Compile and run:

```bash
ghc CheckNumber.hs -o checknumber
./checknumber
```

---

### 🧾 Expected Output:

```
checkNumber 5 = Positive
checkNumber (-3) = Negative
checkNumber 0 = Zero
```

