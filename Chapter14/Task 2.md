HC14T2: Add Dependency and Print Random Number

---

### ✅ Step 1: Modify the `.cabal` file

Open your `.cabal` file (e.g., `HelloCabal.cabal`) and **add `random` to the `build-depends`** section under the executable stanza:

```cabal
executable HelloCabal
  main-is:             Main.hs
  hs-source-dirs:      app
  build-depends:       base >=4.7 && <5,
                       random
  default-language:    Haskell2010
```

---

### ✅ Step 2: Update `app/Main.hs`

```haskell
module Main where

import System.Random (randomRIO)

main :: IO ()
main = do
    putStrLn "Generating a random number between 1 and 100..."
    number <- randomRIO (1, 100) :: IO Int
    putStrLn $ "Random number: " ++ show number
```

---

### ✅ Step 3: Build and Run

```bash
cabal build
cabal run HelloCabal
```

---

### ✅ Example Output

```
Generating a random number between 1 and 100...
Random number: 42
```
