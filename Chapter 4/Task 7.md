HC4T7 - Task 7: Ignore Elements in a List
---

### ✅ Haskell Code: `firstAndThird`

```haskell
-- Function to return the first and third elements from a list
firstAndThird :: [a] -> Maybe (a, a)
firstAndThird (x:_:z:_) = Just (x, z)   -- Pattern matches first and third
firstAndThird _         = Nothing       -- Any other pattern is too short

-- Main function to test firstAndThird
main :: IO ()
main = do
    print $ firstAndThird [10, 20, 30, 40]  -- Just (10, 30)
    print $ firstAndThird ["a", "b", "c"]   -- Just ("a", "c")
    print $ firstAndThird [1]              -- Nothing
    print $ firstAndThird [1, 2]           -- Nothing
    print $ firstAndThird ([] :: [Int])    -- Nothing
```

---

### 🔍 Explanation

* `firstAndThird (x:_:z:_)`: Match the first, skip the second (`_`), take the third, ignore the rest (`_`).
* Returns a `Maybe (a, a)` to handle cases where the list is too short.

---

### 🏃 How to Run:

1. Save this as `FirstAndThird.hs`
2. Compile and run:

```bash
ghc FirstAndThird.hs -o firstandthird
./firstandthird
```

---

### 🧾 Expected Output:

```
Just (10,30)
Just ("a","c")
Nothing
Nothing
Nothing
