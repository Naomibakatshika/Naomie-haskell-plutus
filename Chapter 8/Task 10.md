HC8T10: Deriving Show for Book

* Defines a `Book` type using record syntax,
* Uses `deriving Show` so it can be printed,
* Creates an instance of a `Book`, and
* Prints it using the `Show` instance.

---

### ✅ Haskell Code

```haskell
-- Define the Book type with Show deriving
data Book = Book
  { title  :: String
  , author :: String
  , year   :: Int
  } deriving (Show)

-- Example usage
main :: IO ()
main = do
  let myBook = Book
        { title  = "The Haskell Road to Logic, Math and Programming"
        , author = "Kees Doets and Jan van Eijck"
        , year   = 2004
        }
  print myBook
```

---

### 🧪 Sample Output

```
Book {title = "The Haskell Road to Logic, Math and Programming", author = "Kees Doets and Jan van Eijck", year = 2004}
```
