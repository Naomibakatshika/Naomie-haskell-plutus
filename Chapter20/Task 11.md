HC20T11: randomWalk with State Monad

```haskell
import Control.Monad.State
import System.Random

-- Define the position type
type Position = (Int, Int)

-- Possible moves: up, down, left, right
moves :: [Position]
moves = [(0,1), (0,-1), (-1,0), (1,0)]

-- Randomly pick a move from moves
randomMove :: State StdGen Position
randomMove = do
  gen <- get
  let (idx, gen') = randomR (0, length moves - 1) gen
  put gen'
  return (moves !! idx)

-- Perform one step of the random walk from a given position
step :: Position -> State StdGen Position
step (x,y) = do
  (dx, dy) <- randomMove
  return (x + dx, y + dy)

-- Perform n steps of the random walk, starting from startPos
randomWalk :: Int -> Position -> State StdGen [Position]
randomWalk 0 pos = return [pos]
randomWalk n pos = do
  nextPos <- step pos
  rest <- randomWalk (n-1) nextPos
  return (pos : rest)

-- Run the random walk with a given seed and steps
main :: IO ()
main = do
  let stepsCount = 10
  gen <- getStdGen
  let path = evalState (randomWalk stepsCount (0,0)) gen
  putStrLn "Random walk path:"
  mapM_ print path
```

### How it works:

* `randomMove` picks a random direction.
* `step` applies that move to the current position.
* `randomWalk` recursively performs `n` steps and accumulates the positions.
* `main` runs the random walk starting from `(0,0)` for 10 steps and prints the path.
