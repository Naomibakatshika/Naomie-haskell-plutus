HC13T6: File Names to Map

```haskell
import System.Directory (listDirectory, doesFileExist)
import Data.List (isInfixOf)
import Control.Monad (filterM)
import qualified Data.Map as Map

-- Convert a list of file names into a Map with filename as key and length as value
filesToMap :: [FilePath] -> Map.Map FilePath Int
filesToMap files = Map.fromList [(f, length f) | f <- files]

-- Filter files containing a substring
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
    let fileMap = filesToMap filteredFiles
    putStrLn "File map (filename -> length):"
    mapM_ print (Map.toList fileMap)
```

---

### Explanation:

* `filesToMap` creates a map from filenames to their lengths.
* Files are filtered by the user-given substring.
* The map is printed as a list of key-value tuples.

---

### To run:

Save as `FilesMap.hs`, compile and run:

```bash
ghc FilesMap.hs
./FilesMap
```
