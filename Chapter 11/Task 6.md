HC11T6: Uppercase Converter

---

### ✅ Haskell Code

```haskell
import Data.Char (toUpper)

main :: IO ()
main = do
  putStrLn "Enter a line:"
  line <- getLine
  let upperLine = map toUpper line
  putStrLn upperLine
```

---

### 💡 How It Works

* Imports `toUpper` from `Data.Char`.
* Reads a line with `getLine`.
* Converts each character to uppercase using `map toUpper`.
* Prints the resulting string.

---

### ▶ Example Run

```
Enter a line:
Hello, Haskell!
HELLO, HASKELL!
```
