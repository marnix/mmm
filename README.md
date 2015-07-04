# mmm: Modular Metamath -or- Little Theories for Metamath


## Goal

The goal of this little project is to come up with some sort of module system
for Metamath.

There are two main drivers for this.

First, [`set.mm`](http://us.metamath.org/index.html#mmprog), the main database
of results proved in Metamath, is becoming really large: this text files is 24
MB at last count.  Some statistics for the 25-Jun-2015 version:

    450810 lines (24740442 characters) were read from "set.mm".
    The source has 123892 statements; 1957 are $a and 25097 are $p.

This gives some practical limitations.  For example,
[Github](http://github.com) does not show such large files, nor the commit
diffs in them.  And editors, verifiers, and other tools also occasionally run
into performance problems.

The second -- and for me more important -- problem is one of structure: how are
all these axioms and theorems interconnected? which axiom sets can be proved
from others?

This structure is implicitly present in `set.mm`, and its rendering on
[metamath.org](http://metamath.org), the [Metamath Proof Explorer Theorem
List](http://us.metamath.org/mpeuni/mmtheorems.html) makes this partially
explicit.

However, this structure can be made more explicit by allowing axiom sets to be
named, and storing proofs for different axiom sets in separate files.  (For
people who know [Ghilbert](http://ghilbert-app.appspot.com/), this corresponds
to `.ghi` and `.gh` files.)

Also, it would be helpful to be able to express things like "the positive real
numbers form a group", and then take any theorem that holds for a group, and
automatically have a theorem for positive real numbers.  Basically, this comes
down to a definition/abbreviation mechanism.

The result would be support for the 'little theories' approach to mathematics,
as described and advocated in, e.g., [Farmer, Guttman, and Thayer, "Little
Theories" (Springer-Verlag 1992), pp. 567-581 in Automated Deduction|CADE-11,
volume 607 of Lecture Notes in Computer
Science](http://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.36.8717).

