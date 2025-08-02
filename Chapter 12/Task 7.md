HC12T7: Calculate Circle Area

```haskell
-- Function to calculate the area of a circle
calculateCircleArea :: Floating a => a -> a
calculateCircleArea radius = pi * radius * radius

-- Main function to demonstrate usage
main :: IO ()
main = do
    putStrLn "Enter the radius of the circle:"
    input <- getLine
    let radius = read input :: Double
    let area = calculateCircleArea radius
    putStrLn $ "The area of the circle is: " ++ show area
```

### How It Works:

* The user is prompted to enter a radius.
* The input is read as a `Double`.
* `calculateCircleArea` computes the area using the formula: **π × r²**.
* The result is printed.

### Example:

```
Enter the radius of the circle:
3
The area of the circle is: 28.274333882308138
```
