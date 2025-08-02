HC9T6: Recursive Data Type for Tweets

* `content` as `String`
* `likes` as an `Int`
* `comments` as a list of other `Tweet`s (recursive)

---

### ✅ Haskell Code

```haskell
-- Define the recursive Tweet data type
data Tweet = Tweet
  { content  :: String
  , likes    :: Int
  , comments :: [Tweet]
  } deriving (Show)

-- Example tweets
comment1 :: Tweet
comment1 = Tweet { content = "Nice post!", likes = 3, comments = [] }

comment2 :: Tweet
comment2 = Tweet { content = "Thanks for sharing!", likes = 5, comments = [] }

mainTweet :: Tweet
mainTweet = Tweet
  { content = "Learning Haskell is fun!"
  , likes = 10
  , comments = [comment1, comment2]
  }

-- Main function to print the main tweet
main :: IO ()
main = print mainTweet
```

---

### 🧪 Sample Output

```
Tweet {content = "Learning Haskell is fun!", likes = 10, comments = [Tweet {content = "Nice post!", likes = 3, comments = []},Tweet {content = "Thanks for sharing!", likes = 5, comments = []}]}
```
