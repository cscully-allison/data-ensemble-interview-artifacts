# Themes


## What factors lead to remembering dimensions/aspects of the data?

KT: P6 trying to recall actual results, or at least draw similar graphs to what they have seen. Grounding their choices in prior knowledge.
    - P5 also trying to recall performance metrics
 
- Looking for common core, something to orient the data around
    - P4: “there needs to be some common core, because like, the example would be structured about something that has some commonality, and then you will do perturbations to the input parameters or the execution environment like this, there's really no limit to what you could consider that”
    - P1: looking for consistency to orient the mental model of runs, “Because that's a very, like, throughout all the different kinds of data that I work with, there's always nodes.”



## What elements of a data mental model are there, perhaps those we don't typically think of as part of data typologies? (e.g., causality between parts of the data)

### Related: how do people connect multi-typology data?

- In this ensemble, people use the nodes of the tree (i.e., the functions of the program) to connect the different datasets
    - P5: call tree/call graph provides context and insight into dependencies
    - "And the great thing about like how [EnsembleAPI] and [DatasetAPI] and altogether works together, is that now we can also look into dependencies between these annotated regions."
    - P5: For the Strong Scaling Study, P5 explained challenges in getting the trees to match so that tools are functional and helpful (e.g. don’t need All_Reduce for 1 thread)
    - P6: "the call tree should be the same or similar across the sets of runs. So we have a single representation of the call tree. And then for each node in the tree, we are basically recording the the multitude of runs, and the multitude of runs can be all of the runs for this picture."
    
    
- In this ensemble, people use the profileID of the run to multi-index/connect into the different tables
    - P3: "the performance data is the mean data with multiple index and it's connected to to the two of these other tables through two of its indices from the muilt-index."
   
## How do people summarize big datasets for communication of shape?



## How do people keep track of their analysis?

- P5 wishes for a history of analysis
    - “But right now, I'm having like a lot of steps where I use this data to make some analysis on and all the time you like, have to handle the different [EnsembleAPI Object] and the different objects and all your calculations again, by yourself. And they kind of get lost in a way... But like after 20 notebook cells, you really get lost with what's going on where and, like, what I'm missing is like, not a [EnsembleAPI Object] object, but like a container, where you can add all your analysis to in a ways that this is also carrying some metadata for you to allow to, like, get back some specific analysis that you're done, like, two weeks prior that way.”




## What pieces of the data do people recall initially?

P1
* Performance data (in detail)

P2:
* Performance data
* Metadata

P3:
* Perforamnce data
* Metadata
* Statistics
* Call graph/call tree

P4: ensemble is ??
* Context (metadata?)
* Relationships between instrumented parts of code

P5:
* Performance data
* Statistics data
* Call tree/call graph

P7: 
* Performance data 
* Metadata
* Statistics frame
* Call tree/call graph (not described as a "main part" of the data, not drawn)

P8: ensemble is performance timing data from multiple runs of physics simulation
* Timing data/Performance data
* Metadata
* Call tree (only drawn, not mentioned)

