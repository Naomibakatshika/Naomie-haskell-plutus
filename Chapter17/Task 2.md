HC17T2: Min and Max Newtypes with Semigroup

```haskell
-- Enable necessary extensions for deriving
{-# LANGUAGE DeriveGeneric #-}

import GHC.Generics (Generic)
import Data.Semigroup

-- Define newtype Min
newtype Min a = Min { getMin :: a }
  deriving (Show, Eq, Ord, Generic)

-- Semigroup instance for Min: chooses the smaller value
instance Ord a => Semigroup (Min a) where
  Min x <> Min y = Min (min x y)

-- Optional Monoid instance
instance (Ord a, Bounded a) => Monoid (Min a) where
  mempty = Min maxBound

-- Define newtype Max
newtype Max a = Max { getMax :: a }
  deriving (Show, Eq, Ord, Generic)

-- Semigroup instance for Max: chooses the larger value
instance Ord a => Semigroup (Max a) where
  Max x <> Max y = Max (max x y)

-- Optional Monoid instance
instance (Ord a, Bounded a) => Monoid (Max a) where
  mempty = Max minBound

-- Demo usage
main :: IO ()
main = do
  let values = [5, 3, 8, 1, 9]
      minResult = foldr1 (<>) (map Min values)
      maxResult = foldr1 (<>) (map Max values)

  putStrLn $ "Min of values: " ++ show (getMin minResult)
  putStrLn $ "Max of values: " ++ show (getMax maxResult)
```

### 🔍 Explanation:

* `Min` wraps a value and chooses the smallest in a `Semigroup` operation using `min`.
* `Max` wraps a value and chooses the largest using `max`.
* The `Monoid` instances use `maxBound` and `minBound` respectively, which require `Bounded`.

### 💡 Sample Output:

```
Min of values: 1
Max of values: 9
```
