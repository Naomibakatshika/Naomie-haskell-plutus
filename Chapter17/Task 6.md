HC17T6: maxSeverity Function

```haskell
import Data.Monoid

-- Severity type definition
data Severity = Low | Medium | High | Critical
  deriving (Show, Eq, Ord)

-- Semigroup instance: max severity
instance Semigroup Severity where
  (<>) = max

-- Monoid instance: identity is Low
instance Monoid Severity where
  mempty = Low

-- Function to combine list of severities using mconcat
maxSeverity :: [Severity] -> Severity
maxSeverity = mconcat

-- Example usage
main :: IO ()
main = do
  let severities = [Low, Medium, High, Medium, Critical, Low]
      maxSev = maxSeverity severities
  putStrLn $ "Maximum severity: " ++ show maxSev
```

---

### Explanation:

* `mconcat` folds the list using the `Monoid` instance, which picks the max severity.
* `maxSeverity` simply calls `mconcat` on the input list.

---

### Sample output:

```
Maximum severity: Critical
```
