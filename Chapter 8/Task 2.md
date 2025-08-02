HC8T2: New Types and Data Constructors

1. A `PaymentMethod` data type
2. A `Person` type including `name`, `address`, and `paymentMethod`
3. An instance `bob` who pays with `Cash`

---

### ✅ Haskell Code

```haskell
-- Define the PaymentMethod type
data PaymentMethod = Cash | Card | Cryptocurrency
    deriving (Show)

-- Define the Person type
data Person = Person
    { name :: String
    , address :: (String, Int)
    , paymentMethod :: PaymentMethod
    } deriving (Show)

-- Create a person named bob who pays with cash
bob :: Person
bob = Person
    { name = "Bob"
    , address = ("Main Street", 42)
    , paymentMethod = Cash
    }

-- Main function to test and display bob's info
main :: IO ()
main = print bob
```

---

### 🧪 Sample Output

```
Person {name = "Bob", address = ("Main Street",42), paymentMethod = Cash}
```
