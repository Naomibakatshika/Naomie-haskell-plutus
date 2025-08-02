HC8T8: Type Synonyms and Greeting Function

---

### ✅ Haskell Code

```haskell
-- Type synonyms
type Name = String
type Age = Int

-- Greet function using Name and Age
greet :: Name -> Age -> String
greet name age = "Hello, " ++ name ++ "! You are " ++ show age ++ " years old."

-- Example usage in main
main :: IO ()
main = do
  putStrLn (greet "Alice" 30)
  putStrLn (greet "Bob" 45)
```

---

### 🧪 Output when run:

```
Hello, Alice! You are 30 years old.
Hello, Bob! You are 45 years old.
```
