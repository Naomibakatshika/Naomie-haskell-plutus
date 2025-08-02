HC12T10: Mathematical Operations Module

1. **Defines a module** called `MathOps` with some basic mathematical operations.
2. **Imports and uses** that module in the `Main` program to demonstrate functionality.

---

### 📁 File 1: `MathOps.hs` (The module)

```haskell
module MathOps (
    add,
    subtract',
    multiply,
    divide
) where

-- Addition
add :: Num a => a -> a -> a
add x y = x + y

-- Subtraction (rename to avoid clash with Prelude)
subtract' :: Num a => a -> a -> a
subtract' x y = x - y

-- Multiplication
multiply :: Num a => a -> a -> a
multiply x y = x * y

-- Division
divide :: Fractional a => a -> a -> a
divide x y = x / y
```

---

### 📁 File 2: `Main.hs` (Main program using the module)

```haskell
import MathOps

main :: IO ()
main = do
    let a = 20
    let b = 4

    putStrLn $ "Adding " ++ show a ++ " and " ++ show b ++ ": " ++ show (add a b)
    putStrLn $ "Subtracting " ++ show b ++ " from " ++ show a ++ ": " ++ show (subtract' a b)
    putStrLn $ "Multiplying " ++ show a ++ " and " ++ show b ++ ": " ++ show (multiply a b)
    putStrLn $ "Dividing " ++ show a ++ " by " ++ show b ++ ": " ++ show (divide a b)
```

---

### ✅ How to Compile and Run:

1. Save `MathOps.hs` and `Main.hs` in the same directory.
2. Open terminal in that directory.
3. Compile:

   ```bash
   ghc Main.hs
   ```
4. Run:

   ```bash
   ./Main      # or Main.exe on Windows
   ```

---
