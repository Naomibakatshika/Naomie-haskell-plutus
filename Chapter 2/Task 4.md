HC2T4 - Task 4: Converting Between Infix and Prefix Notations

* Converts **infix expressions** to **prefix (function) notation**
* Converts **prefix function calls** to **infix notation**
* Prints all results for clarity

---

### ✅ Full Haskell Code

```haskell
main :: IO ()
main = do
    -- Infix to Prefix
    let expr1_prefix = (+) 5 3       -- Equivalent to 5 + 3
    let expr2_prefix = (*) 10 4      -- Equivalent to 10 * 4
    let expr3_prefix = (&&) True False  -- Equivalent to True && False

    putStrLn "Infix to Prefix:"
    putStrLn $ "(+) 5 3 = " ++ show expr1_prefix
    putStrLn $ "(*) 10 4 = " ++ show expr2_prefix
    putStrLn $ "(&&) True False = " ++ show expr3_prefix

    -- Prefix to Infix
    let expr4_infix = 7 + 2
    let expr5_infix = 6 * 5
    let expr6_infix = True && False

    putStrLn "\nPrefix to Infix:"
    putStrLn $ "7 + 2 = " ++ show expr4_infix
    putStrLn $ "6 * 5 = " ++ show expr5_infix
    putStrLn $ "True && False = " ++ show expr6_infix
```

---

### 🏃 How to Run:

1. Save it as `PrefixInfix.hs`
2. Compile and run it:

```bash
ghc PrefixInfix.hs -o prefixinfix
./prefixinfix
```

---

### 🔍 Output:

```
Infix to Prefix:
(+) 5 3 = 8
(*) 10 4 = 40
(&&) True False = False

Prefix to Infix:
7 + 2 = 9
6 * 5 = 30
True && False = False
```

