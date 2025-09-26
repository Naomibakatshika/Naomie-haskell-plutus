HC14T3: NumericUnderscores Extension

1. Enables the `NumericUnderscores` extension.
2. Creates large numbers using underscores for readability.
3. Prints them using the `main` function.

---

### ✅ `Main.hs`

```haskell
{-# LANGUAGE NumericUnderscores #-}

module Main where

main :: IO ()
main = do
    let bigNumber     = 1_000_000       :: Int
        largerNumber  = 123_456_789_012 :: Integer
        preciseNumber = 3.141_592_653   :: Double

    putStrLn $ "Big number: " ++ show bigNumber
    putStrLn $ "Larger number: " ++ show largerNumber
    putStrLn $ "Precise number: " ++ show preciseNumber
```

---

### ✅ To run the code:

If using GHC directly:

```bash
ghc Main.hs -o main
./main
```

If using a Cabal project, make sure the file is placed in the `app` directory and listed in your `.cabal` file under the `main-is:` entry.

---

### ✅ Example Output:

```
Big number: 1000000
Larger number: 123456789012
Precise number: 3.141592653
```
