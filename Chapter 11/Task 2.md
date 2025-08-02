HC11T2: Count Characters in a Line

---

### ✅ Haskell Code

```haskell
-- Program to count characters in a line of input

main :: IO ()
main = do
  putStrLn "Please enter a line of text:"
  line <- getLine
  let count = length line
  putStrLn $ "Number of characters: " ++ show count
```

---

### 💡 How It Works

* `getLine` reads a full line of user input.
* `length` calculates the number of characters in the input string.
* The result is printed using `putStrLn`.

---

### ▶ Example Run

```
Please enter a line of text:
Hello, Haskell!
Number of characters: 15
```
