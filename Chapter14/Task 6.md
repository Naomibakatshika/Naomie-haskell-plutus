HC14T6: Project Structure: src and app

---

### 📁 Final Project Structure:

```
MyProject/
├── app/
│   └── Main.hs
├── src/
│   └── Utils.hs
├── MyProject.cabal
├── CHANGELOG.md
├── LICENSE
├── README.md
└── cabal.project
```

---

### ✅ 1. Create Project Directory

```bash
mkdir MyProject
cd MyProject
cabal init --non-interactive --minimal --package-name=MyProject
```

---

### ✅ 2. Create Directories

```bash
mkdir app src
```

---

### ✅ 3. Edit `MyProject.cabal`

Update the `.cabal` file like this:

```cabal
cabal-version:       >=1.10
name:                MyProject
version:             0.1.0.0
build-type:          Simple

library
  hs-source-dirs:      src
  exposed-modules:     Utils
  build-depends:       base >=4.7 && <5
  default-language:    Haskell2010

executable MyProject-exe
  hs-source-dirs:      app
  main-is:             Main.hs
  build-depends:       base >=4.7 && <5,
                       MyProject
  default-language:    Haskell2010
```

---

### ✅ 4. Create `src/Utils.hs`

```haskell
module Utils (greet) where

greet :: String -> String
greet name = "Hello, " ++ name ++ "!"
```

---

### ✅ 5. Create `app/Main.hs`

```haskell
module Main where

import Utils (greet)

main :: IO ()
main = do
    putStrLn (greet "Cabal Project")
```

---

### ✅ 6. Build and Run

```bash
cabal build
cabal run MyProject-exe
```

---

### 🧪 Output

```
Hello, Cabal Project!
```
