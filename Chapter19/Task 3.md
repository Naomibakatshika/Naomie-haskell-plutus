HC19T3: safeProduct for Maybe Int

```haskell
-- safeProduct.hs
safeProduct :: [Maybe Int] -> Maybe Int
safeProduct = foldr (\mx acc -> (*) <$> mx <*> acc) (Just 1)

-- Alternatively using do-notation (more readable for some):
-- safeProduct [] = Just 1
-- safeProduct (x:xs) = do
--   v  <- x
--   vs <- safeProduct xs
--   return (v * vs)

-- Main function to demonstrate usage
main :: IO ()
main = do
  let list1 = [Just 2, Just 3, Just 4]
  let list2 = [Just 2, Nothing, Just 4]

  putStrLn $ "Product of list1: " ++ show (safeProduct list1)  -- Just 24
  putStrLn $ "Product of list2: " ++ show (safeProduct list2)  -- Nothing
```

### Output:

```
Product of list1: Just 24
Product of list2: Nothing
```

### Explanation:

* The function uses a fold to chain `Maybe Int` values using the Applicative style: `(*) <$> mx <*> acc`.
* If **any** element is `Nothing`, the whole result becomes `Nothing`.
