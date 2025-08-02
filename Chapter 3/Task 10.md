HC3T10 - Advanced Task 10: Check if a string is a palindrome using recursion and guards

* Defines the function `isPalindrome :: String -> Bool` using **guards**
* Uses recursion to check whether a string is a **palindrome**
* Tests the function with:

  * `"racecar"` → `True`
  * `"haskell"` → `False`
  * `"madam"` → `True`

---

### ✅ Full Haskell Code

```haskell
-- Recursive function to check if a string is a palindrome
isPalindrome :: String -> Bool
isPalindrome str
    | length str <= 1 = True
    | head str == last str = isPalindrome (init (tail str))
    | otherwise = False

-- Main function to test isPalindrome
main :: IO ()
main = do
    putStrLn $ "isPalindrome \"racecar\" = " ++ show (isPalindrome "racecar")   -- True
    putStrLn $ "isPalindrome \"haskell\" = " ++ show (isPalindrome "haskell")   -- False
    putStrLn $ "isPalindrome \"madam\"   = " ++ show (isPalindrome "madam")     -- True
```

---

### 🏃 How to Run:

1. Save the file as `Palindrome.hs`
2. Compile and run:

```bash
ghc Palindrome.hs -o palindrome
./palindrome
```

---

### 🧾 Expected Output:

```
isPalindrome "racecar" = True
isPalindrome "haskell" = False
isPalindrome "madam"   = True
```

