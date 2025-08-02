HC11T1: Greet the User

---

### ✅ Haskell Code

```haskell
-- Greeting program in Haskell

main :: IO ()
main = do
  putStrLn "What is your name?"
  name <- getLine
  putStrLn ("Hello, " ++ name ++ "! Nice to meet you.")
```

---

### 💡 How It Works

* `putStrLn` displays a prompt to the user.
* `getLine` reads input from the user (in this case, their name).
* The input is stored in `name`, and then used in the final greeting message.

---

### ▶ Example Run

```
What is your name?
Alice
Hello, Alice! Nice to meet you.
```
