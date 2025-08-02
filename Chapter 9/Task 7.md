HC9T7: Engagement Function for Tweets

---

### ✅ Haskell Code

```haskell
-- Define the recursive Tweet data type
data Tweet = Tweet
  { content  :: String
  , likes    :: Int
  , comments :: [Tweet]
  } deriving (Show)

-- Calculate total engagement (likes + engagement of comments)
engagement :: Tweet -> Int
engagement (Tweet _ likes comments) =
  likes + sum (map engagement comments)

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

-- Main function to print the total engagement
main :: IO ()
main = do
  putStrLn $ "Total engagement: " ++ show (engagement mainTweet)
```

---

### 🧪 Sample Output

```
Total engagement: 18
```
