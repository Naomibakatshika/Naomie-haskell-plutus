HC19T10: combineResults for Either

```haskell
-- combineResults.hs
-- Demonstrates combining two Either values applicatively

combineResults :: Either String Int -> Either String Int -> Either String Int
combineResults = liftA2 (+)

main :: IO ()
main = do
  let r1 = Right 10
  let r2 = Right 5
  let r3 = Left "First error"
  let r4 = Left "Second error"

  print $ combineResults r1 r2     -- Right 15
  print $ combineResults r1 r3     -- Left "First error"
  print $ combineResults r3 r4     -- Left "First error"
```

---

### Explanation:

* `liftA2 (+)` lifts the `(+)` function into the `Either` context.
* If both values are `Right`, they are added.
* If either is `Left`, the first `Left` encountered is returned.

---

### Output:

```haskell
Right 15
Left "First error"
Left "First error"
```

---

You can run this with:

```bash
runhaskell combineResults.hs
```
