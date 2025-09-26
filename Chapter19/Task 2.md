HC19T2: addThreeApplicative Function

```haskell
-- Define the function using Applicative style
addThreeApplicative :: Maybe Int -> Maybe Int -> Maybe Int -> Maybe Int
addThreeApplicative x y z = (\a b c -> a + b + c) <$> x <*> y <*> z

-- Example usage in main
main :: IO ()
main = do
  let a = Just 5
      b = Just 10
      c = Just 3
      result1 = addThreeApplicative a b c
      result2 = addThreeApplicative a Nothing c

  putStrLn $ "Result with all Just: " ++ show result1
  putStrLn $ "Result with one Nothing: " ++ show result2
```

### Output:

```
Result with all Just: Just 18
Result with one Nothing: Nothing
```

### Explanation:

* We use `<$>` and `<*>` from the `Applicative` instance of `Maybe`.
* If all inputs are `Just`, the sum is returned as `Just result`.
* If **any** input is `Nothing`, the whole result is `Nothing`.
