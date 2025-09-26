HC17T10: Monoid Instance for Config

* `mempty` is a `Config` with:

  * lowest `loggingLevel` (let's say 0),
  * highest `timeout` (let's say a large number, e.g., `maxBound :: Int`),
  * lowest `retries` (0).

```haskell
import Data.Semigroup (Semigroup(..))
import Data.Monoid (Monoid(..))

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

-- Monoid instance with identity element
instance Monoid Config where
  mempty = Config
    { loggingLevel = 0
    , timeout      = maxBound  -- maximum Int value
    , retries      = 0
    }
  mappend = (<>)

-- Example usage
main :: IO ()
main = do
  let config1 = Config 2 30 3
      config2 = Config 4 20 1
      combined = config1 <> config2
      combinedWithMempty = combined <> mempty
  putStrLn $ "Combined Config: " ++ show combined
  putStrLn $ "Combined with mempty: " ++ show combinedWithMempty
  putStrLn $ "mempty Config: " ++ show (mempty :: Config)
```

---

### Output example:

```
Combined Config: Config {loggingLevel = 4, timeout = 20, retries = 3}
Combined with mempty: Config {loggingLevel = 4, timeout = 20, retries = 3}
mempty Config: Config {loggingLevel = 0, timeout = 9223372036854775807, retries = 0}
```
