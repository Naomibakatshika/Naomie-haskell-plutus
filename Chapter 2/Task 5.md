HC2T5 - Task 5: Defining and Using Functions

1. Defines:

   * `circleArea :: Float -> Float` – calculates the area of a circle from the radius.
   * `maxOfThree :: Int -> Int -> Int -> Int` – returns the maximum of three integers.
2. Tests these functions with different inputs.

---

### ✅ Full Haskell Code

```haskell
-- Function to calculate the area of a circle
circleArea :: Float -> Float
circleArea r = pi * r * r

-- Function to find the maximum of three integers
maxOfThree :: Int -> Int -> Int -> Int
maxOfThree a b c = max a (max b c)

-- Main function to test both
main :: IO ()
main = do
    -- Test circleArea
    let radius1 = 3.0
        radius2 = 5.5
    putStrLn $ "circleArea " ++ show radius1 ++ " = " ++ show (circleArea radius1)
    putStrLn $ "circleArea " ++ show radius2 ++ " = " ++ show (circleArea radius2)

    -- Test maxOfThree
    let x = 12
        y = 7
        z = 20
        a = -5
        b = 0
        c = -2
    putStrLn $ "\nmaxOfThree " ++ show x ++ " " ++ show y ++ " " ++ show z ++ " = " ++ show (maxOfThree x y z)
    putStrLn $ "maxOfThree " ++ show a ++ " " ++ show b ++ " " ++ show c ++ " = " ++ show (maxOfThree a b c)
```

---

### 🏃 How to Run:

1. Save the code in a file named `CircleAndMax.hs`
2. Compile and run:

```bash
ghc CircleAndMax.hs -o circlemax
./circlemax
```

---

### 🧾 Sample Output:

```
circleArea 3.0 = 28.274334
circleArea 5.5 = 95.03318

maxOfThree 12 7 20 = 20
maxOfThree -5 0 -2 = 0
```

