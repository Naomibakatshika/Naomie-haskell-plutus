HC18T7: fmapTuple Function

```haskell
-- fmapTuple applies a function to the second element of a tuple using Functor instance for (,) a
fmapTuple :: Functor ((,) a) => (b -> c) -> (a, b) -> (a, c)
fmapTuple = fmap

-- Example usage
main :: IO ()
main = do
  let tuple1 = ("age", 30)
      tuple2 = ("score", 85)
      result1 = fmapTuple (+5) tuple1
      result2 = fmapTuple (*2) tuple2
  putStrLn $ "Original: " ++ show tuple1 ++ ", after fmapTuple (+5): " ++ show result1
  putStrLn $ "Original: " ++ show tuple2 ++ ", after fmapTuple (*2): " ++ show result2
```

---

### Output:

```
Original: ("age",30), after fmapTuple (+5): ("age",35)
Original: ("score",85), after fmapTuple (*2): ("score",170)
```

Explanation:

* The tuple `(a, b)` is an instance of `Functor` in Haskell where `fmap` applies the function to the **second** element of the tuple, leaving the first element unchanged.
* So `fmapTuple = fmap` uses that directly.
