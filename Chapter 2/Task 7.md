HC2T7 - Task 7: Boolean Expressions

* `True` using `&&`
* `False` using `||`
* `True` using `not`
* A comparison that returns `False`

---

### ✅ Full Haskell Code

```haskell
main :: IO ()
main = do
    -- True using &&
    let expr1 = True && True
    putStrLn $ "True && True = " ++ show expr1

    -- False using ||
    let expr2 = False || False
    putStrLn $ "False || False = " ++ show expr2

    -- True using not
    let expr3 = not False
    putStrLn $ "not False = " ++ show expr3

    -- Comparison that returns False
    let expr4 = 10 < 5
    putStrLn $ "10 < 5 = " ++ show expr4
```

---

### 🏃 How to Run:

1. Save the code in a file named `BooleanExpressions.hs`
2. Compile and run it:

```bash
ghc BooleanExpressions.hs -o booltest
./booltest
```

---

### 🧾 Expected Output:

```
True && True = True
False || False = False
not False = True
10 < 5 = False
```

