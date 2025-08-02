HC2T2 - Task 2: Function Type Signatures

* Provides **function signatures** for the following:

  * `add` – sums two `Int`s
  * `isEven` – checks if an `Int` is even
  * `concatStrings` – concatenates two `String` values
* Implements and tests these functions in the `main` block.

---

### ✅ Full Haskell Code

```haskell
-- Function that adds two Ints
add :: Int -> Int -> Int
add x y = x + y

-- Function that checks if an Int is even
isEven :: Int -> Bool
isEven x = x `mod` 2 == 0

-- Function that concatenates two strings
concatStrings :: String -> String -> String
concatStrings s1 s2 = s1 ++ s2

-- Main function to test all of the above
main :: IO ()
main = do
    -- Test add
    let a = 5
        b = 7
    putStrLn $ "add " ++ show a ++ " " ++ show b ++ " = " ++ show (add a b)

    -- Test isEven
    let n = 6
    putStrLn $ "isEven " ++ show n ++ " = " ++ show (isEven n)

    -- Test concatStrings
    let s1 = "Hello, "
        s2 = "Haskell!"
    putStrLn $ "concatStrings \"" ++ s1 ++ "\" \"" ++ s2 ++ "\" = " ++ concatStrings s1 s2
```

---

### 🏃 How to Run:

1. Save the file as `BasicFunctions.hs`
2. Compile and run it:

```bash
ghc BasicFunctions.hs -o basic
./basic
```

---

### 🔍 Output:

```
add 5 7 = 12
isEven 6 = True
concatStrings "Hello, " "Haskell!" = Hello, Haskell!
```
