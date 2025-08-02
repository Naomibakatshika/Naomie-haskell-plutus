HC9T1: Define a Parametric Type Synonym

---

### ✅ Haskell Code

```haskell
-- Parametric type synonym for Entity with an address of type a
type Entity a = (String, a)  -- (EntityName, Address)

-- Example usage with different address types

-- Address as String
entity1 :: Entity String
entity1 = ("Alice", "123 Main St")

-- Address as (Street, Zip) tuple
entity2 :: Entity (String, Int)
entity2 = ("Bob's Shop", ("Market Road", 90210))

-- Main function to print example entities
main :: IO ()
main = do
  print entity1
  print entity2
```

---

### 🧪 Sample Output

```
("Alice","123 Main St")
("Bob's Shop",("Market Road",90210))
```

---
