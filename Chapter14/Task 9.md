HC14T9: PartialTypeSignatures Extension

---

### ✅ Full running code (`Main.hs`)

```haskell
{-# LANGUAGE PartialTypeSignatures #-}

module Main where

-- Function with a partial type signature using a wildcard
-- The compiler infers the missing parts of the type
addOne :: _ -> _
addOne x = x + 1

main :: IO ()
main = do
    print (addOne 5)     -- prints 6
    print (addOne 3.14)  -- prints 4.14
```

---

### 🧠 Explanation:

* `{-# LANGUAGE PartialTypeSignatures #-}` enables partial type signatures with `_`.
* Here, `addOne :: _ -> _` means: the function takes an input of some numeric type and returns the same numeric type.
* The compiler infers the specific type constraints needed (`Num a => a -> a`).

---

### ▶️ Compile and run:

```bash
ghc Main.hs -o main
./main
```

---
