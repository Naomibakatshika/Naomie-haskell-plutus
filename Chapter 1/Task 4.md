HC1T4 - Task 4: Composing a Function to Process Player Data
* Defines the following functions:

  * `extractPlayers` — extracts player names from a list of `(name, score)` tuples.
  * `sortByScore` — sorts the list in descending order of scores.
  * `topThree` — returns the top three players.
  * `getTopThreePlayers` — uses function composition to combine the above.

```haskell
import Data.List (sortBy)
import Data.Ord (comparing)

-- Type alias for clarity
type Player = (String, Int)

-- Extract player names
extractPlayers :: [Player] -> [String]
extractPlayers players = map fst players

-- Sort players by score in descending order
sortByScore :: [Player] -> [Player]
sortByScore = sortBy (flip (comparing snd))

-- Get top three players
topThree :: [Player] -> [Player]
topThree = take 3

-- Compose functions to get top three player names
getTopThreePlayers :: [Player] -> [String]
getTopThreePlayers = extractPlayers . topThree . sortByScore

-- Main function to test
main :: IO ()
main = do
    let players = [("Alice", 85), ("Bob", 92), ("Charlie", 78), ("Diana", 95), ("Eve", 88)]
    putStrLn "All players and scores:"
    print players

    putStrLn "\nTop 3 player names:"
    print (getTopThreePlayers players)
```

---

### Output (when run):

```
All players and scores:
[("Alice",85),("Bob",92),("Charlie",78),("Diana",95),("Eve",88)]

Top 3 player names:
["Diana","Bob","Eve"]
```

### How to Run:

1. Save the code in a file named `TopPlayers.hs`.
2. Compile and run it using:

```bash
ghc TopPlayers.hs -o topplayers
./topplayers
```


