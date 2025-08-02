HC3T9 - Advanced Task 9: Find the maximum of three numbers using let

* Defines the function `maxOfThree :: Int -> Int -> Int -> Int`
* Uses a `let` binding to store intermediate maximum values
* Returns the maximum of three integers
* Tests with `maxOfThree 10 20 15` and `maxOfThree 5 25 10`

---

### ✅ Full Haskell Code

```haskell
-- Function to find the maximum of three integers using let
maxOfThree :: Int -> Int -> Int -> Int
maxOfThree x y z =
    let maxXY = max x y
        maxXYZ = max maxXY z
    in maxXYZ

-- Main function to test maxOfThree
main :: IO ()
main = do
    putStrLn $ "maxOfThree 10 20 15 = " ++ show (maxOfThree 10 20 15)  -- 20
    putStrLn $ "maxOfThree 5 25 10  = " ++ show (maxOfThree 5 25 10)   -- 25
```

---

### 🏃 How to Run:

1. Save the file as `MaxOfThree.hs`
2. Compile and run:

```bash
ghc MaxOfThree.hs -o maxthree
./maxthree
```

---

### 🧾 Expected Output:

```
maxOfThree 10 20 15 = 20
maxOfThree 5 25 10  = 25
```

