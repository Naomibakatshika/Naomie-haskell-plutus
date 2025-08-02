HC3T3 - Task 3: Convert an RGB color to a hex string using let bindings

* Defines the function `rgbToHex :: (Int, Int, Int) -> String`
* Uses `let` bindings to format each RGB component as a **2-digit hexadecimal string**
* Concatenates them into a final hex color code (e.g. `FF007F`)

---

### ✅ Full Haskell Code

```haskell
import Text.Printf (printf)

-- Function to convert RGB (0-255) to a 6-character hexadecimal string
rgbToHex :: (Int, Int, Int) -> String
rgbToHex (r, g, b) =
    let rHex = printf "%02X" r
        gHex = printf "%02X" g
        bHex = printf "%02X" b
    in rHex ++ gHex ++ bHex

-- Main function to test rgbToHex
main :: IO ()
main = do
    putStrLn $ "rgbToHex (255, 0, 127) = " ++ rgbToHex (255, 0, 127)
    putStrLn $ "rgbToHex (0, 255, 64)  = " ++ rgbToHex (0, 255, 64)
```

---

### 🏃 How to Run:

1. Save the file as `RgbToHex.hs`
2. Compile and run:

```bash
ghc RgbToHex.hs -o rgbhex
./rgbhex
```

---

### 🧾 Expected Output:

```
rgbToHex (255, 0, 127) = FF007F
rgbToHex (0, 255, 64)  = 00FF40
```

---
