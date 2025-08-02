HC8T7: Data Types and Describing Animals

---

### ✅ Haskell Code

```haskell
-- Define the Animal type
data Animal = Dog String | Cat String
  deriving (Show)

-- Function to describe the animal
describeAnimal :: Animal -> String
describeAnimal (Dog name) = "This is a dog named " ++ name ++ "."
describeAnimal (Cat name) = "This is a cat named " ++ name ++ "."

-- Example animal instances
dog1 :: Animal
dog1 = Dog "Buddy"

cat1 :: Animal
cat1 = Cat "Whiskers"

-- Main function to print descriptions
main :: IO ()
main = do
  putStrLn (describeAnimal dog1)
  putStrLn (describeAnimal cat1)
```

---

### 🧪 Output when run:

```
This is a dog named Buddy.
This is a cat named Whiskers.
```
