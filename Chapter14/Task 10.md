HC14T10: Cabal Test Suite

---

### 1. Project structure:

```
MyProject/
├── app/
│   └── Main.hs           -- your main executable (optional)
├── src/
│   └── Counts.hs         -- module with counts function
├── test/
│   └── Spec.hs           -- test suite using Hspec
├── MyProject.cabal       -- cabal file with test-suite section
```

---

### 2. `src/Counts.hs`

```haskell
module Counts (counts) where

import Data.List (group, sort)

counts :: String -> [(Char, Int)]
counts str = map (\g -> (head g, length g)) . group . sort $ str
```

---

### 3. `test/Spec.hs`

```haskell
{-# OPTIONS_GHC -F -pgmF hspec-discover #-}
```

> This file uses **hspec-discover** to automatically find and run tests.

Create a separate test file for detailed tests:

---

### 4. `test/CountsSpec.hs`

```haskell
module CountsSpec where

import Test.Hspec
import Counts (counts)

spec :: Spec
spec = do
  describe "counts" $ do
    it "returns empty list for empty string" $ do
      counts "" `shouldBe` []

    it "counts characters correctly" $ do
      counts "banana" `shouldBe` [('a',3), ('b',1), ('n',2)]

    it "counts single characters" $ do
      counts "a" `shouldBe` [('a',1)]

    it "is case sensitive" $ do
      counts "aA" `shouldBe` [('A',1), ('a',1)]
```

---

### 5. Update your `.cabal` file to include the test suite

Add this at the bottom of your `.cabal` file:

```cabal
test-suite MyProject-test
  type:                exitcode-stdio-1.0
  hs-source-dirs:      test src
  main-is:             Spec.hs
  build-depends:       base >=4.7 && <5,
                       hspec >=2.7,
                       MyProject
  default-language:    Haskell2010
```

---

### 6. Build and run tests

Run:

```bash
cabal update
cabal install hspec    # if you don't have it yet
cabal build
cabal test
```

---

### ✅ Summary

* `Counts.hs` contains the function.
* `test/CountsSpec.hs` contains test cases.
* `test/Spec.hs` is the test discoverer entry point.
* `.cabal` file includes the test suite config.

---
