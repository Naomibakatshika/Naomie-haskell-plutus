HC10T1: ShowSimple Type Class

* Defines a new type class `ShowSimple` with the method `showSimple`.
* Defines a `PaymentMethod` data type.
* Implements an instance of `ShowSimple` for `PaymentMethod`.

---

### ✅ Haskell Code

```haskell
-- Define the ShowSimple type class
class ShowSimple a where
  showSimple :: a -> String

-- Define the PaymentMethod data type
data PaymentMethod = Cash | Card | Cryptocurrency
  deriving (Eq, Show)

-- Implement ShowSimple instance for PaymentMethod
instance ShowSimple PaymentMethod where
  showSimple Cash           = "Cash"
  showSimple Card           = "Card"
  showSimple Cryptocurrency = "Cryptocurrency"

-- Example usage
main :: IO ()
main = do
  putStrLn $ showSimple Cash
  putStrLn $ showSimple Card
  putStrLn $ showSimple Cryptocurrency
```

---

### 🧪 Sample Output

```
Cash
Card
Cryptocurrency
```
