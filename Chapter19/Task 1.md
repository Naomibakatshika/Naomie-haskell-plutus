HC19T1: Applicative Instance for Pair

```haskell
{-# LANGUAGE InstanceSigs #-}

-- Define the Pair data type
data Pair a = Pair a a deriving (Show, Eq)

-- Functor instance for Pair
instance Functor Pair where
  fmap :: (a -> b) -> Pair a -> Pair b
  fmap f (Pair x y) = Pair (f x) (f y)

-- Applicative instance for Pair
instance Applicative Pair where
  pure :: a -> Pair a
  pure x = Pair x x

  (<*>) :: Pair (a -> b) -> Pair a -> Pair b
  (Pair f g) <*> (Pair x y) = Pair (f x) (g y)

-- Example usage
main :: IO ()
main = do
  let p1 = Pair 1 2
      p2 = Pair (+1) (*2)
      result = p2 <*> p1
  putStrLn $ "Applying Pair of functions to Pair of values: " ++ show result
```

### Explanation:

* **`Pair a`** is a simple container that holds two values of type `a`.
* **`Functor` instance** applies a function to both elements of the pair.
* **`Applicative` instance**:

  * `pure` creates a pair where both values are the same.
  * `<*>` applies the first function to the first value, and the second function to the second value.

### Example Output:

```
Applying Pair of functions to Pair of values: Pair 2 4
```
