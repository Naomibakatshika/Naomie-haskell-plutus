HC16T8: Insertion Sort

```haskell
-- Insertion sort implementation
insertionSort :: [Int] -> [Int]
insertionSort [] = []
insertionSort (x:xs) = insert x (insertionSort xs)
  where
    insert :: Int -> [Int] -> [Int]
    insert x [] = [x]
    insert x (y:ys)
      | x <= y    = x : y : ys
      | otherwise = y : insert x ys

-- Main function to demonstrate insertionSort
main :: IO ()
main = do
  putStrLn "Enter a list of integers (comma separated):"
  input <- getLine
  let nums = map read $ words $ map (\c -> if c == ',' then ' ' else c) input :: [Int]
  let sorted = insertionSort nums
  putStrLn "Sorted list:"
  print sorted
```

### How it works:

* `insertionSort` recursively processes the list.
* Each element is inserted into the correct position in the sorted part of the list using the helper function `insert`.

### Example Input:

```
Enter a list of integers (comma separated):
5,2,8,1,3
```

### Output:

```
Sorted list:
[1,2,3,5,8]
```
