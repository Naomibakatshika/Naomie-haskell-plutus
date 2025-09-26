HC20T8: Parser Monad for Simple Expressions

We'll define a custom `Parser` type and implement the necessary instances, then build parsers for numbers and expressions.

```haskell
{-# LANGUAGE ApplicativeDo #-}

import Control.Applicative
import Data.Char (isDigit, digitToInt)

-- Basic Parser type
newtype Parser a = Parser { runParser :: String -> Maybe (a, String) }

-- Functor instance
instance Functor Parser where
  fmap f (Parser p) = Parser $ \input -> do
    (x, rest) <- p input
    return (f x, rest)

-- Applicative instance
instance Applicative Parser where
  pure x = Parser $ \input -> Just (x, input)
  (Parser pf) <*> (Parser pa) = Parser $ \input -> do
    (f, rest1) <- pf input
    (a, rest2) <- pa rest1
    return (f a, rest2)

-- Alternative instance (for choice and failure)
instance Alternative Parser where
  empty = Parser $ const Nothing
  (Parser p1) <|> (Parser p2) = Parser $ \input ->
    p1 input <|> p2 input

-- Monad instance
instance Monad Parser where
  (Parser pa) >>= f = Parser $ \input -> do
    (a, rest1) <- pa input
    runParser (f a) rest1

-- Consume a single character if it satisfies a predicate
satisfy :: (Char -> Bool) -> Parser Char
satisfy pred = Parser $ \case
  (x:xs) | pred x -> Just (x, xs)
  _ -> Nothing

-- Parse a specific character
char :: Char -> Parser Char
char c = satisfy (== c)

-- Parse one or more digits and convert to Int
number :: Parser Int
number = do
  digits <- some (satisfy isDigit)
  return $ foldl (\acc d -> acc * 10 + digitToInt d) 0 digits

-- Parse whitespace (zero or more spaces)
spaces :: Parser ()
spaces = many (satisfy (== ' ')) *> pure ()

-- Parse an expression with addition and multiplication

-- Forward declaration to handle recursion
expr :: Parser Int
expr = do
  t <- term
  expr' t
  where
    expr' acc = (do
      spaces
      char '+'
      spaces
      t <- term
      expr' (acc + t)) <|> pure acc

term :: Parser Int
term = do
  f <- factor
  term' f
  where
    term' acc = (do
      spaces
      char '*'
      spaces
      f <- factor
      term' (acc * f)) <|> pure acc

factor :: Parser Int
factor = number <|> do
  spaces
  char '('
  spaces
  e <- expr
  spaces
  char ')'
  spaces
  return e

-- Helper function to run parser on input and check for full consumption
parseExpr :: String -> Maybe Int
parseExpr input = case runParser expr input of
  Just (result, "") -> Just result
  _ -> Nothing

-- Test main
main :: IO ()
main = do
  let tests = ["2+3*4", "(2+3)*4", "10 + 20 * (3 + 4)", "42", "1 + 2 + 3", "5 * (6 + 7)"]
  mapM_ (\t -> putStrLn $ t ++ " = " ++ show (parseExpr t)) tests
```

### Explanation:

* `Parser` is a simple parser combinator type.
* We define basic parsers like `char`, `number`, and `spaces`.
* Expressions are parsed with correct precedence: `term` handles multiplication, `expr` handles addition.
* `factor` parses either a number or a parenthesized expression.
* `parseExpr` runs the parser and ensures the whole input is consumed.
* `main` tests various expressions and prints the results.
