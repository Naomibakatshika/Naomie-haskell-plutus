HC13T7: Use Custom Module in Main

---

### 1. Your existing `SumNonEmpty.hs` module (make sure it's in the same folder):

```haskell
module SumNonEmpty (sumNonEmpty) where

sumNonEmpty :: Num a => [a] -> a
sumNonEmpty [] = error "sumNonEmpty: empty list"
sumNonEmpty xs = sum xs
```

---

### 2. Create a `Main.hs` file to import and use `sumNonEmpty`:

```haskell
import SumNonEmpty (sumNonEmpty)

main :: IO ()
main = do
    let numbers = [10, 20, 30, 40]
    putStrLn $ "Sum of the list is: " ++ show (sumNonEmpty numbers)

    -- Uncomment the next line to test error on empty list
    -- print $ sumNonEmpty []
```

---

### How to compile and run:

```bash
ghc Main.hs
./Main
```

---

You should see:

```
Sum of the list is: 100
```

If you uncomment the empty list test, the program will crash with the error message `sumNonEmpty: empty list`.
