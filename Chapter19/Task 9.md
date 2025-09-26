HC19T9: pureAndApply Demonstration

```haskell
-- pureAndApply.hs
-- Demonstrates how `pure` works in applicative contexts

pureAndApply :: IO ()
pureAndApply = do
  let add :: Int -> Int -> Int
      add x y = x + y

  putStrLn "Using pure with applicative style:"
  
  let result = pure add <*> Just 3 <*> Just 4
  putStrLn $ "pure add <*> Just 3 <*> Just 4 = " ++ show result

  let ioResult = pure add <*> pure 10 <*> pure 20 :: IO Int
  final <- ioResult
  putStrLn $ "pure add <*> pure 10 <*> pure 20 (in IO) = " ++ show final

main :: IO ()
main = pureAndApply
```

---

### Explanation:

* `pure` lifts a value (like a function) into an applicative context.
* `pure add <*> Just 3 <*> Just 4` applies the function `add` inside the `Maybe` context.
* `pure add <*> pure 10 <*> pure 20` does the same in the `IO` context.

---

### Sample Output:

```
Using pure with applicative style:
pure add <*> Just 3 <*> Just 4 = Just 7
pure add <*> pure 10 <*> pure 20 (in IO) = 30
```

---

You can run this with:

```bash
runhaskell pureAndApply.hs
```
