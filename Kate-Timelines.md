

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
E. Missing in Object 
F. Other Discussion


#### Separate this in figure

G. Direct Prompting - e.g., when we ask 'What about the metadata?' anywhere in
session

#### Notes

We could possible merge "Missing in Object" with "Other Discussion" as I think
it doesn't ever generate new data until we probe.

I'm not including the ABC Tree because that is purely separate from the data.


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
- Late: They mention it later in the answer, for example, after A1 asks for
  clarification in a way that doesn't directly prompt or change the question.
Alternatively when they draw it non-explicit first and then make it explicit.

For example, if someone mentions different compilers without mentioning
metadata, I label it "Implicit Meta". 

If someone mentions timing data, I label it "Implicit Perf".

If someone mentions "performance" or "performance data", I label it explicit.

Grouping by metadata is essentially an 'implicit link'. This is up for debate.

Note implicit isn't exactly bad as people explain by example but in some
cases, especially with links, it can be hard to pick up.


Timelines
=========


#### P10

A. Implicit Meta, Explicit Perf
B. Implicit Meta, Explicit Perf
C. Implicit Meta, Explicit Perf, Late Explicit Meta
D. 
  i. Explicit Meta, Explicit Perf
  ii. Explicit Meta, Explicit Perf
  iii. Explicit Tree
E. Explicit Meta, Late Explicit Tree, Implicit Links
F. N/A
G. N/A


#### P9

A. Implicit Meta, Implicit Perf, Late Explicit Tree, Late Explicit Perf
B. N/A
C. Implicit Meta, Implicit Perf, Late Explicit Meta, Late Explicit Perf
D. 
  i. Implicit Meta, Implicit Perf
  ii. Implicit Meta, Implicit Perf
  iii. Explicit Tree, Implicit Perf
E. N/A
F. Explicit Metadata, Implicit Links
G. Implicit Perf, Implicit Tree, Implicit Meta


#### P8

A. Explciit Perf, Implicit Meta
B. Implicit Perf, Explicit Meta
C. Explicit Tree, Implicit Perf, Implicit Links
D. 
  i. Explicit Tree, Implicit Perf, Explicit Meta
  ii. (Alludes to D.i)
  iii. Explicit Tree
E. Explicit Meta
F. N/A
G. N/A

#### P7

A. Implicit Perf, Implicit Meta, Explicit Tree, Explicit Links, Explicit Perf, Explict Meta, Explciit Stats
B. Explicit Perf, Explicit Stats, Explicit Meta
C. Explicit Tree, Explicit Perf, Explicit Stats, Explicit Meta, Explicit Links
D.
  i. Explicit Perf, Explicit Meta, Explicit Stats
  ii. (Alludes to D.i)
  iii. Explicit Tree, Explicit Perf
E. (Other issues discussed)
F. Explicit Tree, Explicit Links, Explicit Perf 
G. N/A

#### P6

A. Explicit Perf, Implicit Meta
B. Implicit Meta
C. Implicit Meta, Implicit Perf, Implicit Stats
D.
  i. Implicit Perf, Implicit Meta
  ii. (Alludes to D.i)
  iii. Implicit Tree, Implicit Perf
E. N/A
F. N/A
G. Explicit Meta, Explicit Tree, Implicit Stats, Implicit Perf, Explicit Links

#### P5

A. Implicit Perf, Implicit Meta
B. N/A
C. Explicit Perf, Explicit Stats, Explicit Links, Explicit Tree, Implicit Meta
D.
  i. Explicit Tree, Implicit Meta, Implicit Perf
  ii. Implicit Perf, Implciit Meta
  iii. Explicit Tree, Explicit Perf
E. (Other issues discussed)
F. N/A
G. Explicit Metadata

#### P4

A. Implicit Meta, Implicit Perf
B. Implicit Perf
C. Explicit Tree, Implicit Perf, Implicit Meta
D.
  i. Implicit Perf, Implicit Meta
  ii. Implicit Perf, Implicit Meta
  iii. Implicit Perf, Explicit Tree
E. N/A
F. N/A
G. N/A

#### P3

A. Explicit Perf, Explicit Links, Explicit Meta, Explicit Stats, Explicit Tree
B. Explicit Perf, Explicit Links, Explicit Meta, Explicit Stats, Explicit Tree
C. Explicit Perf, Explicit Meta, Explicit Stats, Explicit Links, Explicit Tree
D.
  i. Explicit Perf
  ii. Explicit Perf
  iii. Explicit Tree
E. N/A
F. N/A
G. N/A

#### P2

A. Explicit Perf, Explicit Meta
B. Explicit Perf, Explicit Meta
C. Explicit Perf, Explicit Meta, Explicit Links, Explicit Stats
D.
  i. Explicit Perf, Explicit Meta, Explicit Stats
  ii. Explicit Perf, Explicit Meta
  iii. N/A
E. N/A
F. N/A
G. N/A

#### P1

A. Explicit Perf
B. Implicit Perf
C. Explicit Perf
D.
  i. Implicit Meta, Explicit Perf
  ii. Implicit Meta, Explicit Perf
  iii. N/A
E. N/A
F. N/A
G. N/A

