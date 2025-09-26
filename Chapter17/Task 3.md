HC17T3: Monoid Instance for Severity

```haskell
-- Severity.hs
{-# LANGUAGE DeriveGeneric #-}

import GHC.Generics (Generic)
import Data.Semigroup
import Data.Monoid

-- Define the Severity data type
data Severity = Low | Medium | High | Critical
  deriving (Show, Eq, Ord, Generic)

-- Semigroup instance: keep the higher severity
instance Semigroup Severity where
  (<>) = max

-- Monoid instance: identity is Low
instance Monoid Severity where
  mempty = Low

-- Example usage
main :: IO ()
main = do
  let s1 = Medium
      s2 = High
      s3 = Low
      combined = s1 <> s2 <> s3 <> mempty
  putStrLn $ "Combined severity: " ++ show combined
```

---

### ✅ Explanation:

* `Severity` has an `Ord` instance derived automatically, so `max` can determine the highest severity.
* `Semigroup` uses `max` to combine severities.
* `Monoid` defines `Low` as the identity, meaning combining with `Low` doesn't change the severity.

---

### 💡 Sample Output:

```
Combined severity: High
```
