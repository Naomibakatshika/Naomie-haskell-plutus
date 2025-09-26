HC20T1: safeDivide with Maybe Monad

```haskell
-- safeDivide.hs
-- A program that safely divides two numbers using the Maybe monad

safeDivide :: Double -> Double -> Maybe Double
safeDivide _ 0 = Nothing
safeDivide x y = Just (x / y)

main :: IO ()
main = do
  let result1 = safeDivide 10 2
  let result2 = safeDivide 10 0

  putStrLn $ "10 / 2 = " ++ show result1
  putStrLn $ "10 / 0 = " ++ show result2
```

---

### Output:

```haskell
10 / 2 = Just 5.0
10 / 0 = Nothing
```

---

### How to Run:

Save the code in a file named `safeDivide.hs` and run:

```bash
runhaskell safeDivide.hs
```
