HC15T9: Try Function for File IO Exceptions

---

### ✅ Running code:

```haskell
import System.IO
import Control.Exception
import System.IO.Error (ioeGetErrorString)

main :: IO ()
main = do
  putStrLn "Enter filename to read:"
  filename <- getLine
  result <- try (readFile filename) :: IO (Either IOError String)
  case result of
    Left err -> putStrLn $ "Error reading file: " ++ ioeGetErrorString err
    Right content -> putStrLn $ "File contents:\n" ++ content
```

---

### Explanation:

* `try` runs `readFile filename` and catches `IOError` exceptions.
* Returns `Either IOError String`: `Left` on error, `Right` on success.
* On error, prints a user-friendly error message.
* On success, prints file content.

---
