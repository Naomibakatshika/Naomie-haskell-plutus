HC20T12: File Reading with IO Monad

```haskell
import System.IO

main :: IO ()
main = do
  putStrLn "Enter the file name:"
  fileName <- getLine
  contents <- readFile fileName
  putStrLn "File contents (line by line):"
  let linesOfFile = lines contents
  mapM_ putStrLn linesOfFile
```

### 🧠 How It Works:

* `getLine` reads the filename from user input.
* `readFile` reads the contents of the file as a single string.
* `lines` splits the contents into a list of lines.
* `mapM_ putStrLn` prints each line individually.

### ✅ To Run:

1. Save this code to a file, e.g. `ReadFileLines.hs`
2. Compile: `ghc ReadFileLines.hs`
3. Run: `./ReadFileLines`
4. Enter a file path like `example.txt`