P9: performance regression test (3 cases tested with various # of threads)
* Performance data (time)
* "Annotation tree" (artifical calling context tree)

P10: testing variations in condititions for running BenchmarkSuite (e.g. architectures, versions, compiler, tunings)
* Tunings
* Variants
* Performance data by kernel
* Metadata
    
    
- P6 described a different dataset. P6 described a multiphysics program run, with several computation phases and communication phases. Their main parts of data is the communication because it’s the source of the noise (did not describe data structures or the format of the data). The dataset is a Strong Scaling Study
    * Draws graph for communication time and a graph for computation time
    
    
- When initially describing the data, P7 includes the call tree/graph but then does not draw it or include it as a main part.
    * “So with  [EnsembleAPI Object], the general premise is you'll have a collection of profiles presenting different runs of a piece of software. And those runs can be differentiated by almost any parameter, problem size compiler.”
    * “you load everything up into a single Python based data model, which consists of a graph or "call tree" or "call graph," whichever one your tool is actually collecting.”
    
- Need the context of the runs, the metadata
    - includes the variables of the application, the metrics related to the architecture, execution environment
    - P4: “we have to capture the context so that we describe the context to the extent that we can run do the comparisons. So the context includes things like the compiler, libraries, build dependencies, the actual hardware that things are being run on.”
    
- P3 considers performance datatable to be the "main table" due to multi-indexing
    - "if you look at it from a relational database management system, our relational database management model. So the performance data is the mean data with multiple index and it's connected to to the two of these other tables through two of its indices from the muilt-index."
    - P3 says their ordering is based on parts they work on and functionality of software (i.e., table is missing some functionality so lowest preference)


- Importance of data elements relates to parts they are “touching” for development of performance application
    - P2: “So the stats functions, statistical functions that I've developed for the Thicket project, primarily perform operations on the performance data, so you know, time, front and latency like I had mentioned earlier. So that's one of the reasons I see it as a an important since I do most of my work on it.”
        * Yet they didn't initially state the statistical table or functions as part of the data?
    - P1: “I order it [the parts of the ensemble] because that's kind of like the when I'm developing the significance of what what I'm interacting with the most, it's probably in that order.”

## Strong scaling study

- Participants start with performance data, then include metadata.
    - P7: "so a lot of that data you care about, start with start off with performance data. So you'd have in this case, in fact, you probably have another index… So yeah the number of ranks in that case would be part of the metadata...it started with the metadata and performance data, then you go down to the statistics as needed.”
    - P10 uses performance data and metadata to determine time per kernel metric, plot ranks vs time with multiple lines showing different variant and tuning
    - P2 states metadata and performance data, then adds statistics as an afterthought
        * “Because you know, in the metadata, this is where we're kind of, you're kind of mapping the like, the information that you use to kind of run the job.”
    - P1 uses EnsembleAPI to load multiple profiels with differing numbers of threads

- P3: only looks at performance data table.

- Participants implicitly describe the metadata but do not explicitly state "metadata" until prompted.
    - P8: KT: Says they need to use metadata (“for example, maybe from, you know, the individual runs in the ensemble… something like cycles…but also certainly things like world size, right? For an MPI problem, number of processors, number of cores, or maybe number of nodes, right?”), then draws a line graph
    - P8: Omits metadata but didn’t realize it. “You know, I actually did omit it? And I, you kow, I don’t think of the metadata really, as I guess, I guess I think of that as a separate piece from the actual timing, tree data, right?”

- Participants discuss possible reasons for slowdowns
    - P4: “And that in the scheme of iterations that you work through, you are always taking more or less the same time to not waste resources, where all the other resources that are idling, they're still going to maybe consume some energy or they are blocking somebody else that could be doing useful work.”
    
- P9: visually compare the graphs, side-by-side




## Using tree to relate functions/code to performance data

- P5: Feeds performance metrics into the stats table for insight, but then the tree helps provide further insight
    * “And then we present into another data frame, where now we have a statistical view onto our, like, raw data set. And then this helps to this really helps with visualization, again, was a tree.”
    
    
    
## Using tree for hierarchy, relationships between functions

- P4: Uses "call graph", "call tree", and "call stack" yet understands the nested nature of the call tree and placing the timing data/profiling data onto the tree?
    * “And then for each of the processes, we might be capturing multiple fields of data. And sometimes this data could have a hierarchy of itself. But for most of the data that we are working with, we don't really capture that hierarchy, it's kind of condensed into something that is relatively flat…So flattening the data, in many cases make things a lot easier to work with.”


- P8: calls tree a hiearchy but does not state the relationship between the nodes or indicate why it's a hierarchy


## Difficulty in concisely/accurately describing the tree

- P8: doesn’t remember the word node (“for each, I guess, leaf is not the right word.”)
    - Has difficulty describing the tree, “So, you know, function name, where you have a routine name or something like that, and then you have your timing data, and you have that for every level in the tree basically...I don’t think I’ve ever thought about it quite like that.”
    - In low exclusive/high inclusive question, P8 refers to the tree but also calls it a hierarchy
        * “Right, that that really does come all down to the tree. And, you know, we see that quite frequently. Um, but yeah, that that, that all comes down to the hierarchy.”


## Comparing two architectures

- Participants use runtime metric to determine "better" but need additional data for why
    - P5 likes performance counters to help with the why (behind the runtime)
    
- Participants need some similarity before comparison (e.g. similar architecture, same code run in different settings, only changing amount of threads but keeping other vars constant) 
    - P4: “But in certain sense, we always need some basis that we share so that we can do a useful comparison.”
    - P4: metrics also need to be comparable. “But it's not always completely possible, because sometimes we don't have the same performance counters. So that is maybe one problem to keep in mind. But considering we have similar performance counters, that we can collect from the systems, then, like, I think the key is that we have the same metrics that we can collect, and then do the runtime analysis.”
    - P3: says to "columnar join" on similar parts of performance data table.
        * "But I think it's called a columnar join. So use parts of the performance data table to kind of make that differences and compare it within the performance data table."
    - P1: also columanr join
    - P10: use Speedup to compare, which is CPU time divided by GPU time

- Side-by-side
    - P2: side by side tables
    - P1: columnar join (side-by-side tables-esque)
    - P9: sibe by side graphs
    
    
- Paticipants use the metadata to differentiate between the architectures
    * P7: "Kind of the same: “you'd have two systems, they'd be differentiated by, again, this metadata stuff.”
    

- Participants say comparing two architectures is similar to strong scaling study
    * P8: says program will look similar to the strong scaling study
        * “It is basically going to look exactly like the last, the last response, right? The average time maybe divided by number of cycles, right? And you’ll have how many nodes or cores, whatever your interest added in there, and strong scaling plot of that, which I drew for the last one.”
    * P9: change fields but again, compare graphs side by side

    

    
    
## Low exclusive time, high inclusive time

- Participants find the tree useful
    - P5: “to me personally the data frame is not really useful. It's more like it transportation layer to compute a visual view onto what's going on. So my first step would probably be to look into the tree side by side with, on one side, you have exclusive time. And on the other [. . .], you will have exclusive time. So that you actually come up with like, there is a difference, I think that would help me”
    - P7: uses the tree and performance data --> “then you'd pretty much just have to do a walk traversal of that subtree or sub graph.”
    - P4: traverse the tree “Yeah, I'm still not completely sure if I may have missed the core of the question, because for me, it's like, I don't know, like, I can kind of trust the instrumentation. And then I can just traverse the tree and kind of pick out the elements that I think are contributing to that.”
    - P6: looks at a hierarchy, but the tool they use doesn't distinguish between inclusive and exclusive time?
    - P10: “Let’s start with the tree.” Also query language to filter the tree, “if I knew which node had so I guess, you know, first step, I would still be printing the tree probably. And once I had identified what node, let me just assume one node has the high inclusive time I would use that query language with the kernel being the root node, and then just grab everything underneath it...down to the leaf nodes."



- Particpants draw tables of the times
    - P4 draws table

## If I want to find out which function called another function, what portion of the data would be most important for that? 

- P3: Call tree, “we have a very basic implementation of queries.”

## ABC question

- Participants seem to understand the question better when a relationship between A-B-C is given
    * P5: “that would make more sense to me. You have A at the top, and then you have like some relation... And this probably has to be exclusive times. So B let's say B is like the child too. So these are only leaf nodes in our tree.”
    
- Participants annotate the tree with the times
    * P2 draws indented tree, calls it a tree
    * P7 draws a node-link diagram with the node names and times in the nodes.
    * P8 draws an indented tree with time annotations
    * P9 draws an indented tree with a table-like arrangement of times  next to the tree, copying the tool “That's how [MeasurementAPI] would look.”
    * P10 draws tree and table
    
- Draws the dataset in terms of the tool/software/app
    - P1 draws MeasurementAPI files and EnsembleAPI table, no trees (but also, A1 did not provide a relationship between A,B, and C
    
- Paricipants consider other data structures
    - P3: Um, so it doesn't have to be like a table. It can be any data structure,
        - R1: However you want to represent it. 
        - P3: Okay. Um, I think I'll just use a table then its probably the . . . I think this was just the easiest approach.


    
## Metadata

- Definition of metadata:
    * P8: “I consider made meta data to be I guess, sort of what I would call the basic characteristics of the problem."
        - YES: architecture, system name, OS. NO: total memory usage, memory usage per MPI rank, total number of dofs, etc. POSSIBLY: total overall execution time
    * P3: " we have information like, who who ran the program, how long, how long the program ran, when the launch date was, all that kind of information. So not strictly performance data, but kind of more information about the execution of the program for each of the profile”
gives examples of metadata: launch date, user
    * P2: when a job was ran, what system it was ran on, the compiler, compiler optimizations
    
    
- P5: Metadata used to answer queries, but not considered part of the data
    * "“Um, well right now it's kind of, detached in ways, the metadata is only really used to like. . . you can look into the metadata. And then you can query by it... But honestly, like, right now, I'm only using it to query for stuff, which I know its there but I'm not really using it to explore the application in a way that I know you could use metadata for."

    
- P8: complains about pulling out the metadata "in a useful way", i.e., as ints/floats, not as strings
    * KT: Is the metadata in a separate dataframe that they don’t know exists?
    * “So so, you know, by my Python skills are can be iffy, at best. So, you know, like I said, some of these things may, absolutely, it may be easy to get out of the object, and I just don't know how to do it. One of the things that I will say has been a challenge has been or can be metadata. I don't you know, and maybe all of the metadata really is wrapped up in the in the [Programmatic Profile Analysis Software A]  object”
    * “this is made a little difficult in Python, since it's not a typed language, but you know, when I pull out a number, I don't want it to be a string”
Can’t recollect the exact columns that cause the issue

- P8: Hard to know ahead of time what metadata you will find interesting
    * “But you know, the the thing with the metadata is, it's very hard to predict what you're going to want to look at, you know, so when you when you go through the code, you just kind of throw a bunch of stuff in there, here. Here's, here are all the things that I think might be interesting, right? Start Time, stop time, cluster name, architecture, you know, all of these kinds of things that you're like, Okay, well, when I go to sit down and analyze this data, these are the things that I might actually be interested in. But it never fails. When you do that, that you're gonna come across something that well, why didn't I put that in there? Right? Or can I infer that from what I did put in there? And sometimes, yes, sometimes no.”
    
- P9: as a side note!! Says metadata
“for each of the test cases, we have our metadata annotations here, which shows well just, a bunch of things like well, okay, of course, the time it was recorded, all the metadata, like the number of threads that we use, the test case name, and other stuff, like compilers, and whatnot. And also, basically the global performance metric that we're interested in, ultimately, which is like, time for instrumentation call, and also, the total runtime after benchmark again… compiler, system”






