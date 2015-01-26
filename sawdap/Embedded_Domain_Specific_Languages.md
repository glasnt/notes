Anthony Sloane, Macq. U 
@inkytonik

General Purpose Language - GPL e.g. fortran
Domain Specific Language - DSL e.g. HTML
 - not always executable
 - abstractions may not be GPL compatable

Structred Data Processing e.g. RDBS w/SQL <- DSL

Hadoop API for MapReduce Domain 
 - hadoop.apache.org - paralell processing
 - hive.apache.org - Hive DSL - SQL-ish -> hadoop

External DSL   - DSL compiler (proper)   -> target program
vs
Internal DSL   - Host Compler (e.g. GHC) -> target program
(embedded, shallow)

EDSL ~= library 

A more holistic approach to an API/Library


Kiama.googlecode.com
 - by Macq. U, in Scala (similar to Stratego)
 - symbols are their own implementations
 - e.g. `+` != arithmetic addition

Deep EDSL
 - Host program -> Host compiler -> DSL Compiler -> Problem Config -> Target Program
 - multi-step
 - some context known to compiler

Scoobi (GH:NICTA/scoobi)
 - 500-100 LOC Java -> 7 lines of scoobi
 - uses kiama for optimization to hadoop jobs

Hadoop based DSL (Abstract) - generic primatives
vs
Concrete DSL - domain datatypes

Chisel.eecs.berkeley.edu
 - deep embedding of hardware spec

stanford-ppl.github.io/Delite
 - EPFL
 - supercharged
 - multiview, traversals
 - multi lang

Domain experts can code, machines can think about complexity
 - e.g. OptiMesh (shallow water simulator), OptiGraph (google page rank), OptiQL (SQL)
 -> exponentially aster on multi code

convenience of GPL with optimizations of underlying grunt

Programmers do the DSL
Domain Experts take DSL for awesomeness
 -> abstract out the computer Science

Audience comments: 
 - Basic DSL (joke DSL)
 - Haskell already exposes some optimizations
 - not a lot of commerial applications, very research based & new
  - counter argument - Puppet, Chef = EDSL



