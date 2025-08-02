HC13T9: Renaming Module Namespace

---

### 🔧 Scenario

We have two modules:

* `MathAdd` with a function `add`
* `MathMultiply` with a function `add` (simulates conflict)

We'll **rename** these modules using `as` and call `add` from both.

---

### 1. `MathAdd.hs`

```haskell
module MathAdd (add) where

add :: Int -> Int -> Int
add x y = x + y
```

---

### 2. `MathMultiply.hs`

```haskell
module MathMultiply (add) where

add :: Int -> Int -> Int
add x y = x * y
```

---

### 3. `Main.hs`

```haskell
import qualified MathAdd as A
import qualified MathMultiply as M

main :: IO ()
main = do
    let x = 4
        y = 3
    putStrLn $ "Addition (A.add): " ++ show (A.add x y)
    putStrLn $ "Multiplication (M.add): " ++ show (M.add x y)
```

---

### ✅ How to Run

1. Save the files: `MathAdd.hs`, `MathMultiply.hs`, and `Main.hs`
2. Compile:

   ```bash
   ghc Main.hs
   ```
3. Run:

   ```bash
   ./Main
   ```

---

### 🧾 Output

```
Addition (A.add): 7
Multiplication (M.add): 12
```

---

### ✅ Summary

* `qualified` prevents name clashes.
* `as` renames the module for convenient access.
* You can now use both `add` functions from different contexts without conflict.
