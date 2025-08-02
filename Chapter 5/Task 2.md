HC5T2: Filtering Odd Numbers

---

### ✅ Haskell Code: Filter Odd Numbers

```haskell
-- Use filter to extract all odd numbers from 1 to 30
oddNumbers :: [Int]
oddNumbers = filter odd [1..30]

-- Main function to print the result
main :: IO ()
main = do
    putStrLn "Odd numbers from 1 to 30:"
    print oddNumbers
```

---

### 🏃 How to Run:

1. Save this code as `FilterOdd.hs`
2. Compile and run:

```bash
ghc FilterOdd.hs -o filterodd
./filterodd
```

---

### 🧾 Expected Output:

```
Odd numbers from 1 to 30:
[1,3,5,7,9,11,13,15,17,19,21,23,25,27,29]
```
