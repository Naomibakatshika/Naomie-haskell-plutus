HC18T4: mapToBits Function

```haskell
-- mapToBits converts each Bool to '1' if True, '0' if False
mapToBits :: [Bool] -> [Char]
mapToBits = fmap (\b -> if b then '1' else '0')

-- Example usage
main :: IO ()
main = do
  let boolList = [True, False, True, True, False]
  putStrLn $ "Original bool list: " ++ show boolList
  putStrLn $ "Converted to bits: " ++ mapToBits boolList
```

---

### Output:

```
Original bool list: [True,False,True,True,False]
Converted to bits: 10110
```
