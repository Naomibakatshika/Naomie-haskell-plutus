HC13T10: Multi-Module Main Function

1. List files in the current directory
2. Filter files based on a **user-provided substring**
3. Sort and display the matching results

---

### ✅ **Code: `Main.hs`**

```haskell
import System.Directory (listDirectory)
import Data.List (isInfixOf, sort)

main :: IO ()
main = do
    putStrLn "Enter a search term to filter files:"
    searchTerm <- getLine

    -- Get list of files in the current directory
    allFiles <- listDirectory "."

    -- Filter files that contain the search term
    let filteredFiles = filter (isInfixOf searchTerm) allFiles

    -- Sort the filtered list
    let sortedFiles = sort filteredFiles

    putStrLn "\nMatching files:"
    mapM_ putStrLn sortedFiles
```

---

### 🔧 How to Run

1. Save the file as `Main.hs`

2. In terminal, compile and run:

   ```bash
   ghc Main.hs
   ./Main
   ```

3. When prompted, enter a substring (e.g., `"txt"`) to see matching files.

---

### 📝 Example Output

```
Enter a search term to filter files:
txt

Matching files:
notes.txt
summary.txt
```

---
