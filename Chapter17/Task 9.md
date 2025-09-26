HC17T9: Config Data Type and Semigroup Instance

```haskell
import Data.Semigroup (Semigroup(..))

-- Define Config data type
data Config = Config
  { loggingLevel :: Int
  , timeout      :: Int
  , retries      :: Int
  } deriving (Show, Eq)

-- Semigroup instance combining Configs:
-- max loggingLevel, min timeout, max retries
instance Semigroup Config where
  (Config log1 to1 ret1) <> (Config log2 to2 ret2) =
    Config
      (max log1 log2)
      (min to1 to2)
      (max ret1 ret2)

-- Example usage
main :: IO ()
main = do
  let config1 = Config 2 30 3
      config2 = Config 4 20 1
      combinedConfig = config1 <> config2
  putStrLn $ "Combined Config: " ++ show combinedConfig
```

---

### Output:

```
Combined Config: Config {loggingLevel = 4, timeout = 20, retries = 3}
```
