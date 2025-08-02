HC7T4: Custom Type with Show and Read

---

### ✅ Haskell Code: `Shape` with `Show` and `Read`

```haskell
-- Define the Shape data type
data Shape = Circle Double | Rectangle Double Double

-- Implement Show instance
instance Show Shape where
    show (Circle r) = "Circle " ++ show r
    show (Rectangle w h) = "Rectangle " ++ show w ++ " " ++ show h

-- Implement Read instance
instance Read Shape where
    readsPrec _ input = 
        case words input of
            ("Circle":r:_) ->
                [(Circle (read r), "")]
            ("Rectangle":w:h:_) ->
                [(Rectangle (read w) (read h), "")]
            _ -> []

-- Main function to test Show and Read
main :: IO ()
main = do
    let shape1 = Circle 5.0
    let shape2 = Rectangle 3.0 4.0

    -- Test Show
    putStrLn $ "Show Circle: " ++ show shape1
    putStrLn $ "Show Rectangle: " ++ show shape2

    -- Test Read
    let readShape1 = read "Circle 7.5" :: Shape
    let readShape2 = read "Rectangle 6.0 8.0" :: Shape

    putStrLn $ "Read Circle: " ++ show readShape1
    putStrLn $ "Read Rectangle: " ++ show readShape2
```

---

### 🏃 How to Run

1. Save the code in a file called `Shape.hs`
2. Compile and run:

```bash
ghc Shape.hs -o shape
./shape
```

---

### 🧾 Expected Output

```
Show Circle: Circle 5.0
Show Rectangle: Rectangle 3.0 4.0
Read Circle: Circle 7.5
Read Rectangle: Rectangle 6.0 8.0
```
