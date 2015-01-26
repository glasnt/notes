Robert Clifton-Everest, UNSW

GPUS
 - ++ computing power
 - -- memory
 - minimal instruction set
 -> haskell based EDSL
  - looks like haskell, but C code
  - zipWith, fold

scalar = 0 dimensional array
vector = 1 dimensional array
array  = n dimensional array

carenorhabditis elegans - worm
 - waterflow tests
 - glowing neurons (generically modified)

Video processing problems
 - memory issues - Problem #1 (large sets, array)
 - nested parallelism - Problem #2  (3d)

Streams! Sequencing!


 Exp (int, word32, double, float, bool)
 ->
 Acc (array)
 ->
 Seq (array)  <- neww incorporation

 - big game of scissors paper rock in interoperability

`streamIn :: Arrays A => [a] -> Seq [a]`

able to apply things like an array - But How? 
 - can't do it sequentially (problem #2)
 - flatten an array to a vector! -> `Vector'` (problem #1)

folds aren't chunkable in it's normal form 
 - do fancy things to make it work  - reduce? re-reduce? (couchdb)

no recursion, only simple loops 
 - how to pick good chunk size

Banana fold paper
 
