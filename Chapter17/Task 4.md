HC17T4: Monoid Instance for Sum Newtype

```haskell
import Data.Semigroup

-- Define Sum newtype
newtype Sum a = Sum { getSum :: a }
  deriving (Show, Eq)

-- Semigroup instance: sum two values
instance Num a => Semigroup (Sum a) where
  Sum x <> Sum y = Sum (x + y)

-- Monoid instance: identity is 0
instance Num a => Monoid (Sum a) where
  mempty = Sum 0

-- Example usage
main :: IO ()
main = do
  let values = [Sum 3, Sum 7, Sum 2]
      total = mconcat values
  putStrLn $ "Sum of values: " ++ show (getSum total)
```

---

### Explanation:

* `Semigroup` combines two `Sum` values by adding them.
* `Monoid` defines `mempty` as `Sum 0`, the additive identity.
* `mconcat` folds the list using the `Monoid` instance.

---

### Sample Output:

```
Sum of values: 12
```
