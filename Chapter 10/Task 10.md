HC10T10: Concatenatable Type Class

---

### ✅ Haskell Code

```haskell
-- Define the Concatenatable type class
class Concatenatable a where
  concatWith :: a -> a -> a

-- Implement the instance for String (which is [Char])
instance Concatenatable String where
  concatWith = (++)

-- Test the function
main :: IO ()
main = do
  let str1 = "Hello, "
      str2 = "world!"
  putStrLn $ concatWith str1 str2
```

---

### 🧠 Explanation

* The type class `Concatenatable` defines a method `concatWith` that combines two values of the same type.
* The instance for `String` uses the `(++)` operator, which concatenates two lists (including strings).
* The `main` function demonstrates usage by combining `"Hello, "` and `"world!"`.

---
