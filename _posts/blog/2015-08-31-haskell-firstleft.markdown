---
layout: post
title: "Haskell: firstLeft"
date: 2015-08-31
author: Fil
categories:
- blog
- haskell
img: first-left.jpg
thumb: first-left.jpg
---
I found myself recently reaching for a firstLeft function. The idea was that using `Either` to model failure/success of a function, you either want to get the first error back (`Left`) or all the results (`Right`).

```haskell
firstLeft :: [Either a b] -> Either a [b]

Prelude> firstLeft [Right 1, Right 2, Right 3]
Right [1,2,3]
Prelude> firstLeft [Right 1, Right 2, Right 3, Left "gah!"]
Left "gah!"
Prelude> firstLeft [Right 1, Left "ooh!", Right 2, Right 3, Left "gah!"]
Left "ooh!"
```

[Benl](http://benl.ouroborus.net/) immediately pointed out to me, this is in fact `sequence`:

```haskell
sequence :: (Monad m, Traversable t) => t (m a) -> m (t a)

Prelude> sequence [Right 1, Right 2, Right 3]
Right [1,2,3]
Prelude> sequence [Right 1, Right 2, Right 3, Left "gah!"]
Left "gah!"
Prelude> sequence [Right 1, Left "ooh!", Right 2, Right 3, Left "gah!"]
Left "ooh!"
```

If this is not immediately obvious as to why these two are equivalent, see below. Type variables can effectively be curried:

```haskell
sequence   :: (Monad m, Traversable t) => t (m a) -> m (t a)
-- m = Either a:
sequence'  :: (Traversable t) => t ((Either a) b) -> (Either a) (t b)
-- t = []:
sequence'' :: [Either a b] -> Either a [b]
firstLeft  :: [Either a b] -> Either a [b]
```

The term `sequence` seems a bit confusing, I generally thought of this as a kind of `collect` operation. Interestingly, the documentation for `sequence` refers to this term too in describing it:

> Evaluate each [..] action in the structure [..] and *collect* the results.
