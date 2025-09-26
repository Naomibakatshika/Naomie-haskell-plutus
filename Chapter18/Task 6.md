HC18T6: applyToMaybe Function

```haskell
-- applyToMaybe applies a function to the value inside a Maybe using fmap
applyToMaybe :: (a -> b) -> Maybe a -> Maybe b
applyToMaybe = fmap

-- Example usage
main :: IO ()
main = do
  let maybeVal1 = Just 10
      maybeVal2 = Nothing
      result1 = applyToMaybe (*2) maybeVal1
      result2 = applyToMaybe (*2) maybeVal2
  putStrLn $ "Original: " ++ show maybeVal1 ++ ", after applyToMaybe (*2): " ++ show result1
  putStrLn $ "Original: " ++ show maybeVal2 ++ ", after applyToMaybe (*2): " ++ show result2
```

---

### Output:

```
Original: Just 10, after applyToMaybe (*2): Just 20
Original: Nothing, after applyToMaybe (*2): Nothing
```
