HC5T6: Function Composition

1. **Squares** each number in a list,
2. **Filters** only the even squares.

---

### ✅ Haskell Code: Function Composition for Squared Evens

```haskell
-- Function using function composition to square and filter even numbers
evenSquares :: [Int] -> [Int]
evenSquares = filter even . map (^2)

-- Main function to test evenSquares
main :: IO ()
main = do
    print $ evenSquares [1..10]     -- [4,16,36,64,100]
    print $ evenSquares [3,5,7]     -- []
    print $ evenSquares [2,4,6]     -- [4,16,36]
```

---

### 🏃 How to Run:

1. Save the file as `EvenSquares.hs`
2. Compile and run it:

```bash
ghc EvenSquares.hs -o evensquares
./evensquares
```

---

### 🧾 Expected Output:

```
[4,16,36,64,100]
[]
[4,16,36]
```
