HC13T5: Restrict Module Export List

```haskell
module SumNonEmpty (sumNonEmpty) where

-- Public function
sumNonEmpty :: Num a => [a] -> a
sumNonEmpty [] = emptyListError
sumNonEmpty xs = sum xs

-- Helper function (not exported)
emptyListError :: a
emptyListError = error "sumNonEmpty: empty list"
```

---

### Explanation:

* The module exports **only** `sumNonEmpty`.
* `emptyListError` is a helper function that produces the error and is **kept private** inside the module.
* This helps keep the API clean and hides internal details.

---

### To test it, use a separate file like:

```haskell
import SumNonEmpty (sumNonEmpty)

main :: IO ()
main = do
    print $ sumNonEmpty [5, 6, 7]  -- prints 18
    print $ sumNonEmpty []          -- errors with message "sumNonEmpty: empty list"
```

Compile and run as usual:

```bash
ghc Main.hs
./Main
```
