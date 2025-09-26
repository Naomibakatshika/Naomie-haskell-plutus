HC18T1: mapToLower Function with fmap

```haskell
import Data.Char (toLower)

-- mapToLower converts all characters in a list to lowercase using fmap
mapToLower :: [Char] -> [Char]
mapToLower = fmap toLower

-- Example usage
main :: IO ()
main = do
  let text = "Hello, HASKELL!"
  putStrLn $ "Original: " ++ text
  putStrLn $ "Lowercase: " ++ mapToLower text
```

---

### Output:

```
Original: Hello, HASKELL!
Lowercase: hello, haskell!
```
