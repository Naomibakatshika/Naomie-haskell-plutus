HC11T3: Double a Number

---

### ✅ Haskell Code

```haskell
-- Program to read a number and print it multiplied by 2

main :: IO ()
main = do
  putStrLn "Please enter a number:"
  input <- getLine
  let number = read input :: Int
  let result = number * 2
  putStrLn $ "The number multiplied by 2 is: " ++ show result
```

---

### 💡 How It Works

* `getLine` reads input as a `String`.
* `read` converts the `String` to an `Int`.
* The number is multiplied by 2.
* The result is printed.

---

### ▶ Example Run

```
Please enter a number:
7
The number multiplied by 2 is: 14
```
