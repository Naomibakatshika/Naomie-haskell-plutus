HC14T7: Library Component in Cabal

```
MyProject/
├── app/
│   └── Main.hs          -- your main executable
├── src/
│   └── MyLib.hs         -- your library module
├── MyProject.cabal      -- the cabal file
```

---

### ✅ Example `MyProject.cabal` File (Modified)

```cabal
cabal-version:       >=1.10
name:                MyProject
version:             0.1.0.0
build-type:          Simple

-- Library component
library
  hs-source-dirs:      src
  exposed-modules:     MyLib
  build-depends:       base >=4.7 && <5
  default-language:    Haskell2010

-- Executable component
executable MyProject-exe
  hs-source-dirs:      app
  main-is:             Main.hs
  build-depends:       base >=4.7 && <5,
                       MyProject           -- dependency on the library
  default-language:    Haskell2010
```

---

### ✅ Example Library Module (`src/MyLib.hs`)

```haskell
module MyLib (greet) where

greet :: String -> String
greet name = "Hello, " ++ name ++ "!"
```

---

### ✅ Example Executable (`app/Main.hs`)

```haskell
module Main where

import MyLib (greet)

main :: IO ()
main = putStrLn (greet "Cabal with Library")
```

---

### ✅ Build and Run

```bash
cabal build
cabal run MyProject-exe
```

---

### ✅ Output

```
Hello, Cabal with Library
```
