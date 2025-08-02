HC1T7 - Task 7: Converting Fahrenheit to Celsius

```haskell
-- Define a function to convert Fahrenheit to Celsius
fToC :: Floating a => a -> a
fToC f = (f - 32) * 5 / 9

-- Main function to test fToC
main :: IO ()
main = do
    let fahrenheit = 98.6
    putStrLn $ "Fahrenheit: " ++ show fahrenheit
    putStrLn $ "Celsius: " ++ show (fToC fahrenheit)
```

---

### Explanation:

* The formula used is:
  **Celsius = (Fahrenheit - 32) × 5⁄9**
* The function is **pure** and works with any `Floating` type (e.g., `Float`, `Double`).

---

### How to Run:

1. Save it as `FToC.hs`.
2. Compile and run:

```bash
ghc FToC.hs -o ftoc
./ftoc
```

---


