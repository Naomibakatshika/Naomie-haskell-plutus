HC10T2: Summable Type Class

* Defines a **type class** `Summable` with a function `sumUp :: [a] -> a`.
* Implements the **instance for `Int`**.

---

### ✅ Haskell Code

```haskell
-- Define the Summable type class
class Summable a where
  sumUp :: [a] -> a

-- Implement Summable for Int
instance Summable Int where
  sumUp = foldr (+) 0

-- Example usage
main :: IO ()
main = do
  let numbers = [1, 2, 3, 4, 5] :: [Int]
  putStrLn $ "Sum of numbers: " ++ show (sumUp numbers)
```

---

### 🧪 Sample Output

```
Sum of numbers: 15
```
