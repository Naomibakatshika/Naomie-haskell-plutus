HC11T7: User Options

* Prints a menu of options to the user.
* Reads the user's choice.
* Executes different code based on the choice.

---

### ✅ Haskell Code

```haskell
main :: IO ()
main = do
  putStrLn "Choose an option:"
  putStrLn "1. Greet"
  putStrLn "2. Show current time"
  putStrLn "3. Exit"
  choice <- getLine
  case choice of
    "1" -> do
      putStrLn "Hello! Nice to meet you."
      main  -- loop back to menu
    "2" -> do
      putStrLn "Sorry, time functionality not implemented yet."
      main  -- loop back to menu
    "3" -> putStrLn "Goodbye!"
    _   -> do
      putStrLn "Invalid choice, try again."
      main  -- loop back to menu
```

---

### 💡 How It Works

* Displays options 1, 2, and 3.
* Uses `case` on user input to decide what to do.
* Loops back to the menu unless the user chooses to exit.

---

### ▶ Example Run

```
Choose an option:
1. Greet
2. Show current time
3. Exit
2
Sorry, time functionality not implemented yet.
Choose an option:
1. Greet
2. Show current time
3. Exit
1
Hello! Nice to meet you.
Choose an option:
1. Greet
2. Show current time
3. Exit
3
Goodbye!
```
