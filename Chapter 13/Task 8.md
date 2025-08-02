HC13T8: Qualified Imports for Name Conflicts

---

### Example scenario:

* Module `MathOps1` and `MathOps2` both define a function called `add`.
* We import both qualified so we can use `MathOps1.add` and `MathOps2.add` to disambiguate.

---

### 1. `MathOps1.hs`

```haskell
module MathOps1 (add) where

add :: Int -> Int -> Int
add x y = x + y
```

---

### 2. `MathOps2.hs`

```haskell
module MathOps2 (add) where

add :: Int -> Int -> Int
add x y = x + y + 1  -- slightly different behavior to show distinction
```

---

### 3. `Main.hs` using qualified imports

```haskell
import qualified MathOps1
import qualified MathOps2

main :: IO ()
main = do
    let a = 5
        b = 10

    putStrLn $ "Using MathOps1.add: " ++ show (MathOps1.add a b)
    putStrLn $ "Using MathOps2.add: " ++ show (MathOps2.add a b)
```

---

### How to run:

1. Save the three files above.
2. Compile the main file:

   ```bash
   ghc Main.hs
   ```
3. Run:

   ```bash
   ./Main
   ```

---

### Expected output:

```
Using MathOps1.add: 15
Using MathOps2.add: 16
```

---

### Explanation:

* By using `import qualified`, you avoid name clashes.
* You prefix the function calls with the module name to specify which version to use.
