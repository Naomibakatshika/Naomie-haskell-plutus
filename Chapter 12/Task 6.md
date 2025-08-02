HC12T6: Sort a List of Integers

```haskell
import Data.List (sort)

-- Main function to read input, process, and print sorted list
main :: IO ()
main = do
    putStrLn "Enter a list of integers separated by spaces:"
    input <- getLine
    let numbers = map read (words input) :: [Int]
    let sortedNumbers = sort numbers
    putStrLn "Sorted list in ascending order:"
    print sortedNumbers
```

### Example usage:

```
Enter a list of integers separated by spaces:
3 1 4 1 5 9 2
Sorted list in ascending order:
[1,1,2,3,4,5,9]
```

### Notes:

* The `words` function splits the input into a list of strings.
* `map read` converts each string to an integer.
* `sort` is imported from `Data.List` and sorts the list.
* `print` outputs the sorted list.
