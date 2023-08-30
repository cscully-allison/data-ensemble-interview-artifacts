

Legend
======

## Prompts Overview Timeline

A. Describe Data Ensemble - the first question
B. Important Parts - if asked as the second question
C. Draw Data Ensemble - the initial drawing
D. Tasks
  i. Scaling
  ii. Architecture
  iii. Inclusive Time
E. Other Discussion


## Data


#### Parts

- Perf - Performance Data Frame
- Meta - Metadata Frame
- Stats - Stats Frame
- Tree - Call tree / Call graph
- Links - Relations among parts

#### Modifiers

- Explicit: They explicitly state the [EnsembleAPI] name for it
- Implicit: They imply/allude to data contained in that part of the
  [EnsembleAPI]
If they start implicit and then it becomes explicit, I just mark explicit.

Examples:

Iif someone mentions different compilers without mentioning metadata, I label it "Implicit Meta". 

If someone mentions timing data, I label it "Implicit Perf".

If someone mentions "performance" or "performance data", I label it "Explicit Perf."

Grouping by metadata is essentially an 'implicit link'. This is up for debate.

Note implicit isn't exactly bad as people explain by example but in some
cases, especially with links, it can be hard to pick up.


Timelines
=========


#### P10

A.  Implicit Meta, Explicit Perf
B.  Implicit Meta, Explicit Perf
C.  Explicit Meta, Explicit Perf
D. 
  i.  Explicit Meta, Explicit Perf
  ii.  Explicit Meta, Explicit Perf
  iii.  Explicit Tree
E.  Explicit Meta, Explicit Tree, Implicit Links


#### P9

A.  Implicit Meta, Explicit Perf, Explicit Tree
B.  N/A
C.  Explicit Meta,  Explicit Perf
D. 
  i.  Implicit Meta, Implicit Perf
  ii.  Implicit Meta, Implicit Perf
  iii.  Explicit Tree, Implicit Perf
E.  N/A
F.  Explicit Meta, Implicit Perf, Implicit Tree, Implicit Links


#### P8

A.  Implicit Meta, Explciit Perf
B.  Explicit Meta, Implicit Perf
C.  Implicit Perf, Explitic Tree, Implicit Links
D. 
  i.  Explicit Meta, Implicit Perf, Explicit Tree
  ii.  (Alludes to D.i)
  iii.  Explicit Tree
E.  Explicit Meta


#### P7

A.  Explicit Meta, Explicit Perf, Explicit Tree, Explicit Stats, Explicit Links
B.  Explicit Meta, Explicit Perf, Explicit Stats,
C.  Explicit Meta, Explicit Perf, Explicit Tree, Explicit Stats, Explicit Links
D.
  i.  Explicit Meta, Explicit Perf, Explicit Stats
  ii.  (Alludes to D.i)
  iii.  Explicit Perf, Explicit Tree
E.  Explicit Perf, Explicit Tree, Explicit Links


#### P6

A.  Implicit Meta, Explicit Perf
B.  Implicit Meta
C.  Implicit Meta, Implicit Perf, Implicit Stats
D.
  i.  Implicit Meta, Implicit Perf
  ii.  (Alludes to D.i)
  iii.  Implicit Perf, Implicit Tree
E.  Explicit Meta, Implicit Perf, Explicit Tree, Implicit Stats, Explicit Links

#### P5

A.  Implicit Meta, Implicit Perf
B.  N/A
C.  Implicit Meta, Explicit Perf, Explicit Tree, Explicit Stats, Explicit Links
D.
  i.  Implicit Meta, Implicit Perf, Explicit Tree
  ii.  Implicit Meta, Implciit Perf
  iii.  Explicit Perf, Explicit Tree
E.  Explicit Meta


#### P4

A.  Implicit Meta, Implicit Perf
B.  Implicit Perf
C.  Implicit Meta, Implicit Perf, Explicit Tree
D.
  i.  Implicit Meta, Implicit Perf
  ii.  Implicit Meta, Implicit Perf
  iii.  Implicit Perf, Explicit Perf
E. N/A

#### P3

A.  Explicit Meta, Explicit Perf, Explicit Tree, Explicit Stats, Explicit Links
B.  Explicit Meta, Explicit Perf, Explicit Tree, Explicit Stats, Explicit Links
C.  Explicit Meta, Explicit Perf, Explicit Tree, Explicit Stats, Explicit Links
D.
  i.  Explicit Perf
  ii.  Explicit Perf
  iii.  Explicit Tree
E. N/A


#### P2

A.  Explicit Meta, Explicit Perf
B.  Explicit Meta, Explicit Perf
C.  Explicit Meta, Explicit Perf, Explicit Stats, Explicit Links
D.
  i.  Explicit Meta, Explicit Perf, Explicit Stats
  ii.  Explicit Meta, Explicit Perf
  iii. N/A
E. N/A


#### P1

A.  Explicit Perf
B.  Implicit Perf
C.  Explicit Perf
D.
  i.  Implicit Meta, Explicit Perf
  ii.  Implicit Meta, Explicit Perf
  iii. N/A
E. N/A

