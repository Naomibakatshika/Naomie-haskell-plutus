HC1T2 - Task 2: Pure Function Example

```haskell
-- Define a function to calculate the area of a circle
circleArea :: Floating a => a -> a
circleArea r = pi * r * r

-- Main function to test circleArea
main :: IO ()
main = do
    let radius = 5.0
    putStrLn $ "Given radius: " ++ show radius
    putStrLn $ "Area of circle: " ++ show (circleArea radius)
```

### Explanation:

* `circleArea` is a **pure function** — its output depends only on the input `r`, and it has no side effects.
* `Floating a => a -> a` allows `circleArea` to work with any floating-point number type, like `Float` or `Double`.
* `pi` is a predefined constant in Haskell from the `Prelude`.

### How to Run:

1. Save it as `Circle.hs`.
2. Compile and run:

   ```bash
   ghc Circle.hs -o circle
   ./circle
   ```


