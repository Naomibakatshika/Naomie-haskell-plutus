HC2T3 - Task 3: Immutable Variables

* Defines four **immutable variables**:

  * `myAge :: Int`
  * `piValue :: Double`
  * `greeting :: String`
  * `isHaskellFun :: Bool`
* Demonstrates that these variables **cannot be changed** after being defined.
* Attempts to "modify" a variable (in a commented-out line) to show what happens.

---

### ✅ Full Haskell Code

```haskell
-- Immutable variable definitions
myAge :: Int
myAge = 25

piValue :: Double
piValue = 3.14159

greeting :: String
greeting = "Hello, Haskell!"

isHaskellFun :: Bool
isHaskellFun = True

main :: IO ()
main = do
    putStrLn $ "My age: " ++ show myAge
    putStrLn $ "Value of pi: " ++ show piValue
    putStrLn $ "Greeting: " ++ greeting
    putStrLn $ "Is Haskell fun? " ++ show isHaskellFun

    -- Attempt to "modify" an immutable variable (this won't compile if uncommented)
    -- myAge = 30  -- ❌ Error: Cannot redefine `myAge`

    putStrLn "\nNOTE: Variables in Haskell are immutable. Uncommenting the line above will cause a compile-time error."
```

---

### 🏃 How to Run:

1. Save it as `ImmutableVars.hs`
2. Compile and run:

```bash
ghc ImmutableVars.hs -o immutables
./immutables
```

---

### 🔥 What Happens If You Try to Modify?

If you uncomment this line:

```haskell
myAge = 30
```

You'll get a **compile-time error**, like this:

```
ImmutableVars.hs:17:5: error:
    Multiple declarations of ‘myAge’
    Declared at: ImmutableVars.hs:4:1
```

This reinforces the idea that **variables in Haskell are immutable** — once defined, they cannot be changed.


