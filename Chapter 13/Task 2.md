HC13T2: Filter Files by Substring

```haskell
import System.Directory (listDirectory, doesFileExist)
import Data.List (isInfixOf)
import Control.Monad (filterM)

-- Filter files containing the substring
filterFilesBySubstring :: String -> IO [FilePath]
filterFilesBySubstring substr = do
    allEntries <- listDirectory "."
    files <- filterM doesFileExist allEntries
    return $ filter (isInfixOf substr) files

main :: IO ()
main = do
    putStrLn "Enter substring to filter files:"
    substr <- getLine
    filteredFiles <- filterFilesBySubstring substr
    putStrLn "Files containing the substring:"
    mapM_ putStrLn filteredFiles
```

---

### How it works:

* Lists all entries in the current directory.
* Filters to keep only files.
* Filters filenames to those containing the user-provided substring.
* Prints the matching filenames.

---

### To run:

Save as `FilterFiles.hs`, compile with `ghc FilterFiles.hs`, then run `./FilterFiles`.
