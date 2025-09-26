HC20T7: findFirst with Either Monad

```haskell
findFirst :: (a -> Bool) -> [a] -> Either String a
findFirst _ [] = Left "No element found matching the predicate."
findFirst predicate (x:xs)
  | predicate x = Right x
  | otherwise   = findFirst predicate xs

main :: IO ()
main = do
  print $ findFirst (> 5) [1, 2, 3, 6, 8]  -- Should print: Right 6
  print $ findFirst (< 0) [1, 2, 3, 6, 8]  -- Should print: Left "No element found matching the predicate."
```

### Explanation:

* `findFirst` takes a predicate `(a -> Bool)` and a list `[a]`.
* It recursively checks elements; if none matches, returns `Left` with an error string.
* If an element matches, returns `Right` with that element.
* The `main` function tests it with two cases.
