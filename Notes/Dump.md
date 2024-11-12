FO == Aperiodic Monoids == Star free Regular == Counter Free Automata
- Star-Free regular E : epsilon | A | not E | E + E |Empty | EE
  - Sigma * valid because it is not of emtpy
  - a* is valid because its not of union of Sigma*b Sigma*

Star Free -> Aperiodic
- Negation is for free
- Or is also possible because boolean combinatoin
- Single letter accepting is possible because let monoid be {0, 1, a} epsilon goes to 1, a goes to a, everythign else goes to 0 and a*a = 0
- Emtpty Language is also accepted
- So is just eh empty string
- Concatenation words because given an L1 that goes to M1, and L2 that goes to L2. Consider a word w x^2n y, we split the word in half where first half is accepted by L1 and tehe second half is accepted by L2 and extending it in one of the half must work.,

SF -> FO
- Epsilong words
- single letter words forall x, y (x = y /\ a(x))
- Negation trivially words
- or words
- empty langauge words
- FOr concatenation : L - epsilong is a lanuage of some sentence phi. for L1 and L2, exists y relativize<y(phi1) /\ reltivize>y(phi2) and take special care about epsilong cases

FO -> Aperiodic
- EF games over word models, lets fucking gooo.
- We already place free variables on the two words 
- Give a quantifier depth k, claim that that is aperiodic repeat thingy m = 2^k, take teh word x w^m y and x w^(m+1) y 
  - Play the even waaala EF game basically.

Aperiodic -> SF
- Given a monoid M, an ideal is a set such that MIM = I (A singleton 0 if it exists forms an ideal itself)
- I1 and I2 are non-trivial, then I1 intersection I2 is an ideal.
  - There intersection is also no trivial then i1*i2 is in both i1 and i2
- Finite Monoid can be thought of as weird partial orders where if xy gives somethign, then xy is below x and y, then an ideal would be a downward closure.
- We can also order ideals using inclusion, but there is minimal element, which is the intersection of all the ideal which will definitely be empty.