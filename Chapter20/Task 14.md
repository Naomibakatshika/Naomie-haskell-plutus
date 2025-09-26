HC20T14: mapMFilter Monadic Map-Filter

```haskell
import Control.Monad (forM)
import Data.Maybe (catMaybes)

-- | mapMFilter applies a monadic function to a list, filtering out Nothing results
mapMFilter :: Monad m => (a -> m (Maybe b)) -> [a] -> m [b]
mapMFilter f xs = do
    results <- forM xs f
    return (catMaybes results)

-- Example monadic function: keeps even numbers and doubles them
keepEvenDouble :: Int -> IO (Maybe Int)
keepEvenDouble x =
    if even x
        then return (Just (x * 2))
        else return Nothing

-- Main function to demonstrate mapMFilter
main :: IO ()
main = do
    let numbers = [1..10]
    putStrLn "Doubling even numbers from 1 to 10:"
    filtered <- mapMFilter keepEvenDouble numbers
    print filtered
```

### Output when run:

```
Doubling even numbers from 1 to 10:
[4,8,12,16,20]
```

### Explanation:

* `mapMFilter` takes a function `f :: a -> m (Maybe b)` and a list `[a]`.
* It maps `f` over the list, collecting `Maybe b` values in a monadic context.
* It uses `catMaybes` to remove all `Nothing` results, returning a monadic `[b]`.
