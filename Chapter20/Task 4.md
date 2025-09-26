HC20T4: countChars with State Monad

```haskell
import Control.Monad.State

-- countChars takes a Char and a String, returns the count of that Char in the String using State Int
countChars :: Char -> String -> Int
countChars ch str = execState (mapM_ updateCount str) 0
  where
    updateCount :: Char -> State Int ()
    updateCount c = do
      count <- get
      if c == ch
        then put (count + 1)
        else put count

main :: IO ()
main = do
  let testStr = "hello world, how many l's are here?"
      charToCount = 'l'
      result = countChars charToCount testStr
  putStrLn $ "Number of '" ++ [charToCount] ++ "' in the string: " ++ show result
```

---

### Explanation:

* The `State Int` monad keeps track of the current count.
* We traverse the string with `mapM_ updateCount`, updating state if the character matches.
* Finally, `execState` runs the stateful computation starting from 0 and returns the final count.

---
