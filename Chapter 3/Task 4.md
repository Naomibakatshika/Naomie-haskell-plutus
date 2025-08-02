HC3T4 - Task 4: Calculate the area of a triangle using Heron's formula

* Defines `triangleArea :: Float -> Float -> Float -> Float`
* Uses `let` to compute the semi-perimeter `s`
* Applies **Heron’s formula**:

  $$
  \text{area} = \sqrt{s(s - a)(s - b)(s - c)}
  $$
* Tests it with `triangleArea 3 4 5` and `triangleArea 7 8 9`

---

### ✅ Full Haskell Code

```haskell
-- Function to calculate the area of a triangle using Heron's formula
triangleArea :: Float -> Float -> Float -> Float
triangleArea a b c =
    let s = (a + b + c) / 2
    in sqrt (s * (s - a) * (s - b) * (s - c))

-- Main function to test triangleArea
main :: IO ()
main = do
    putStrLn $ "triangleArea 3 4 5 = " ++ show (triangleArea 3 4 5)
    putStrLn $ "triangleArea 7 8 9 = " ++ show (triangleArea 7 8 9)
```

---

### 🏃 How to Run:

1. Save the file as `TriangleArea.hs`
2. Compile and run:

```bash
ghc TriangleArea.hs -o trianglearea
./trianglearea
```

---

### 🧾 Expected Output:

```
triangleArea 3 4 5 = 6.0
triangleArea 7 8 9 = 26.832815
```

---

