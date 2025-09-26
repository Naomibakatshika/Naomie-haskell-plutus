HC20T5: Reader Monad for Configurable Greeting

```haskell
import Control.Monad.Reader

-- Define a Config type with a greeting prefix and language info
data Config = Config
  { greetingPrefix :: String
  , language       :: String
  }

-- The greeting function reads from Config and returns a greeting message for a given name
greetUser :: String -> Reader Config String
greetUser name = do
  cfg <- ask
  let prefix = greetingPrefix cfg
      lang = language cfg
  return $ prefix ++ ", " ++ name ++ "! Welcome (" ++ lang ++ ")."

-- Run greeting with a sample config and user name
main :: IO ()
main = do
  let config = Config { greetingPrefix = "Hello", language = "English" }
      greetingMessage = runReader (greetUser "Alice") config
  putStrLn greetingMessage
```

---

### Explanation:

* `Config` stores configuration for greetings.
* `greetUser` uses `Reader Config` to access the configuration and generate a personalized message.
* `main` runs the Reader monad with a concrete config and prints the result.

---

Running this will output:

```
Hello, Alice! Welcome (English).
```
