Ben Lippmeier

"Big Data" = exceeds local memory, or Excel
 - out of core processing, streaming

example - 100+ GB ascii file cannot be loaded into memory

segmented fold - sum group
 
banish arrays when working with big data 
 - medium data (?)
 - string vs array


(Attempt at replicating diagrams in ascii follow)


`*|` source/Wire - always readable until EOF

`o|` sink - always writable, cannot block  - "there is no try"
 - `mapi :: (a -> b) -> I a -> I b`
 - `mapo :: (a -> b) -> O b -> O a` 
 - polarity in functions, pully vs pushy

duplication - pull from left has to be same as right - buffer = bad (computational limitations)

`dup_o :: I a -> O a -> I a` - polarity allows no buggering 

      *|
    dup_io
    */  o\

folds segmentation, segmented sum

    x = 2 1 0 3 0 4
    y = 4 2 5 1 2 3 4 1 3 1

    -> 4 2 | 5 | |  1 2 3 | | 4 1 3 1
    (index in x segments array y, tuples summed)
  
    => output = [ 6 5 0 6 0 9 ]
 

Input diagrams for dup_io


    fold *\ /*     |  *\ /o  OK
           |*      |    |o 

                 ----------

    invalid *\ /o  |  o\ /o  buffer
              |*   |    |o 


invalid - because can't have a source to source. Buffer because can't have all sinks


Validation of modality
 - create library of only valid combinations
 - combinations that result in buffers or invalid not implemented
 -> guarenteed streaming of arbitary IO

(named combinations -> function names)

Draings - Source into Sink 

Pipes can't prevent buffering. No continuations
 - "Fusion"


Sink - push - eject
Source - eat - eject <- "Taps"?

Storm - Java
