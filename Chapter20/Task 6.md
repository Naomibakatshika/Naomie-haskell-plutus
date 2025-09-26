HC20T6: doubleMonad Combining Maybe and List

```haskell
import Control.Monad.Trans.Maybe
import Control.Monad.Trans.Class (lift)
import Control.Monad (guard)

-- Example function combining Maybe and List using MaybeT
doubleMonad :: [Maybe Int]
doubleMonad = runMaybeT $ do
  x <- lift [1, 2, 3]      -- lift list into MaybeT
  guard (x > 1)            -- guard works like a filter
  y <- MaybeT (Just x)     -- wrap x into MaybeT
  return y

main :: IO ()
main = print doubleMonad
```

### Explanation:

* `MaybeT` wraps a monad with `Maybe` effects, here `MaybeT []` is `Maybe` inside `List`.
* We `lift` the list into `MaybeT` to work with list values.
* `guard` filters values inside the monad.
* `MaybeT (Just x)` wraps the `Maybe` value inside the transformer.
* Running `doubleMonad` produces the list of `Maybe Int` results.

### Output when running `main`:

```haskell
[Just 2,Just 3]
```
