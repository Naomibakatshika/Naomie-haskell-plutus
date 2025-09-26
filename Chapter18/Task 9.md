HC18T9: compositionLawCheck Function

```haskell
-- The Functor composition law states:
-- fmap (f . g) == fmap f . fmap g

-- compositionLawCheck takes a Functor value and two functions,
-- and checks whether the composition law holds.
compositionLawCheck :: (Functor f, Eq (f c)) => (b -> c) -> (a -> b) -> f a -> Bool
compositionLawCheck f g x = fmap (f . g) x == (fmap f . fmap g) x

-- Example usage
main :: IO ()
main = do
  let maybeVal = Just 5
      listVal  = [1, 2, 3]
      f = (*2)
      g = (+3)

  print $ compositionLawCheck f g maybeVal   -- Should print True
  print $ compositionLawCheck f g listVal    -- Should print True
```

---

### Explanation:

* The **Functor composition law** ensures that applying `fmap` to a composed function (`f . g`) is the same as applying `fmap` twice (`fmap f . fmap g`).
* This function works for any functor `f` where `Eq` can be derived for the final result.
* The example uses `Maybe` and list functors to demonstrate it.
