HC8T9: Record Type and Transaction Function

1. Defines **type synonyms** `Address` and `Value`.
2. Defines a **data type** `Transaction` using **record syntax**.
3. Implements a **function `createTransaction`** that constructs a `Transaction` and returns its `transactionId`.

---

### ✅ Haskell Code

```haskell
-- Type synonyms
type Address = String
type Value = Int

-- Transaction data type
data Transaction = Transaction
  { from          :: Address
  , to            :: Address
  , amount        :: Value
  , transactionId :: String
  } deriving (Show)

-- Function to create a Transaction and return its ID
createTransaction :: Address -> Address -> Value -> String
createTransaction fromAddr toAddr val =
  let txId = "TX-" ++ fromAddr ++ "-" ++ toAddr ++ "-" ++ show val
      tx = Transaction { from = fromAddr, to = toAddr, amount = val, transactionId = txId }
  in transactionId tx

-- Example usage
main :: IO ()
main = do
  let txId = createTransaction "Alice123" "Bob456" 100
  putStrLn $ "Transaction ID: " ++ txId
```

---

### 🧪 Sample Output

```
Transaction ID: TX-Alice123-Bob456-100
```

This code:

* Uses string manipulation to generate a fake `transactionId`.
* Returns that ID from the `createTransaction` function.
* You can later extend this to return the full `Transaction` record if needed.
