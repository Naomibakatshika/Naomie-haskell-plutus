HC11T10: Reverse User Input

---

### ✅ Haskell Code

```haskell
main :: IO ()
main = do
  putStrLn "Enter a string:"
  input <- getLine
  let reversed = reverse input
  putStrLn $ "Reversed string: " ++ reversed
```

---

### 💡 How It Works

* Reads a line of input using `getLine`.
* Uses the built-in `reverse` function to reverse the string.
* Prints the reversed string.

---

### ▶ Example Run

```
Enter a string:
Haskell
Reversed string: lleksaH
```
