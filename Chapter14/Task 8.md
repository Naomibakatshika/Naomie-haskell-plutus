HC14T8: Character Frequency Function

---

### ✅ Full Running Code (`counts.hs`)

```haskell
import Data.List (group, sort)

-- | Returns a list of (Char, Int) pairs showing frequency of characters
counts :: String -> [(Char, Int)]
counts str = map (\g -> (head g, length g)) . group . sort $ str

-- Example usage in main
main :: IO ()
main = do
  putStrLn "Enter a string:"
  input <- getLine
  let result = counts input
  putStrLn "Character frequencies:"
  print result
```

---

### 🔍 How it Works:

1. `sort str` — sorts characters so identical ones are adjacent.
2. `group` — groups adjacent equal elements.
3. `map (\g -> (head g, length g))` — converts each group into a tuple: the character and its count.

---

### ✅ Example Run

```bash
$ runhaskell counts.hs
Enter a string:
banana
Character frequencies:
[('a',3),('b',1),('n',2)]
```

---
