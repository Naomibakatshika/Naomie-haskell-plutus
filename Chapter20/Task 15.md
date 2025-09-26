HC20T15: treeSum with Custom Monad

1. A custom binary tree type.
2. A custom monad (`SumMonad`) to compute the sum while encapsulating the state of summation.
3. A `treeSum` function that computes the sum of elements in the tree using this custom monad.

---

### ✅ Full Haskell Code:

```haskell
{-# LANGUAGE InstanceSigs #-}

-- Define the binary tree
data Tree a = Leaf a | Node (Tree a) (Tree a)
  deriving Show

-- Define the custom monad type
newtype SumMonad a = SumMonad { runSum :: Int -> (a, Int) }

-- Functor instance
instance Functor SumMonad where
  fmap f (SumMonad g) = SumMonad $ \s ->
    let (a, s') = g(s)
    in (f a, s')

-- Applicative instance
instance Applicative SumMonad where
  pure x = SumMonad $ \s -> (x, s)
  SumMonad f <*> SumMonad x = SumMonad $ \s ->
    let (g, s')  = f s
        (y, s'') = x s'
    in (g y, s'')

-- Monad instance
instance Monad SumMonad where
  return = pure
  (SumMonad x) >>= f = SumMonad $ \s ->
    let (a, s') = x s
        SumMonad y = f a
    in y s'

-- Helper to add a value to the sum state
addValue :: Int -> SumMonad ()
addValue x = SumMonad $ \s -> ((), s + x)

-- treeSum function using the custom monad
treeSum :: Tree Int -> SumMonad ()
treeSum (Leaf x) = addValue x
treeSum (Node l r) = do
  treeSum l
  treeSum r

-- Run treeSum and extract the final sum
runTreeSum :: Tree Int -> Int
runTreeSum t = snd $ runSum (treeSum t) 0

-- Example tree
exampleTree :: Tree Int
exampleTree = Node (Leaf 3) (Node (Leaf 4) (Leaf 5))

-- Main function to show the result
main :: IO ()
main = do
  let total = runTreeSum exampleTree
  putStrLn $ "Sum of elements in tree: " ++ show total
```

---

### 💡 Output when run:

```
Sum of elements in tree: 12
```

---

### ✅ Explanation:

* `Tree` is a simple binary tree with `Leaf` and `Node`.
* `SumMonad` is a custom state monad that carries an `Int` sum.
* `treeSum` walks the tree and accumulates values using the custom monad.
* `runTreeSum` kicks off the computation with initial sum `0`.
