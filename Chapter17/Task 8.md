HC17T8: foldWithSemigroup Function

```haskell
import Data.Semigroup

-- foldWithSemigroup combines all elements of a non-empty list using (<>)
foldWithSemigroup :: Semigroup a => [a] -> a
foldWithSemigroup = foldr1 (<>)

-- Example usage with lists (which are Semigroups)
main :: IO ()
main = do
  let listOfLists = [[1,2], [3,4], [5]]
      combined = foldWithSemigroup listOfLists
  putStrLn $ "Combined list: " ++ show combined
```

---

### Notes:

* `foldr1` requires the list to be non-empty; otherwise, it will error.
* If you want to handle empty lists, you need a `Monoid` constraint instead and use `foldr mempty (<>)`.

---

### Example output:

```
Combined list: [1,2,3,4,5]
```
