HC2T6 - Task 6: Understanding Int vs Integer

* Defines:

  * `smallNumber :: Int` with the value `262`
  * `bigNumber :: Integer` with the value `2127`
* Attempts to compute `2^64 :: Int`, which **will overflow** on most systems because `Int` is typically 64-bit and `2^64` exceeds the max `Int`.

⚠️ **Note:** In a compiled Haskell program, attempting `2^64 :: Int` will likely result in an **overflow** and return an incorrect result. `Integer` can handle large values correctly.

---

### ✅ Full Haskell Code

```haskell
-- Define smallNumber as Int
smallNumber :: Int
smallNumber = 262

-- Define bigNumber as Integer
bigNumber :: Integer
bigNumber = 2127

main :: IO ()
main = do
    putStrLn $ "smallNumber (Int): " ++ show smallNumber
    putStrLn $ "bigNumber (Integer): " ++ show bigNumber

    -- Evaluate 2^64 as Int (will likely overflow)
    let powerInt :: Int
        powerInt = 2 ^ 64

    putStrLn $ "2^64 :: Int (may overflow): " ++ show powerInt

    -- Evaluate 2^64 as Integer (correct)
    let powerInteger :: Integer
        powerInteger = 2 ^ 64

    putStrLn $ "2^64 :: Integer (correct): " ++ show powerInteger
```

---

### 🏃 How to Run:

1. Save the file as `OverflowTest.hs`
2. Compile and run:

```bash
ghc OverflowTest.hs -o overflowtest
./overflowtest
```

---

### 🧪 What Happens in GHCi?

If you try this in GHCi:

```haskell
:t 2^64
-- Default is Integer unless specified

2^64 :: Int
-- Likely returns: 0 or a negative number (due to overflow)

2^64 :: Integer
-- Returns: 18446744073709551616 (correct value)
```

---

### ✅ Recommended Takeaway:

Use `Integer` when working with large numbers to avoid overflow, as `Int` is bounded (typically `-2^63` to `2^63 - 1` on 64-bit systems).

