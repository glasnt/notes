Fraser Tweedale, Redhat

Haskell, yay! (and some other lang)

- automated counter example testing
- meaningful documentation

inline: `> prop composed`

import Test.Quickcheck

singleton, associative reflexivity -> math!

`ghci> quick check <method>`

identity testing

Arbitary a > instance

example output: "Failed! falsifiable: " followed by examples, corner cases

Manual fuzz sometimes required for domain specific cases, e.g. password hash similarities

Failure cases - hspec confirms failure cases works

Machine checkable, documentation good

Other modes: 
 
 exhaustive testing - test all the data - small check

 proof - no test data - theroum based, idris (.idr files) - won't compile if theorum falsifiable

shrink - reduce

gh/bitemyapp


