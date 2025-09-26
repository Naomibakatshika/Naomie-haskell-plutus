HC18T5: Functor Instance for Either

```haskell
-- Define a simplified Either type for demonstration
data Either e a = Left e | Right a deriving (Show, Eq)

-- Functor instance for Either, fmap applies only to Right
instance Functor (Either e) where
  fmap _ (Left e)  = Left e
  fmap f (Right a) = Right (f a)

-- Example usage
main :: IO ()
main = do
  let val1 = Right 10 :: Either String Int
      val2 = Left "Error" :: Either String Int
      fmapResult1 = fmap (+5) val1
      fmapResult2 = fmap (+5) val2
  putStrLn $ "fmap on Right: " ++ show fmapResult1
  putStrLn $ "fmap on Left: " ++ show fmapResult2
```

---

### Output:

```
fmap on Right: Right 15
fmap on Left: Left "Error"
```

This defines the `Functor` instance so that `fmap` transforms the value inside `Right` but leaves `Left` unchanged.
