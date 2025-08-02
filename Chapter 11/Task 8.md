HC11T8: Even or Odd Checker

---

### ✅ Haskell Code

```haskell
main :: IO ()
main = do
  putStrLn "Enter a number:"
  input <- getLine
  let number = read input :: Int
  if even number
    then putStrLn "The number is even."
    else putStrLn "The number is odd."
```

---

### 💡 How It Works

* Reads input as a string.
* Converts it to an `Int` with `read`.
* Uses the built-in `even` function to check parity.
* Prints the result accordingly.

---

### ▶ Example Run

```
Enter a number:
7
The number is odd.
```
