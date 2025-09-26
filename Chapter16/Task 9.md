HC16T9: Remove Duplicates from List

```haskell
-- Function to remove duplicates from a list
removeDuplicates :: Eq a => [a] -> [a]
removeDuplicates [] = []
removeDuplicates (x:xs)
  | x `elem` xs = removeDuplicates xs
  | otherwise   = x : removeDuplicates xs

-- Main function to demonstrate removeDuplicates
main :: IO ()
main = do
  putStrLn "Enter a list of items (comma separated):"
  input <- getLine
  let items = words $ map (\c -> if c == ',' then ' ' else c) input
  let result = removeDuplicates items
  putStrLn "List after removing duplicates:"
  print result
```

### Example:

#### Input:

```
Enter a list of items (comma separated):
apple,banana,apple,orange,banana
```

#### Output:

```
List after removing duplicates:
["orange","apple","banana"]
```
