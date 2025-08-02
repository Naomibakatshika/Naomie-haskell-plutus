HC5T7: The $ Operator

---

### ✅ Original Expression

```haskell
result = sum (map (*2) (filter (>3) [1..10]))
```

---

### ✅ Rewritten with `$` Operator

```haskell
-- Rewritten using the $ operator
result :: Int
result = sum $ map (*2) $ filter (>3) [1..10]

-- Main function to test the result
main :: IO ()
main = do
    putStrLn "The result is:"
    print result
```

---

### 🏃 How to Run:

1. Save this as `DollarExample.hs`
2. Compile and run it:

```bash
ghc DollarExample.hs -o dollarexample
./dollarexample
```

---

### 🧾 Expected Output:

```
The result is:
84
```

---

### 💡 Why use `$`?

The `$` operator is **right-associative** and **low-precedence**, which allows you to **avoid nested parentheses**. For example:

```haskell
sum $ map (*2) $ filter (>3) [1..10]
```

is equivalent to:

```haskell
sum (map (*2) (filter (>3) [1..10]))
```
