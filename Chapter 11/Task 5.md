HC11T5: Repeat Until "quit"

---

### ✅ Haskell Code

```haskell
-- Program that repeatedly asks for input until user types "quit"

main :: IO ()
main = loop
  where
    loop = do
      putStrLn "Enter something (type 'quit' to exit):"
      input <- getLine
      if input == "quit"
        then putStrLn "Goodbye!"
        else do
          putStrLn $ "You entered: " ++ input
          loop
```

---

### 💡 How It Works

* Defines a recursive `loop` function inside `main`.
* Reads input each iteration.
* Stops if input is `"quit"`.
* Otherwise, prints the input and calls `loop` again.

---

### ▶ Example Run

```
Enter something (type 'quit' to exit):
Hello
You entered: Hello
Enter something (type 'quit' to exit):
Haskell
You entered: Haskell
Enter something (type 'quit' to exit):
quit
Goodbye!
```
