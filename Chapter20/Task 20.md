HC20T20: batchProcessing with Monadic Bind

---

### ✅ Full Working Code

```haskell
module Main where

-- Simulates a monadic processing pipeline using IO and bind (>>=)
batchProcessing :: IO ()
batchProcessing =
    getLine >>= \input1 ->
    putStrLn ("You entered: " ++ input1) >>= \_ ->
    getLine >>= \input2 ->
    putStrLn ("Next input was: " ++ input2)

-- Main function to run batchProcessing
main :: IO ()
main = do
    putStrLn "Enter first input:"
    batchProcessing
```

---

### 🧪 Example Run

```bash
Enter first input:
hello
You entered: hello
world
Next input was: world
```

---

### 🔍 Explanation

* `>>=` is the monadic bind operator: it takes a monadic value and a function, passing the unwrapped result to the function.
* `getLine` reads user input (an `IO String`).
* The lambda (`\input1 -> ...`) handles the unwrapped string and performs further actions.
* The actions are chained in sequence using only `>>=` to demonstrate explicit monadic composition.

---
