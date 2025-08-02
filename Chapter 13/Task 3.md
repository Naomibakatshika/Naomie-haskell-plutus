HC13T3: Sort and Return Filtered Files

```haskell
import System.Directory (listDirectory, doesFileExist)
import Data.List (isInfixOf, sort)
import Control.Monad (filterM)

-- Filter and sort files containing the substring
filterAndSortFiles :: String -> IO [FilePath]
filterAndSortFiles substr = do
    allEntries <- listDirectory "."
    files <- filterM doesFileExist allEntries
    let filtered = filter (isInfixOf substr) files
    return (sort filtered)

main :: IO ()
main = do
    putStrLn "Enter substring to filter files:"
    substr <- getLine
    sortedFiles <- filterAndSortFiles substr
    putStrLn "Sorted filtered files:"
    mapM_ putStrLn sortedFiles
```

---

### How it works:

* Lists all directory entries.
* Filters to files only.
* Filters filenames by substring.
* Sorts the filtered list.
* Prints the sorted file names.

---

### To run:

Save as `FilterSortFiles.hs`, compile with `ghc FilterSortFiles.hs`, then run `./FilterSortFiles`.
