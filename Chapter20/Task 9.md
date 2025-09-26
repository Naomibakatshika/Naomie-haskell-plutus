HC20T9: replicateMonad with Identity Monad

```haskell
import Control.Monad.Identity

-- replicateMonad replicates a value n times inside the Identity monad
replicateMonad :: Int -> a -> Identity [a]
replicateMonad n x = sequenceA (replicate n (pure x))

-- Or equivalently using replicateM:
-- replicateMonad n x = replicateM n (pure x)

-- Testing the function
main :: IO ()
main = do
  let result = runIdentity $ replicateMonad 5 "hello"
  print result
```

### Explanation:

* We use `replicate n (pure x)` to create a list of `n` actions inside the monad, each producing `x`.
* `sequenceA` (or `replicateM`) runs these actions and collects the results in the monadic context.
* `Identity` simply wraps the pure value, so running `runIdentity` extracts the list.

When you run this, you get:

```
["hello","hello","hello","hello","hello"]
```
