HC16T7: Element Existence in List

```haskell
-- Function to check if an element exists in a list
elementExists :: (Eq a) => a -> [a] -> Bool
elementExists _ [] = False
elementExists x (y:ys)
  | x == y    = True
  | otherwise = elementExists x ys

-- Main function to demonstrate usage
main :: IO ()
main = do
  putStrLn "Enter a list of integers (comma separated):"
  inputList <- getLine
  let nums = map read $ words $ map (\c -> if c == ',' then ' ' else c) inputList :: [Int]
  
  putStrLn "Enter the number to search for:"
  inputElem <- getLine
  let elemToFind = read inputElem :: Int

  if elementExists elemToFind nums
    then putStrLn "Element exists in the list."
    else putStrLn "Element not found in the list."
```

### How it works:

* The function `elementExists` uses recursion to traverse the list.
* It returns `True` as soon as it finds the element, or `False` if the list is exhausted.

### Example:

Input:

```
Enter a list of integers (comma separated):
1,2,3,4,5
Enter the number to search for:
3
```

Output:

```
Element exists in the list.
```
