HC10T9: MinMax Type Class

---

### ✅ Haskell Code

```haskell
-- Define the MinMax type class
class MinMax a where
  minValue :: a
  maxValue :: a

-- Provide an instance for Int
instance MinMax Int where
  minValue = minBound
  maxValue = maxBound

-- Test function
main :: IO ()
main = do
  putStrLn $ "Min Int: " ++ show (minValue :: Int)
  putStrLn $ "Max Int: " ++ show (maxValue :: Int)
```

---

### 🧠 Explanation

* The `MinMax` type class defines two methods: `minValue` and `maxValue`.
* The `Int` instance uses Haskell’s built-in `minBound` and `maxBound` for `Int`.

---
