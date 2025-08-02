HC8T1: Type Synonyms and Basic Function

---

### ✅ Haskell Code

```haskell
-- Type synonyms
type Address = String
type Value = Int

-- Function that generates a transaction description
generateTx :: Address -> Address -> Value -> String
generateTx from to amount =
    "Transaction from " ++ from ++ " to " ++ to ++ " of " ++ show amount ++ " units."

-- Main function for testing
main :: IO ()
main = do
    let sender = "Alice123"
    let receiver = "Bob456"
    let amount = 100
    putStrLn $ generateTx sender receiver amount
```

---

### 💡 How It Works

* `type Address = String` and `type Value = Int` are type synonyms used for clarity.
* `generateTx` builds a simple string that represents a transaction from one address to another.

---

### 🧪 Sample Output

```
Transaction from Alice123 to Bob456 of 100 units.
```
