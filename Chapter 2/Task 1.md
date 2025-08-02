HC2T1 - Task 1: Checking Types in GHCi

1. Shows the **expected types** of the given expressions as comments.
2. Prints out the values (for illustration).
3. Optionally, you can later open GHCi to verify the types using `:t <expression>`.

---

### ✅ Haskell Code with Comments on Expected Types

```haskell
-- Expected Types:
-- 42              :: Num a => a         (typically Int or Integer)
-- 3.14            :: Fractional a => a  (typically Double)
-- "Haskell"       :: [Char]             (String is just a type synonym for [Char])
-- 'Z'             :: Char
-- True && False   :: Bool

main :: IO ()
main = do
    putStrLn "Evaluating and displaying values with expected types:"
    
    -- Integer literal
    let intVal = 42
    putStrLn $ "42 (expected type: Num a => a): " ++ show intVal

    -- Floating-point literal
    let floatVal = 3.14
    putStrLn $ "3.14 (expected type: Fractional a => a): " ++ show floatVal

    -- String
    let strVal = "Haskell"
    putStrLn $ "\"Haskell\" (expected type: [Char]): " ++ strVal

    -- Character
    let charVal = 'Z'
    putStrLn $ "'Z' (expected type: Char): " ++ [charVal]

    -- Boolean expression
    let boolVal = True && False
    putStrLn $ "True && False (expected type: Bool): " ++ show boolVal
```

---

### 🧪 How to Check Types in GHCi

Once in GHCi, type the following to confirm the types:

```haskell
:t 42
:t 3.14
:t "Haskell"
:t 'Z'
:t True && False
```

---

### 🏃 How to Run This Program

1. Save it as `TypeCheck.hs`
2. Compile and run it:

```bash
ghc TypeCheck.hs -o typecheck
./typecheck

