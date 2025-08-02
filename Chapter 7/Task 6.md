HC7T6: Using Integral and Floating Type Classes

---

### ✅ Haskell Code: `circleCircumference`

```haskell
-- Define a generic function for calculating circumference
circleCircumference :: (Real a, Floating b) => a -> b
circleCircumference r = 2 * pi * realToFrac r

-- Main function to test with different numeric types
main :: IO ()
main = do
    print $ circleCircumference 7            -- Using Int
    print $ circleCircumference 7.5          -- Using Double
    print $ circleCircumference (10 :: Integer)
```

---

### 🏃 How to Run

1. Save the code as `CircleCircumference.hs`
2. Compile and run:

```bash
ghc CircleCircumference.hs -o circlecirc
./circlecirc
```

---

### 🧾 Expected Output

```
43.982297150257104
47.12388980384689
62.83185307179586
```
