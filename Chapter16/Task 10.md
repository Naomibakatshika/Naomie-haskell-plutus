HC16T10: Character Frequency in String

```haskell
import qualified Data.Map as Map
import Data.Char (toLower)

-- Function to count frequency of each character
charFrequency :: String -> Map.Map Char Int
charFrequency = foldr insertChar Map.empty
  where
    insertChar c = Map.insertWith (+) c 1

-- Main function to demonstrate usage
main :: IO ()
main = do
  putStrLn "Enter a string:"
  input <- getLine
  let freqMap = charFrequency (map toLower input)
  putStrLn "Character frequencies:"
  mapM_ print (Map.toList freqMap)
```

### Example Usage:

**Input:**

```
Enter a string:
Hello World
```

**Output:**

```
Character frequencies:
('d',1)
('l',3)
('r',1)
('o',2)
('w',1)
('e',1)
('h',1)
(' ',1)
```
