HC1T5 - Task 5: Laziness in Haskell

* Defines `infiniteNumbers` as an **infinite list** of numbers starting from 1.
* Defines `firstN` to extract the first `n` elements using `take`.
* Tests it with a few sample values.

---

### ✅ Full Haskell Code

```haskell
-- Define an infinite list of numbers starting from 1
infiniteNumbers :: [Integer]
infiniteNumbers = [1..]

-- Function to get the first n numbers from the infinite list
firstN :: Int -> [Integer]
firstN n = take n infiniteNumbers

-- Main function to test firstN
main :: IO ()
main = do
    putStrLn "First 10 numbers from the infinite list:"
    print (firstN 10)

    putStrLn "\nFirst 5 numbers from the infinite list:"
    print (firstN 5)

    putStrLn "\nFirst 20 numbers from the infinite list:"
    print (firstN 20)
```

---

### 🏃 How to Run:

1. Save it as `InfiniteList.hs`
2. Compile and run:

```bash
ghc InfiniteList.hs -o infinite
./infinite
```

---

### 🧾 Expected Output:

```
First 10 numbers from the infinite list:
[1,2,3,4,5,6,7,8,9,10]

First 5 numbers from the infinite list:
[1,2,3,4,5]

First 20 numbers from the infinite list:
[1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20]
```

