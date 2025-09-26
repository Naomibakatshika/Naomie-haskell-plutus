HC20T10: Nested StateT and MaybeT Transformer

```haskell
{-# LANGUAGE FlexibleContexts #-}

import Control.Monad.Trans.State
import Control.Monad.Trans.Maybe
import Control.Monad.Trans.Class (lift)
import Control.Monad.IO.Class (liftIO)
import Control.Monad (when)

-- Type alias for the combined monad stack:
-- StateT Int (MaybeT IO) a
type MyMonad = StateT Int (MaybeT IO)

-- A sample computation that increments state and fails if state > 5
incrementAndCheck :: MyMonad ()
incrementAndCheck = do
  st <- get
  let newSt = st + 1
  put newSt
  lift . MaybeT $ do
    liftIO $ putStrLn $ "Current state: " ++ show newSt
    -- fail when state > 5
    return $ if newSt > 5 then Nothing else Just ()

-- Run the computation until failure
runComputation :: Int -> IO ()
runComputation initialState = do
  result <- runMaybeT $ runStateT (loop) initialState
  case result of
    Nothing -> putStrLn "Computation failed (state > 5)."
    Just ((), finalState) -> putStrLn $ "Finished successfully with state: " ++ show finalState
  where
    loop :: MyMonad ()
    loop = do
      incrementAndCheck
      loop -- recurse until failure

main :: IO ()
main = runComputation 0
```

### Explanation:

* `MyMonad` combines `StateT Int` on top of `MaybeT IO`.
* `incrementAndCheck` increments the state and uses `MaybeT` to fail when the state exceeds 5.
* `runComputation` runs the loop starting from a given initial state until the failure condition triggers.
* The program prints the state at each step, then reports failure or success.

Run this code to see the output:

```
Current state: 1
Current state: 2
Current state: 3
Current state: 4
Current state: 5
Current state: 6
Computation failed (state > 5).
```
