HC10T5: ShowDetailed Type Class

1. Defines a type class `ShowDetailed` with a function `showDetailed :: a -> String`.
2. Defines a `User` type with fields like name and age.
3. Implements the `ShowDetailed` type class for the `User` type.

---

### ✅ Haskell Code

```haskell
-- Define the ShowDetailed type class
class ShowDetailed a where
  showDetailed :: a -> String

-- Define a User data type
data User = User
  { name :: String
  , age  :: Int
  }

-- Implement ShowDetailed for User
instance ShowDetailed User where
  showDetailed (User n a) = "User Name: " ++ n ++ ", Age: " ++ show a

-- Example usage
main :: IO ()
main = do
  let user1 = User "Alice" 30
  let user2 = User "Bob" 25

  putStrLn (showDetailed user1)
  putStrLn (showDetailed user2)
```

---

### 🧪 Sample Output

```
User Name: Alice, Age: 30
User Name: Bob, Age: 25
```
