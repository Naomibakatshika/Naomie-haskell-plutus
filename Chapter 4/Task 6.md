HC4T6 - Task 6: Identify List Contents Using Pattern Matching


### ✅ Haskell Code: `whatsInsideThisList`

```haskell
-- Function that returns a message based on the number of elements in a list
whatsInsideThisList :: [a] -> String
whatsInsideThisList []       = "The list is empty."
whatsInsideThisList [_]      = "The list has one element."
whatsInsideThisList [_, _]   = "The list has two elements."
whatsInsideThisList (_:_:_)  = "The list has multiple elements."

-- Main function to test whatsInsideThisList
main :: IO ()
main = do
    print $ whatsInsideThisList ([] :: [Int])
    print $ whatsInsideThisList [42]
    print $ whatsInsideThisList [1, 2]
    print $ whatsInsideThisList [1, 2, 3]
    print $ whatsInsideThisList "Hi"         -- List of characters
    print $ whatsInsideThisList "Hello"      -- Longer list
```

---

### 🏃 How to Run:

1. Save the file as `ListDescription.hs`
2. Compile and run it:

```bash
ghc ListDescription.hs -o listdesc
./listdesc
```

---

### 🧾 Example Output:

```
"The list is empty."
"The list has one element."
"The list has two elements."
"The list has multiple elements."
"The list has two elements."
"The list has multiple elements."
```
