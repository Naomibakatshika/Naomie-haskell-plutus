HC14T5: Custom Data Type and Pattern Matching with @

---

### ✅ `Main.hs`

```haskell
module Main where

-- Define a custom data type Result
data Result a = Success a | Error String
  deriving Show

-- Function that demonstrates pattern matching using @
describeResult :: Show a => Result a -> String
describeResult r@(Success val) = "Got a Success result: " ++ show r ++ ", with value: " ++ show val
describeResult r@(Error msg)   = "Got an Error result: " ++ show r ++ ", with message: " ++ msg

main :: IO ()
main = do
    let res1 = Success 42
    let res2 = Error "Something went wrong"
    
    putStrLn (describeResult res1)
    putStrLn (describeResult res2)
```

---

### 🧠 Key Features:

* `Result a` has two constructors: `Success a` and `Error String`.
* Pattern matching with `@` like `r@(Success val)`:

  * Binds `r` to the entire value (`Success 42`).
  * Binds `val` to the unwrapped value (`42`).
* Demonstrates `describeResult` for both constructors.

---

### ▶️ To Compile and Run:

```bash
ghc Main.hs -o result-app
./result-app
```

---
