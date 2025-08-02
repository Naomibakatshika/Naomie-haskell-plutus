HC11T9: Sum Two Numbers

---

### ✅ Haskell Code

```haskell
main :: IO ()
main = do
  putStrLn "Enter the first number:"
  input1 <- getLine
  putStrLn "Enter the second number:"
  input2 <- getLine
  let num1 = read input1 :: Int
      num2 = read input2 :: Int
      sumResult = num1 + num2
  putStrLn $ "The sum is: " ++ show sumResult
```

---

### 💡 How It Works

* Reads two lines of input.
* Converts both inputs to integers using `read`.
* Adds them and prints the result.

---

### ▶ Example Run

```
Enter the first number:
10
Enter the second number:
25
The sum is: 35
```
