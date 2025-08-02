HC4T1 - Task 1: Define a weatherReport Function

* Defines the function `weatherReport :: String -> String`
* Uses **pattern matching** to match specific weather conditions
* Returns a custom message for each case:

  * `"sunny"` → `"It's a bright and beautiful day!"`
  * `"rainy"` → `"Don't forget your umbrella!"`
  * `"cloudy"` → `"A bit gloomy, but no rain yet!"`
  * Any other string → `"Weather unknown"`
* Includes test calls in `main` for `"sunny"`, `"rainy"`, `"cloudy"`, and `"foggy"`

---

### ✅ Full Haskell Code

```haskell
-- Function that matches weather conditions and returns a description
weatherReport :: String -> String
weatherReport "sunny"  = "It's a bright and beautiful day!"
weatherReport "rainy"  = "Don't forget your umbrella!"
weatherReport "cloudy" = "A bit gloomy, but no rain yet!"
weatherReport _        = "Weather unknown"

-- Main function to test weatherReport
main :: IO ()
main = do
    putStrLn $ "weatherReport \"sunny\"  = " ++ weatherReport "sunny"
    putStrLn $ "weatherReport \"rainy\"  = " ++ weatherReport "rainy"
    putStrLn $ "weatherReport \"cloudy\" = " ++ weatherReport "cloudy"
    putStrLn $ "weatherReport \"foggy\"  = " ++ weatherReport "foggy"
```

---

### 🏃 How to Run:

1. Save the file as `WeatherReport.hs`
2. Compile and run:

```bash
ghc WeatherReport.hs -o weather
./weather
```

---

### 🧾 Expected Output:

```
weatherReport "sunny"  = It's a bright and beautiful day!
weatherReport "rainy"  = Don't forget your umbrella!
weatherReport "cloudy" = A bit gloomy, but no rain yet!
weatherReport "foggy"  = Weather unknown
```

