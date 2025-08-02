HC4T4 - Task 4: Rewrite specialBirthday using Pattern Matching

---

### ✅ Assumptions

The original `specialBirthday` function likely checked for special birthday ages like `1`, `18`, `21`, `50`, `100`, etc. We'll match a few typical ones.

---

### ✅ Full Haskell Code (Pattern Matching Version)

```haskell
-- Function that uses pattern matching to return birthday messages
specialBirthday :: Int -> String
specialBirthday 1   = "Happy 1st Birthday!"
specialBirthday 18  = "Congratulations on becoming an adult!"
specialBirthday 21  = "Cheers to 21! Time to celebrate!"
specialBirthday 50  = "Half a century old—Happy 50th!"
specialBirthday 100 = "A century! What a milestone!"
specialBirthday age = "Happy " ++ show age ++ "th Birthday!"

-- Main function to test specialBirthday
main :: IO ()
main = do
    putStrLn $ specialBirthday 1
    putStrLn $ specialBirthday 18
    putStrLn $ specialBirthday 21
    putStrLn $ specialBirthday 50
    putStrLn $ specialBirthday 100
    putStrLn $ specialBirthday 33
```

---

### 🏃 How to Run:

1. Save the file as `SpecialBirthday.hs`
2. Compile and run it:

```bash
ghc SpecialBirthday.hs -o birthday
./birthday
```

---

### 🧾 Sample Output:

```
Happy 1st Birthday!
Congratulations on becoming an adult!
Cheers to 21! Time to celebrate!
Half a century old—Happy 50th!
A century! What a milestone!
Happy 33th Birthday!
```

