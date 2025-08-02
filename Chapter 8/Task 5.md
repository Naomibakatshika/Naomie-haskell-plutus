HC8T5: Record Syntax for Person

---

### ✅ Haskell Code

```haskell
-- Define the Person type using record syntax
data Person = Person
  { name :: String
  , age :: Int
  , isEmployed :: Bool
  } deriving (Show)

-- Create two Person instances
person1 :: Person
person1 = Person { name = "Alice", age = 30, isEmployed = True }

person2 :: Person
person2 = Person { name = "Bob", age = 25, isEmployed = False }

-- Main function to print both persons
main :: IO ()
main = do
  putStrLn "Person 1:"
  print person1
  putStrLn "\nPerson 2:"
  print person2
```

---

### 🧪 Sample Output

```
Person 1:
Person {name = "Alice", age = 30, isEmployed = True}

Person 2:
Person {name = "Bob", age = 25, isEmployed = False}
```
