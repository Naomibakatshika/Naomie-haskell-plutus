HC17T1: Severity Data Type and Semigroup Instance

```haskell
-- Enable necessary language features
{-# LANGUAGE DeriveGeneric #-}

import GHC.Generics (Generic)
import Data.Semigroup

-- Define Severity levels
data Severity = Low | Medium | High | Critical
  deriving (Show, Eq, Ord, Generic)

-- Semigroup instance: higher severity wins
instance Semigroup Severity where
  (<>) = max

-- Optional Monoid instance (if you want a neutral value)
instance Monoid Severity where
  mempty = Low

-- Demonstration in main
main :: IO ()
main = do
  let s1 = Medium
      s2 = High
      s3 = Low
      s4 = Critical

  putStrLn $ "Medium <> High = " ++ show (s1 <> s2)
  putStrLn $ "Low <> Medium = " ++ show (s3 <> s1)
  putStrLn $ "High <> Critical = " ++ show (s2 <> s4)
```

### 🔧 Explanation:

* `Severity` is ordered by `Ord`, so we can use `max` to determine the higher one.
* The `Semigroup` instance uses `(<>) = max` to ensure combining severities yields the more severe of the two.
* The `Monoid` instance defines `Low` as the neutral severity.

### 💡 Sample Output:

```
Medium <> High = High
Low <> Medium = Medium
High <> Critical = Critical
```
