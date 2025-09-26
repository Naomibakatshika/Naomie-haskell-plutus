HC18T8: identityLawCheck Function

```haskell
-- identityLawCheck takes a Functor value and returns True if fmap id == id
identityLawCheck :: (Functor f, Eq (f a)) => f a -> Bool
identityLawCheck x = fmap id x == x

-- Example usage with Maybe and list functors
main :: IO ()
main = do
  let maybeVal = Just 42
      listVal = [1, 2, 3]
      nothingVal = Nothing :: Maybe Int
  print $ identityLawCheck maybeVal    -- Should print True
  print $ identityLawCheck listVal     -- Should print True
  print $ identityLawCheck nothingVal  -- Should print True
```

---

### Explanation:

* The **identity law** for functors states that `fmap id == id`.
* The function `identityLawCheck` tests this by applying `fmap id` to the input and comparing it with the input itself.
* It requires `Eq (f a)` to compare equality.
* Examples test it on `Maybe` and list values.
