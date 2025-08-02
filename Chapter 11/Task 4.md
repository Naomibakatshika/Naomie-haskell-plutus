HC11T4: Concatenate Two Lines

---

### ✅ Haskell Code

```haskell
-- Program to read two lines and print their concatenation

main :: IO ()
main = do
  putStrLn "Enter the first line:"
  line1 <- getLine
  putStrLn "Enter the second line:"
  line2 <- getLine
  let combined = line1 ++ line2
  putStrLn $ "Concatenated lines: " ++ combined
```

---

### 💡 How It Works

* Reads two separate lines using `getLine`.
* Concatenates them using `(++)`.
* Prints the combined string.

---

### ▶ Example Run

```
Enter the first line:
Hello,
Enter the second line:
 world!
Concatenated lines: Hello, world!
```
