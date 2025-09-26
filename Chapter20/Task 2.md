HC20T2: sequenceMaybe for List of Maybe

```haskell
-- sequenceMaybe.hs

sequenceMaybe :: [Maybe a] -> Maybe [a]
sequenceMaybe [] = Just []
sequenceMaybe (x:xs) = case x of
  Nothing -> Nothing
  Just v  -> case sequenceMaybe xs of
               Nothing -> Nothing
               Just vs -> Just (v:vs)

-- Alternatively, using do-notation for clarity:
-- sequenceMaybe (x:xs) = do
--   v <- x
--   vs <- sequenceMaybe xs
--   return (v:vs)

main :: IO ()
main = do
  print $ sequenceMaybe [Just 1, Just 2, Just 3]    -- Should print: Just [1,2,3]
  print $ sequenceMaybe [Just 1, Nothing, Just 3] -- Should print: Nothing
  print $ sequenceMaybe []                         -- Should print: Just []
```

---

### How to run

Save as `sequenceMaybe.hs` and run:

```bash
runhaskell sequenceMaybe.hs
```

---
