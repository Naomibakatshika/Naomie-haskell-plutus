HC13T1: List Files in Directory

---

### ✅ **Haskell Code: `ListFiles.hs`**

```haskell
import System.Directory (listDirectory, doesFileExist)
import System.FilePath ((</>))

main :: IO ()
main = do
    putStrLn "Listing all files in the current directory:\n"
    currentDir <- listDirectory "."
    filesOnly <- filterM doesFileExist currentDir
    mapM_ putStrLn filesOnly
```

---

### 🔧 How it Works:

* `listDirectory "."` lists all contents (files & folders) in the current directory.
* `doesFileExist` filters out only files (ignoring directories).
* `mapM_ putStrLn` prints each file name line-by-line.

---

### ▶️ **How to Run It**

1. Save the file as `ListFiles.hs`.
2. Open a terminal in the same directory.
3. Run:

   ```bash
   ghc ListFiles.hs -o listfiles
   ./listfiles         # or listfiles.exe on Windows
   ```

---
