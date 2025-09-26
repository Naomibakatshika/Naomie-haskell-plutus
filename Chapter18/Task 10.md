HC18T10: nestedFmap Function

```haskell
-- Define a function that applies a function to a nested functor structure
nestedFmap :: (Functor f, Functor g) => (a -> b) -> f (g a) -> f (g b)
nestedFmap = fmap . fmap

-- Example usage
main :: IO ()
main = do
  let nestedList = Just [1, 2, 3]         -- Maybe [Int]
      nestedMaybe = Just (Just 5)         -- Maybe (Maybe Int)
      nestedIO = return [1, 2, 3] :: IO [Int]  -- IO [Int]

  -- Applying (+1) to each Int inside nested functors
  print $ nestedFmap (+1) nestedList      -- Output: Just [2,3,4]
  print $ nestedFmap (*10) nestedMaybe    -- Output: Just (Just 50)
  result <- nestedFmap (*2) nestedIO      -- Output: [2,4,6]
  print result
```

---

### Explanation:

* `nestedFmap = fmap . fmap` composes two `fmap` calls.
* This is useful when you're working with **nested functor structures**, like:

  * `Maybe [a]` (a list inside a `Maybe`)
  * `IO [a]` (a list wrapped in `IO`)
  * `Maybe (Maybe a)` (nested optional values)

### Output:

```
Just [2,3,4]
Just (Just 50)
[2,4,6]
```
