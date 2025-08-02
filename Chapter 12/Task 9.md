HC12T9: Read and Print File Content

```haskell
import System.IO
import System.IO.Error (isDoesNotExistError)
import Control.Exception (catch, IOException)

-- Function to safely read and print a file's contents
readFileSafe :: FilePath -> IO ()
readFileSafe path = catch
    (do
        contents <- readFile path
        putStrLn "File contents:"
        putStrLn contents
    )
    handler
  where
    handler :: IOException -> IO ()
    handler e
        | isDoesNotExistError e = putStrLn "Error: File does not exist."
        | otherwise             = putStrLn $ "An error occurred: " ++ show e

-- Main function
main :: IO ()
main = do
    putStrLn "Enter the file path to read:"
    filePath <- getLine
    readFileSafe filePath
```

### How it works:

* Prompts the user to enter a file path.
* Attempts to read and print the file contents.
* If the file doesn't exist, it prints: `Error: File does not exist.`
* Handles other IO exceptions by printing the error message.

### To run:

1. Save it to a file like `ReadFile.hs`
2. Compile with `ghc ReadFile.hs`
3. Run with `./ReadFile` or `ReadFile.exe` on Windows.
