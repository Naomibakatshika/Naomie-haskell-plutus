HC12T8: Merge Two Sorted Lists

```haskell
-- Function to merge two sorted lists
mergeLists :: Ord a => [a] -> [a] -> [a]
mergeLists [] ys = ys
mergeLists xs [] = xs
mergeLists (x:xs) (y:ys)
    | x < y     = x : mergeLists xs (y:ys)
    | otherwise = y : mergeLists (x:xs) ys

-- Main function to test mergeLists
main :: IO ()
main = do
    let list1 = [1, 3, 5, 7]
    let list2 = [2, 4, 6, 8]
    let merged = mergeLists list1 list2
    putStrLn "Merged sorted list:"
    print merged
```

### Output:

```
Merged sorted list:
[1,2,3,4,5,6,7,8]
```

### Explanation:

* `mergeLists` takes two sorted lists and merges them recursively:

  * It compares the heads of both lists and places the smaller one at the front of the result.
  * This continues until one of the lists is empty.
