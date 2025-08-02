HC4T5 - Task 5: Add a Catch-All Pattern with a Custom Message

---

### ✅ Updated Haskell Code

```haskell
-- Function that uses pattern matching for special birthdays,
-- and includes the age in the general case.
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
    putStrLn $ specialBirthday 33   -- Not a special age
    putStrLn $ specialBirthday 75   -- Not a special age
```

---

### 🏃 How to Run:

1. Save as: `SpecialBirthday.hs`
2. Compile and run:

```bash
ghc SpecialBirthday.hs -o birthday
./birthday
```

---

### 🧾 Example Output:

```
Happy 1st Birthday!
Congratulations on becoming an adult!
Cheers to 21! Time to celebrate!
Half a century old—Happy 50th!
A century! What a milestone!
Happy 33th Birthday!
Happy 75th Birthday!
```
