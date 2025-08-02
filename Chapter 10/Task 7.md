HC10T7: Convertible Type Class

1. Defines a `PaymentMethod` type.
2. Creates a **multi-parameter** type class `Convertible a b` with the method `convert :: a -> b`.
3. Implements `convert` to convert `PaymentMethod` to `String`.

---

### ✅ Haskell Code

```haskell
{-# LANGUAGE MultiParamTypeClasses #-}

-- Define the PaymentMethod data type
data PaymentMethod = Cash | Card | Cryptocurrency deriving (Show)

-- Define the Convertible type class with two type parameters
class Convertible a b where
  convert :: a -> b

-- Make PaymentMethod convertible to String
instance Convertible PaymentMethod String where
  convert Cash = "Paid with cash"
  convert Card = "Paid with card"
  convert Cryptocurrency = "Paid with cryptocurrency"

-- Example usage
main :: IO ()
main = do
  putStrLn (convert Cash)
  putStrLn (convert Card)
  putStrLn (convert Cryptocurrency)
```

---
