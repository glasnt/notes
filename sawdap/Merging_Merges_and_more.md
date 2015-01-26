Amos Robinson, PHD @ UNSW, @MosRobinson

(a discussion on theory)

Tables on disk, too big for memory
 - ordered by an ID, important for math
 - e.g.  business accounts w/money
 -> sum, group, filter operation to find a thing w/A & B, then find another thing with C
  - want a way to have O(1) without buffering


Query plan: 

    A   B   C  
    |   |   |
    merge   |  
      |     |
       merge
       group
       filter 


Can combinators be merged? 

    if     | A >  B  A = B    A < B  } K
    more.. | A ∧ ¬B  A ∧ B   ¬A ∧ B 
    output |    (Ak, Av, Bv)
             A -> *B         B -> *A
   
    Plug Merge - addition of sparce vectors
    Zip  A ∧ B -> (A,b)
    Append, pull from sides

"Fusion" of combinators


Legend: `∧` and , `¬` not, * Lemma (eventual state)

            A < B   A = B   A > B
    B < C     A      AB       B
    B = C     A      ABC      BC
    B > C     AC     C        C


What can't we fuse? 

    A merge B  ⊕  A zip B (?)

"Traditional Ternary Logic" - True, False, Maybe
 ( Game Theory ) First order logic

Streamit Language
