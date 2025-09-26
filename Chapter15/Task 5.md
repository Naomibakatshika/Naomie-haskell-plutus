HC15T5: Safe Division Using Maybe

---

### ✅ Running code:

```haskell
safeDiv :: (Eq a, Fractional a) => a -> a -> Maybe a
safeDiv _ 0 = Nothing
safeDiv x y = Just (x / y)

-- Example usage
main :: IO ()
main = do
  print $ safeDiv 10 2    -- Just 5.0
  print $ safeDiv 5 0     -- Nothing
  print $ safeDiv 7.5 2.5 -- Just 3.0
```

---

### Explanation:

* Pattern matches on divisor `0` to return `Nothing`.
* Otherwise returns `Just` with the division result.
* `Fractional` constraint allows division on fractional types (`Float`, `Double`).
* `Eq` is needed to compare with zero
