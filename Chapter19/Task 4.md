HC19T4: liftAndMultiply with liftA2

```haskell
-- liftAndMultiply.hs
import Control.Applicative (liftA2)

-- Lifts a binary function (Int -> Int -> Int) into an applicative context
liftAndMultiply :: Applicative f => f Int -> f Int -> f Int
liftAndMultiply = liftA2 (*)

-- Main function to demonstrate usage
main :: IO ()
main = do
  let a = Just 3
  let b = Just 4
  let c = Nothing

  putStrLn $ "Just 3 * Just 4 = " ++ show (liftAndMultiply a b)     -- Just 12
  putStrLn $ "Just 3 * Nothing = " ++ show (liftAndMultiply a c)   -- Nothing
```

### Output:

```
Just 3 * Just 4 = Just 12
Just 3 * Nothing = Nothing
```

### Explanation:

* `liftA2 (*)` lifts the multiplication function into the context of `Maybe`.
* If either argument is `Nothing`, the result is `Nothing`.
