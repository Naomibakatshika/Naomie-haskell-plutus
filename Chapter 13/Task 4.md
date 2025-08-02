HC13T4: SumNonEmpty Module

```haskell
module SumNonEmpty (sumNonEmpty) where

-- sumNonEmpty sums a list of numbers, errors if the list is empty
sumNonEmpty :: Num a => [a] -> a
sumNonEmpty [] = error "sumNonEmpty: empty list"
sumNonEmpty xs = sum xs
```

---

### How to use it:

Create a separate file (e.g., `Main.hs`) to test it:

```haskell
import SumNonEmpty (sumNonEmpty)

main :: IO ()
main = do
    print $ sumNonEmpty [1,2,3,4]  -- prints 10
    print $ sumNonEmpty []          -- errors with message "sumNonEmpty: empty list"
```

---

### Compile & run:

```bash
ghc Main.hs
./Main
```
