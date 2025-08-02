HC7T3: Function Using Multiple Constraints

---

### ✅ Haskell Code: `compareValues`

```haskell
-- compareValues takes two values and returns the larger one
compareValues :: (Eq a, Ord a) => a -> a -> a
compareValues x y = if x >= y then x else y

-- Main function to test compareValues with different types
main :: IO ()
main = do
    -- Test with Int
    print (compareValues 5 10)      -- Output: 10

    -- Test with Char
    print (compareValues 'a' 'z')   -- Output: 'z'

    -- Test with Float
    print (compareValues 3.14 2.71) -- Output: 3.14

    -- Test with String
    print (compareValues "apple" "banana") -- Output: "banana"
```

---

### 🏃 How to Run

1. Save the code in a file called `CompareValues.hs`
2. Compile and run:

```bash
ghc CompareValues.hs -o comparevalues
./comparevalues
```

---

### 🧾 Expected Output

```
10
'z'
3.14
"banana"
```
