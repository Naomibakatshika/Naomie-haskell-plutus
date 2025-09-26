HC14T1: Initialize a Cabal Project

---

### ✅ **Step-by-step Instructions**

#### 1. **Create a new project directory**

```bash
mkdir HelloCabal
cd HelloCabal
```

---

#### 2. **Initialize the Cabal project**

```bash
cabal init --non-interactive --minimal --exe --package-name HelloCabal
```

This generates:

* `HelloCabal.cabal`
* `app/Main.hs`
* `cabal.project`

---

#### 3. **Edit `app/Main.hs`**

Make sure it looks like this:

```haskell
module Main where

main :: IO ()
main = putStrLn "Hello, Cabal!"
```

---

#### 4. **Build the project**

```bash
cabal build
```

---

#### 5. **Run the executable**

```bash
cabal run HelloCabal
```

---

### ✅ Expected Output

```
Hello, Cabal!
```

---
