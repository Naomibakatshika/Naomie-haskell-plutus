HC1T3 - Task 3: Checking if a Number is Greater than 18

```haskell
-- Define a function that checks if a number is greater than 18
greaterThan18 :: (Ord a, Num a) => a -> Bool
greaterThan18 x = x > 18

-- Main function to test greaterThan18
main :: IO ()
main = do
    let number = 20
    putStrLn $ "Given number: " ++ show number
    putStrLn $ "Is the number greater than 18? " ++ show (greaterThan18 number)
```

### Explanation:

* `greaterThan18 :: (Ord a, Num a) => a -> Bool`
  This type signature means the function works for any numeric type that supports ordering (like `Int`, `Float`, etc.).
* `x > 18` evaluates to `True` if `x` is greater than 18, otherwise `False`.

### How to Run:

1. Save it as `GreaterThan18.hs`.
2. Compile and run it with GHC:

```bash
ghc GreaterThan18.hs -o greater
./greater
```


