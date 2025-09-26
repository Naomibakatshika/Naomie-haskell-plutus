HC17T5: combineLists Function

```haskell
import Data.Semigroup

-- combineLists concatenates two lists using Semigroup (<>)
combineLists :: [Int] -> [Int] -> [Int]
combineLists xs ys = xs <> ys

-- Example usage
main :: IO ()
main = do
  let list1 = [1, 2, 3]
      list2 = [4, 5, 6]
      combined = combineLists list1 list2
  putStrLn $ "Combined list: " ++ show combined
```

---

### Explanation:

* Lists in Haskell already have a `Semigroup` instance where `<>` is list concatenation.
* `combineLists` just applies `<>` to the two lists.

---

### Sample Output:

```
Combined list: [1,2,3,4,5,6]
```
