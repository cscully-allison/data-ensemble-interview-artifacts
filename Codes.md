# Conventions
===========

During early stages, please add recklessly. Possible dupes are okay. We will
split/merge in later rounds through discussion/affinity diagramming etc.

## Themes are written as first-level headers

  - Codes are written as next level, subcodes as the following level
  - Evidence is listed as bullet points, ideally quotes but at least
    references to participants.

# Themes & Codes
==============

## Ensemble Elephants

These codes have something to do with the mental model of the data. This
probably needs to be split or at least made hierarchical at some point, but
for now let's put everything here.


### What is an ensemble?

  - Multiple profiles / runs
    - P1: "Purposely multiple profiles of data as in comparison to \[DatasetAPI], where it may be only or usually is only one profile?"
    - P3: "we allow multi runs, multi run performance data, which is basically multiple profiles to be stored into an object."
    - P5: "It's also a good idea to have multiple rounds in order to model anything, basically, this also helps us in a way that we can take, like 10 rounds, and then we would have two profiles, we would generate a stats frame for that have like an aggregated or statistical relevant view on the data that we have."
    - P6: "included basically lots of repeat runs"
    - P7: "we just collect that data into what we do those runs multiple times."
    - P7: "So the idea is load this data from all the trials into one big performance model and analyze it."
    - P8: "And what comes out of that is really timing data. Right. So, you know, we use \[Lab]'s \[MeasurementAPI] library, and it generates timing data. And so I ended up with this with, you know, a set of timing data for every run. And so, you know, we do an ensemble of runs, typically, you know, I don't know, five or 10 different runs, right."
    - P9 performance regression test (3 cases tested with various # of threads)
    - P9: Multiple tests "So we're basically running through a few different test cases, every test the speed of the annotation instrumentation library,"
    - P9: "it runs through a few different test cases. So specifically, there's one test case where we're testing the \[MeasurementAPI] instrumentation calls without any measurements. And then two measurement configurations. One is aggregation, which would basically give you a, well, a profile that you normally get out of applications that we look at where we aggregating things, \[unintelligible] over time, and one is a trace. So we're recording every beginning and reaching event. Okay, so these are the three test cases. And then we're testing that gun across a bunch of numbers of threads actually, sort of get only like single process runs, because we're looking only at the local \[MeasurementAPI] instrumentation time, but over different numbers of threads."
    - P9 "So once you have that you can run this experiment for different numbers of ranks, obviously, you're getting separate data sets for each of these experiments."
    - P10 "So out of the \[BenchmarkSuite], we're wanting to run the kernels across different variants. And then the variants will be run across different architectures such as GPU. We might be running it with different versions of \[BenchmarkSuite], and understanding the performance of \[BenchmarkSuite]. You could be using different compilers in the \[BenchmarkSuite] and understanding compiler benefits or performance benefits. Let's see. And then I guess within that as well, we have different tunings that exists within the variants that might change the performance as well."
  
  - Examples of different things to collect
    - P4: "for the performance data, we are basically dealing with different programs, executions, and there's different these programs are instrumented and they typically collect different performance counters, these might be exposed to the CPU, these can be software counters that are kind of made up just for the purpose of a special investigation into some performance question"
      - Also: "And typically the applications we are working with, and they will be implemented this way, they do have a few parameters of themselves."
      - "And we are working on different architectures and platforms. And this leads to these counters being expressed differently."
    - P5 also lists possible data to collect
    - P6 explains in terms of the questions about systems and noise
    - P7 "So a lot of what we're dealing with is just to be added as a few layers, so to say, all right, like the opening close calls, three intercept time, that normal time, the actual producer code, yeah, consumer code going deeper, we time the actual send and receive functions that you've DCX stuff like that's what time these different layers, the software"
    - P7 "So you have performance data where you have which is indexed on both your profile ID and your nodes, that contains your actual metrics, the data, so time memory usage, stuff like that. There's the metadata frame, which is only indexed on profile ID. And that just contains information again, like compiler, problem size, the things that can differentiate the runs. And then there is also a statistics frame, which is the stores the results of many aggregate statistics operations on performance data. And that is also indexed on the nodes."
    - P8 "And typically, what comes out is, you know, you have, you can get various things depending on what options you ask for when you run the code. But, you know, typically, it consists of something like a minimum time, a max time and an average time."
    - P9 "And one thing that's pretty useful is we have like the details, exact amount of times. So for each of the test cases, we have our metadata annotations here, which shows well just, a bunch of things like well, okay, of course, the time it was recorded, all the metadata, like the number of threads that we use, the test case name, and other stuff, like compilers, and whatnot."
    - P10 draws the metadata first as a list of columns/things to collect

  - Hazy / Flexible
    - P4: "I tend to be very flexible and fuzzy in the definition there, because my experience has just said, it doesn't even make too much sense to constrain it so so much."
    - P4: "So there's a few different structures to data, but I think this is two things that I've commonly seen."
    - P7: "and because it allows a lot of flexibility. And so exactly, what you want to do depends a lot on the specifics of the past. The specific data that you have stuff like that,"
    
  - Multidimensional
    - P4: "But it's basically a multi dimensional space of, of parameters to care about."
    - P4: "I think it makes sense to look what is kind of distributed across the MPI ranks. And typically, we have some application domains. So this might be a volume or space."
    - P4: Refers to enemsble as relationships between instrumented parts of code
    - P9: "So it's like, like not too ensemble-y, I would say, with only like two dimensions."
    - P9: thinks in terms of IVs (independent variables) "So I think the ensemble part of this is that we're recording this thing for, well, looking at our benchmark for three different test cases and a bunch of different threads. So yeah, it's only like two dimensions. In this case, it's over three, if you consider that we're doing this over a period of time. So we're looking at data in the past and tell us developing now."
    - P10 implied by the number of factors listed
 
  - Outcome not the data
    - P6 draws outcome plots
    - P8 "And, you know, and I want to be able to infer something about the collection of runs, right? And not just, you know, it might be nice to look at one individual, but really, this is this is really more about the ensemble than it is any single individual."
    - P8: ensemble is performance timing data from multiple runs of physics simulation
 
  - A process
    - P6 discusses filtering and reductions when asked to describe [EnsembleAPI]
    object.
    - P10 "But the idea being that we have the tuning and the variant captured within our [EnsembleAPI]  object. Right now, we've been capturing the metadata, or the variant into the metadata. But I think there's this further to this further, more fine grained specification that we're trying to get after where we're putting tuning also into the metadata. So that we can then filter , you know, basically create sub-[EnsembleAPI] that are based on the variant and the tuning together."

  - Supports multiple studies
    - P8 "Yeah, my Python is pretty, pretty awful. But it does show the kind of, at least for me, and and the kind of workflows that I, in particular want to do with \[EnsembleAPI] with which these are the scaling workflows, right? Weak scaling, strong scaling, throughput studies, right? "

    
  
### Pieces of the EnsembleAPI were forgotten.

  - For each participant and each EnsembleAPI piece, list when, if ever, the
    participant alluded to the piece and how. 
  - For this code, there are four pieces: Performance Data, Metadata, Stats
    Data, and Call Tree (Call Graph).
  - For this code, there are four places it can appear: initial verbal question, drawing, tasks, and never. It may be useful to mark when something appeared in one but was later forgotten.
  - P1
    - Performance data: 
      - Spoken (In detail)
      - Drawn as a table
    - Call tree: 
      - Spoken* - acknowledges DatasetAPI nodes, but claims EnsembleAPI is different. Nodes appear to be used in a different way than as a tree
      - Not Drawn
      - Would consider this not totally included
    - Metadata
      - Only implied through indices when spoken/drawn
      - Alluded to during tasks
    - Stats
      - Never
  - P2
    - Performance data:
      - Spoken
      - Drawn
    - Call tree:
      - Not spoken
      - Not drawn
      - Never
    - Metadata:
      - Spoken
      - Drawn
    - Stats
      - Not initially spoken, comes up glancingly in importance question
      - Drawn
  - P3:
    - Performance data:
      - Spoken
      - Drawn
    - Call tree:
      - Spoken
      - Drawn
    - Metadata:
      - Spoken
      - Drawn
    - Stats:
      - Spoken
      - Drawn
    - Inductive Codes:
      - P3 considers performance datatable to be the "main table" due to multi-indexing
          - "if you look at it from a relational database management system, our relational database management model. So the performance data is the mean data with multiple index and it's connected to to the two of these other tables through two of its indices from the muilt-index."
          - P3 says their ordering is based on parts they work on and functionality of software (i.e., table is missing some functionality so lowest preference)
  - P4:
    - Performance data:
      - Speaks common performance fields
      - Drawn
    - Call tree:
      - Spoken to some extent "But there's also the relationship of these annotated regions."
      - Drawn
    - Metadata:
      - Speaks metadata fields
      - Spoken (as runtime context)
      - "I think the key is that there needs to be some common core, because like, the example would be structured about something that has some commonality, and then you will do perturbations to the input parameters or the execution environment like this, there's really no limit to what you could consider that."
      - "So the context includes things like the compiler, libraries, build dependencies, the actual hardware that things are being run on."
      - Drawn kind of as the data sourcing?
    - Stats:
      - Not Spoken
      - Not Drawn
    - Inductive Codes:
      - Need the context of the runs, the metadata
      - includes the variables of the application, the metrics related to the architecture, execution environment
        - P4: “we have to capture the context so that we describe the context to the extent that we can run do the comparisons. So the context includes things like the compiler, libraries, build dependencies, the actual hardware that things are being run on.”
  - P5:
  - Performance data:
    - Spoken implied by "counters" and "timestamps"
    - Drawn
  - Call tree:
    - Spoken implied by "regions", and mention of "nodes"
    - Drawn
  - Metadata:
    - spoken implied by 'compilers'
    - Not drawn
  - Stats:
    - Not spoken
    - Made refrences to derived statistics as part of analysis
    - Drawn
  - P6:
    - Performance data:
      - Spoken/implied
      - Drawn/implied (axes)
    - Call tree:
      - Spoken/implied ("phases", communication calls)
      - Spoken in more detail on prompting
    - Meta data:
      - Spoken/implied (architectures, scales)
      - Drawn/implied (axes)
      - On direct ask, did not get into metadata
    - Stats:
      - Drawn/implied (variance)
      - Spoken later on prompting
    - Inductive Codes:
      - Unique Data Description
        - P6 described a different dataset. P6 described a multiphysics program run, with several computation phases and communication phases. Their main parts of data is the communication because it’s the source of the noise (did not describe data structures or the format of the data). The dataset is a Strong Scaling Study
          * Draws graph for communication time and a graph for computation time
  - P7 [drawing](https://github.com/cscully-allison/data-ensemble-interview-artifacts/blob/main/P7/Scanned%20from%20a%20Xerox%20Multifunction%20Printer.pdf)
    - Performance data
      - Spoken
        - On Importance: "Yeah, so the most important is definitely the performance data."
      - Drawn
    - Call tree
      - Spoken
      - Drawn
    - Metadata
      - Spoken
      - Drawn
    - Stats
      - Spoken
      - Drawn
    - (KATY: Can you explain this a bit to me? I thought P7 included the call graph in their initial drawing.)
    * Call tree/call graph (not described as a "main part" of the data, not drawn)
    * When initially describing the data, P7 includes the call tree/graph but then does not draw it or include it as a main part.
        * “So with  [EnsembleAPI Object], the general premise is you'll have a collection of profiles presenting different runs of a piece of software. And those runs can be differentiated by almost any parameter, problem size compiler.”
        * “you load everything up into a single Python based data model, which consists of a graph or "call tree" or "call graph," whichever one your tool is actually collecting.”

  - P8
    - Perf
      - Spoken/alluded to with timing data
      - On importance: "the timing data is, is is very general, right, you can do a whole lot of things with that. . ."
      - Drawn as hanging off the tree
    - Call tree
      - Spoken/alluded to with code regions BUT not as a tree
      - Drawn very clearly tree first
    - Metadata
      - Spoken/alluded to "And then there, there are other things you can get, you know, in, in the ensembles, one of the things that's, that's can be important, too, is variants and things like that. You know, so that can be an important attribute to get, but but that's, that is in general, you know, what we get out of that?"
      - During importance question: "There's metadata associated with each of those pieces."
      - Not Drawn
    - Stats
      - Never
  - P9
    - Perf
      - Spoken
      - Drawn (y-axis)
    - Call Tree
      - Possibly spoken/implied (function annotations)
      - "Annotation tree" (artifical calling context tree)
      - Spoken with the word 'tree' for the annotations
    - Metadata
      - Spoken/Implied (e.g., 'per benchmark)
      - Drawn (x-axis after having stated time as a metadata dimension)
    - Stats
      - Never
  - P10
    - Perf
      - Alluded to/implied initially
      - Drawn as lists of data columns too
    - Call Tree
      - Not initially spoken
      - Not initially drawn
      - Appears for Task 3
    - Metadata
      - Alluded to/implied initally
      - Drawn as abstract list of column names
      - Actually drawn twice
    - Stats
      - Not initially spoken
      - Not initially drawn

#### Describing application instead of performance data
  - P6
  - P10 regarding the project, eventually gets into the data.

### Relations Between Data Parts
    
#### Ensemble data structure pieces are linked structurally

  - P1, P2 (drawing, speaking), P3 (drawing, speaking)
  - P4: "we're nesting multiple contexts into each other"
  - P5: Draws arrows from perf frame to stats frame and stats frame to tree
  - P2: Two parts share a similar structure "So \[the stats table] is kind of the same kind of format as the performance table."
  - P3: "And it's going to the first table, which is the performance data table with with that profile hash that we just talked about. So it's like a foreign key for for that table."
  - P3: ".You can see the relationship between these is through the profiles the profile hash."
  - P7: "So you have performance data where you have which is indexed on both your profile ID and your nodes, that contains your actual metrics, the data, so time memory usage, stuff like that. There's the metadata frame, which is only indexed on profile ID."
  - P6: "right, and the metadata is per run. So there's a correspondence between the table that has all of the runs recorded. And so for each of the 10, or whatever runs, you have an entry in your metadata that records all of the all the things you know about that run."
  - P7: "And then there's three data frames constructed using the nodes in the graph and the profile IDs as the indicies different, like combinations of those things, depending on the data frame."
  - P7 describing a graph database
  - P8 "it's very hierarchical, right?"
  - P8 "it is this hierarchical grouping of elements, right, that, that starts with a straight line that goes all the way down from top to bottom, right. And then you have the hierarchy that comes off the side. I mean, you can collapse, you know, the hierarchies in various points. So that that's, that's really what I think of when I think of this data, and that sort of hierarchical description."


#### Ensemble data structure pieces are linked meaningfully
  -  P1 ". Your profile one would be corresponding to the data set from the run with two CPUs and then profile two correspond to the run with four CPUs, and then you'd see in your times, well, you should see that the time for profile one is gonna be higher than the time for profile two, because it had more CPUs"
  - P2 "Obviously, they kind of affect each other, like, in some kind of formats, because, you know, certain metadata like compilier optimization, things like that will directly affect the values 
  - in the performance data table."
  - P3: "And one thing that's important to note is that the statistics and the performance data table they also have a call graph component to it. So they have a tree component to it. And these two represent the nodes and the relationship between the nodes."
  - P5: ". . .the data frame is not really useful. It's more like it transportation layer to compute a visual view onto what's going on."
  - P5 "And the great thing about like how [[EnsembleAPI]] and [[DatasetAPI]] and altogether works together, is that now we can also look into dependencies between these annotated regions."


#### Influences on importance 

#### Presence / Commonality
  - P1: "throughout all the different kinds of data that I work with, there's always nodes"
  - P1: "the metrics themselves is another dimension of that, that I'm adjacent to the nodes that I'm expecting to see when I'm working with the data"
  - P4: "It's just that like, time to solution is something that is very often captured."

#### Indexing power
  - P1: "but it's kind of less important because we have that represented as like an inner index . So it's kind of like, subsequent to the nodes, I guess, in the visualization in my head."
  - P3: "performance data is acts as sort of the main table, if you look at it from a relational database management system, our relational database management model"

#### What participant interacts with

  - P1: "Yeah, I order it because that's kind of like the when I'm developing the significance of what what I'm interacting with the most, it's probably in that order."
  - P2: "I see the performance data as the most important piece of the ensemble data, just because most of the work that I do is on the performance side."
  - P3: "personally, I've worked mainly with metadata table. So that's why it took precedence compared to the statistics table."
  - P8: "Yeah, so in general, you know, I mean, you take these ensembles, and I mean, we can do you know, the timing data is, is is very general, right, you can do a whole lot of things with that, depending on what you're trying to, you know, get out of the ensemble, right all kinds of different things, but I typically am interested in at least up to this point, my primary interest has been how the code performs in different scaling regimes."
  - Tensions with this model
    P2:  “So the stats functions, statistical functions that I've developed for the Thicket project, primarily perform operations on the performance data, so you know, time, front and latency like I had mentioned earlier. So that's one of the reasons I see it as a an important since I do most of my work on it.”
      * Yet they didn't initially state the statistical table or functions as part of the data?

#### What leads to insight (Connor: Look for split opportunities here)

  - P2: "I think, you know, with what we're kind of working towards on the project, performance data kind of provides insights into your data. More, so I think then possibly metadata does because you can, you know, perform correlations, perform time series analysis and things like that. So you can kind of get a much better insight, in my opinion, using the performance data rather than the metadata."
  - P4: "I think it boils down to the question that you're investigating what is important, and that basically informs us the granularity I was mentioning, but also the parameters that you are capturing."
  - P4: "If you want to optimize for energy to solution, then you have to look for for different metrics, and even some things that we are not currently capturing. But it really depends on the objectives that you want to take into account."
  - P5: [In refrence to the stats frame and its importyance] "this is more interesting for the tree view, I think, in many ways, and because we can aggregate of all the profiles that we have available for each node, so that we can get like a mean of all our metrics"
  - P7: "Yeah, so the most important is definitely the performance data. That's your actual stuff, you have to analyze."
  - P8: "the timing data is, is is very general, right, you can do a whole lot of things with that, depending on what you're trying to, you know, get out of the ensemble, right all kinds of different things,"
  - P10: "But it's really the tunings that we're after to understand how they're performing."
    - This is specifically an attribute/column of the run that they care about
    - "So that's really helping us understand, you know, where were we running, it's giving us an idea of where we are running, and then what optimizations we might have done to the kernel."
  - P7: "In terms of the statistics, and metadata. They're important, depends what you want. So if you really want to get a sense of how things change within parameters, your performance data, or your metadata are probably a bit more important. If you're more interested in just how things perform on average, or, again, on statistical operations based on performance data, then your statistics will be more important than that data just depends on what you want to analyze."

#### Feature maturity

  - P3: "And then once we talk about the entire table, I bring the call call tree because that's a functionality we're still working on. And making sure like changes can be propagated to that data structure. So it's still a work in progress compared to the tables."

#### Easy to understand

  - P5: "So right now my favorite favorite metric, I say, because like I guess, so it's really easy to understand what you want to optimize for, because you're obviously looking for the lowest runtime."


### Multidimensional Data Produces Unique Struggles in Holding a Mental Model

#### Participants dropped or reduced dimensions of the data. (Connor: Second pass)
    
  - by accident
    - P6 "Right, so each data point in here is basically so this is one run rate. And then the error bars? Well, no, that's not a one run, it's an average of the runs. And the error bars are also the average for the different runs right?"
    - P7 "Yeah. So essentially, problems are essentially problem scale in terms of the system size, like MPI ranks to be a good proxy for that. Versus you said, time, so a lot of that data you care about, start with start off with performance data. So you'd have in this case, in fact, you probably have another index. So besides these two are the third we're gonna be . . . no, number of MPI ranks not just each rank, my bad, that's slightly confusing."
  
  - on purpose 

    - part of analysis process
      - P2 describes how the Stats table is in some sense for this purpose
      - P5 talking about the stats table.
      - P6 groups comm versus comp "Essentially, fairly quickly, we kind of grouped computation by type where computation was one type"
      - P6 averages/variances across equivalent runs (noise)
      - P6: "So obviously, you start by looking at the whole thing, right? The entire entirety of the runtime. And then, you know, you start throwing away things that may be irrelevant like IO, you can you can drop IO at different rates, so maybe you shouldn't really consider it as part of your just pure performance study and right."
      - P6: "basically, [MeasurementAPI] tracks, a profile per rank. And then it's doing a reduction step to combine all of that information, and essentially, what ends up so we can specify what it does was the data when it combines it. So for this metadata, who sends to who, I want that appended right, I want the full list for the times."
      - P8: "And so, you know, you run it on many processors, right. So you have a lot of ranks there. And so you get, you know, every rank is going to give you a different time. And these are all, you know, collected and aggregated. And so what you get at these aggregate times, and so you do you get a minimum time for the section of code a max time for the section of code and an average time."
      - P8 calculates dataset-level things like timing/cycle and memory/rank.
      - P9 does multiple line charts across the dimensions not already on an axis
      - P9 "And it would then go and aggregate this across MPI ranks in case you're having an MPI program. So the thing that you're getting out in the end is like minimum, maximum, average and total time per region across MPI ranks. So, that's your final metric." 
  
    - perhaps the point is to do the reductions
      - P6 "And then the computation of the average, in the error bars that that data would end up essentially in the stats frame. Right? Right. So for this plot, I am no longer looking, I start with the individual runs. But for this plot, I'm no longer looking at the individual run. So I'm looking at the data and the stats frame."
    
    - retrieving dimensions/detail
      - P6 discusses needed to drill down for root cause
  
    - to simplify the dataset (in general)
      - P4 "But like, in principle, there's a full spectrum of aggregated data that is kind of profiling a region and just preserving some characteristics that are kind of accumulated over time."
      - P4 "So like this happens on multiple rings, or in multiple processes. So there might be multiple values attached to that. And then for each of the processes, we might be capturing multiple fields of data. And sometimes this data could have a hierarchy of itself. But for most of the data that we are working with, we don't really capture that hierarchy, it's kind of condensed into something that is relatively flat."
      - P4 "So, I mean, I think that the data is hierarchical, is often an artifact, how we are designing systems, and they just tend to be hierarchical, because it's manageable."
      - P7: "And right now, we're just doing basic averaging."
      - P7: "here's a little hard to map it one, one, because, yeah, the multi indexing is a bit different from what you'd normally do in a graph database. In general, normally, in a graph database, you'd have. . . main here, I'm just going to say we have a single profile to get rid of the profile ID to main"
      - P10 "So let's do this first single kernel."
      - also "I do it for a single kernel. Let's see. And I guess in terms of the. . . lets see what I do a single variant, and tuning? I guess you could make this multiple variants and turnings as well."
  
    - practical/technological reasons
      - P4: "So we are using this collapse view because we can still kind of for for a particular call, say like we added a second cog function, we can look at the stack, and then we can aggregate around that, but like, we're doing this mostly because we have to, because we can't afford to, to store like this at the exact granularity that we have in most cases."
      - P6: "To save time, most of the time, we essentially indicate that I would like to know the min, max and average. And so as it essentially collapses it down to these three values where instead of keeping 1000s of values, right, however many ranks you have."
      - P6: "Yep. So there's, there's different averages, right? You're averaging different things at different steps. But yeah, so with [MeasurementAPI], we can essentially request, what data gets output? If you really need the correct data, you can, we would be able to read that into a [EnsembleAPI object]. But I don't think we've tried to read in multiple of these into the get, right, because that's essentially an additional dimension on my data." 

  - unclear if on purpose
    - P8 draws a single call tree already collapsed across all profiles (similar to DatasetAPI)
 



#### Multi-dimensional aspect of ensembles is hard / Ensembles all the way down
    
  - P1: "if you have two CPU four CPU for AWS, and then a two CPU four CPU for LC, then you're kind of in trouble. Because how do you kind of extend, you know, if you've said everything vertically, you kind of, you're getting things mixed up."
  - P2 uses duplication of [EnsembleAPI] objects for Task 2
  - P4: "Also, because it becomes a little bit easier with some of the tooling that we are developing to automate things if there is not additional hierarchy to take care of, because like, each level of hierarchy might be sort of a convention that one has sent to accommodate. So flattening the data, in many cases make things a lot easier to work with."
  - P4: Describning how execution over time is a critical aspect of analysis and not captured by [EsenembleAPI] model "But in principle, so like, I also mentioned that, like this, this perspective on the data is not really capturing what the program is doing the program is having more of a graph structure where like in main you you are calling the post processing, for example, and then it's calling the calculate p. And, like, maybe there's a case where this internally might pause the same calculation function that is also used in another step for example."
  - P5 ends up with multiple objects: "Okay, let's give me please all the "group by"s of MPI ranks, so that I would retrieve like sub-[EnsembleAPI Object]. Only like one example of a [EnsembleAPI Object], but you can get more [EnsembleAPI Object] out of them, by creating sub-[EnsembleAPI Object], because of group by clauses really are similar to databases"
  - P5 "the data frame itself was only like a storage container for data. And it's hard to really read, because there's so much going on. So it's even harder to see like, if there's even behaviors that you are interested in, it's only obviously obvious that some parts take more time. And some take a lot of time. And you don't really get the view behind that."
  - P5 "But right now, I'm having like a lot of steps where I use this data to make some analysis on and all the time you like, have to handle the different [EnsembleAPI Object]  and the different objects and all your calculations again, by yourself. And they kind of get lost in a way."
  - P6 has difficulties adding allocation information
    - "So there's a lot of data that's, that's happening. And also they are sending different amount of data to different processes. And so And also, it's, if you were to measure each send individually, that's going to be a ton of data. So step one, I'm trying to at least record who's sending to who and how much the measuring part is probably not feasible, because you'd have to like, insert more barriers to properly measure it right, which complete completely perturbs things. These are asynchronous asynchronous calls, right. So that's a challenge to measure. But at the very least, I am trying to record which logical process pairs are communicating and how much data they're sending, then I can dump out into the metadata."
  - P6 adds attributes to the call tree nodes separate from the performance table
  - P6: "And then I can compute on it, I can, so let's say I have 10 runs, I can compute the average and whatnot and be provided a storage facility that's essentially an order reduction mechanism, right where you you had 10 times in this function, but now you have a single average, a single variance, what have you, right?"
  - P7 pretty much trying to do all graph database stuff "So this is where it gets tricky with the nodes, because the performance data is a little hard to wrap your head around with the traditional graph database model. I know there are ways to do it, but I don't, I'm not that familiar with graph databases. That's exactly that's how it works."
  - P7 gets fuzzy parts of the model wrong "But you might have, this column might map to -- I don't know why I wrote "perf data" there. Node, that would be nodes. Say "A", your metrics. And then at the end, you might have your ID, your profile ID."
  - P10 on cross-product filter of tuning and variants "But the idea being that we have the tuning and the variant captured within our [EnsembleAPI]  object. Right now, we've been capturing the metadata, or the variant into the metadata. But I think there's this further to this further, more fine grained specification that we're trying to get after where we're putting tuning also into the metadata. So that we can then filter, you know, basically create sub-[EnsembleAPI] that are based on the variant and the tuning together."
  - P10 "it's easy to be able to select or parameterize across the variants. And then right now you basically get all all available tunings for that variant, but it is not the same set of tunings for each variant. And so we really do need, we need the unique, you know, combinations, that is the cross product of those two. "


#### Tension with the casting of the data (TODO: Think about this one)
    
  - P4 is anti-tree, P5 is pro-tree
  - P5 "the data frame itself was only like a storage container for data. And it's hard to really read, because there's so much going on. So it's even harder to see like, if there's even behaviors that you are interested in, it's only obviously obvious that some parts take more time. And some take a lot of time. And you don't really get the view behind that."
  - P7 on what's missing "And that's traces, time series. They're extremely important, especially once you start getting to more state of the art applications, which are a lot of those, again, have to do with the workflow type model, which is very time series dependent."
  - P10 "So the tuning right now is, is in our data, it's actually stored right now on our graph."

#### Problems Constructing a Data Model

  - Diffculties in comparing datasets
    - P4 speaks extensively about comparison basis
    - P5: "So the challenge there was and still is that when we try to measure, take measurements with only one node, we have annotations that do not occur when we have like two nodes. Because a lot of MPI communication is missing, though, we even have completely missing regionals"
  - Analysis Workflows
    - Automated Analysis
      - P4: "So you might want to have tooling that is very capable to automate questions that are commonly asked for for time based optimizations, for example"
      - P6: "This, you would have, you would have your computation much lower for the GPU, right. Which then means that the communication happens a lot more frequently. And I know that, and I can reason about it, but it is, I do not yet know how to represent that in \[EnsembleAPI], the frequency of something occurring, right."
    - Intuiting Workflows
      - P8: "And my, I guess my bigger challenge has been constructing useful workflows from the [EnsembleAPI] object."
  - Need for further dimesions
    - P7: "And that's traces, time series. They're extremely important, especially once you start getting to more state of the art applications, which are a lot of those, again, have to do with the workflow type model, which is very time series dependent."
  - Availability of Data/Metadata
    - P5 "I would fall back to like getting more insights out of the performance counters. But of course, they are completely different. If we compare like, Intel top-down metrics with AMD metrics, Performance Counters, then we have to, then we would have like different counters, and some counters are not available on AMD architectures, and some not available on Intel,"
    - P8: "One of the things that I will say has been a challenge has been or can be metadata. I don't you know, and maybe all of the metadata really is wrapped up in the in the [EnsembleAPI] object."
    - P8: "But but getting metadata out of the [EnsembleAPI] object in a useful way sometimes has has been a challenge"
    - P10: "So I think the piece that we're working through right now is how to capture how I guess where to properly put what [MeasurementAPI] calls these attributes into our [EnsembleAPI] object. 


### Influences on the mental model

#### Data model is tool-dependent

   - P1: "Does it matter in the way I think about it, because I think about it in a [EnsembleAPI] way versus like, a [MeasurementAPI] way or like, it's, I get to choose in what way I want to look at it."
   - P1: "And then, so does it matter whether I look at this through [EnsembleAPI] lens or [DatasetAPI] lens, or yeah, so. . ."
   - P1: (In reference to drawing) "On the left, I just called that "profile one dot [MeasurementAPI]." Because that's how you think about it kind of."
   - P2: "Um, so I mean, there's kind of two parts, there's one part where, when it's well before. . . do you mean, like, when it's like, what the [MeasurementAPI] files are once it's actually loaded into a [EnsembleAPI] with that with our like, what we kind of look at?"
   - P2 talks about [MeasurementAPI] format as messy while pandas format is easier to read/work with, see block starting with "Yeah, I don't I'll describe"
   - P5 (Implying data will come from an annotation-based tool like [MeasurementAPI]) ". . .now we can also look into dependencies between these **annotated regions**."
   - P8 - "Okay, so, so, yeah, the way I think about the staff that and this has been this has really been driven by the tools that I use, it's very hierarchical, right?"
   - P7 - 'their data model' "Again, this is all synthetic, this is the second piece of their data model. We can just do it this way. Then down here."
   - P7 "So this implementation depends a lot on the specific tool you're looking at."
   - P8 "Yeah, I can, it's, it's, it's? Well, I mean, I say I can't, that's, I don't think I've ever thought about it quite like that. It's a kind of think, if I can, can relate this to something that the only thing I can think of is is the, you know, the particular tool that I use to generate the data, right, which is, which is [Lab]'s [[DatasetAPI]] tool, and it generates this, this, it's not what you would think of, in when you think of tree, right?"
   - P8 draws something that looks like output of [DatasetAPI] 
   - P8: "Okay, so, so, yeah, the way I think about the staff that and this has been this has really been driven by the tools that I use, it's very hierarchical, right?"
   - P8: (equates routine with annotation because [MeasurementAPI]) "whatever routine or whatever annotation, the code developer has added to the code. . . to describe what's being timed"
   - P9 describes interactions from [DataExplorationGUI] "And you can look at this in more detail, if you just like hover over this thing, and have your little extra box essentially, is part where you have like, time per call, or no, total time."
   - P9 "in [DataExplorationGUI], I mean, you can click this your first load of thing, it shows you your top region entry, like many. And if you click in there, you can basically go down to any specific hierarchy level, or Yeah, that's the level that you're interested in."

#### Data sourcing is part of the model

  - P1: "[PhysicsCode]'s like one example or like some [BenchmarkSuite] run where you have like time as a column, maybe exclusive time, inclusive time."
  - P2: Draws the initial sourcing from [MeasurementAPI]
  - P4 speaks extensively on all the collection factors of the model, starting with "I mean, it's kind of"
  - P4 "So in that sense, if we are looking at studying performance, for compute optimization, for example, then we will typically try to construct an ensemble that has varying parameters, and would construct the instrumentation so that we are not capturing things that are subject to resource to too much noise or to share resources."
  - P4: "but there's actually a lot of thought that should go into the measurement process to begin with."
  - P4: "And then there's a part of the actual metrics that the instrumentation is gathering. And this is typically constrained by the architectures to an extent. So there's a relationship between the instrumentation and execution environment."
  - P4: Draws the data sourcing
  - P5: Includes [MeasurementAPI] in a flow chart in the drawing
  - P6: "And then for each node in the tree, we are basically recording the the multitude of runs, and the multitude of runs can be all of the runs for this picture. Right. And then you can filter."
  - P7: Draws individual profiles separately as a stack
  - P8: "so a lot of the data is generated, you know, when a code developer or maybe, you know, a code developer at the prompting of a user goes in and says, I want to instrument this section of code, right."

#### Data model is vague

  - P9: "So once you have that you can run this experiment for different numbers of ranks, obviously, you're getting separate data sets for each of these experiments."

#### Data's relation to the domain is part of the model
  
  - P4 speaks extensively on all the collection factors of the model, starting with "I mean, it's kind of"
  - P4 draws the domain, speaks extensively about the application and ties to it throughout
  - P7 "Yeah, those are examples. Exactly what it is depends on the application."

#### Consistency/Commonality (Katy please let me know what you think of these)
  - Looking for common core, something to orient the data around (see [Presence / Commonality](#presence-/-commonality))
    - P4: “there needs to be some common core, because like, the example would be structured about something that has some commonality, and then you will do perturbations to the input parameters or the execution environment like this, there's really no limit to what you could consider that”
    - P1: looking for consistency to orient the mental model of runs, “Because that's a very, like, throughout all the different kinds of data that I work with, there's always nodes.”
     
#### Data is described based on how it is stored

  - P2: "we just take ensembles of data and load them into pandas data frames, and then using those pandas data data frame, perform analysis on that data."
  - P3: "Do you want to know the kind of the structure of the data the way it's stored?"
  - P7: "So this is kind of the high level view a bit more low level, you'll get into like how it's actually organized in memory, and on disk and stuff like that."

#### Data is described based on how it is accessed

  - P1: "Yeah, so I'm just doing a performance data table, kind of because that's the way I think about when I read in a data set, and I'm working with a data set."
  - P4: "for example, they have an instrumentation solution that looks particularly at higher libraries, not so much CPU counters, and we ran into similar analysts problem there because we are dealing with multi dimensional data. And then we have to slice and cut through the data to get like a view that allows for fair comparisons."

#### Data is described based on how it is used

  - P4: "So we would like if we want to do comparative studies to inform maybe the choice of a library or compiler, we would look at multiple measurements of that. And also multiple measurements across different of these input parameters, for example, to see how the behavior and others is changing, in particular, how the performance might improve or degrade, according to that."
  - P4: "for example, they have an instrumentation solution that looks particularly at higher libraries, not so much CPU counters, and we ran into similar analysts problem there because we are dealing with multi dimensional data. And then we have to slice and cut through the data to get like a view that allows for fair comparisons."
  - P4: "So in that sense, if we are looking at studying performance, for compute optimization, for example, then we will typically try to construct an ensemble that has varying parameters, and would construct the instrumentation so that we are not capturing things that are subject to resource to too much noise or to share resources."
  - P5 also trying to recall performance metrics
  - P6: "basically, the study of performance on different machines"
  - P6: "Essentially, some of the questions were, how much noise do we see in those different runs? Is there are the runs on AWS more noisy? And then also comparing the performance? So if you have essentially comparable hardware, you know, on pram, and then in the clouds, do you get the same performance?"
  - P6 evokes model by trying to recall actual results, or at least draw similar graphs to what they have seen. Grounding their choices in prior knowledge.
  
#### Goal Oriented Data Descriptions

  - P9: "One is aggregation, which would basically give you a, well, a profile that you normally get out of applications that we look at where we aggregating things . . . And then we're testing that run
  across a bunch of numbers of threads actually, sort of get only like single process runs, because we're looking only at the local [MeasurementAPI] instrumentation time, but over different numbers of threads."
  - P10: "We might be running it with different versions of [BenchmarkSuite], and understanding the performance of [BenchmarkSuite]. You could be using different compilers in the [BenchmarkSuite] and understanding compiler benefits or performance benefits"

#### Data is described based on analysis workflow

  - P6: "So the error bars were very similar on on machine one and machine two, were once on prem and ones in the cloud. And then I did the exact same thing for communication. And I saw a very different very different picture. . ."

  Maybe bundle some of these following ones v:

#### Tensions with Exact Data and Mental Models
  - Exact Data is not Important
    - P1: "so the data I work with, it's sort of arbitrary as a developer"
    - P1: "the columns themselves are kind of arbitrary"
    - P1: "And then third, probably the profiles. That's the data itself, but it's kind of less important because we have that represented as like an inner index. So it's kind of like, subsequent to the nodes, I guess, in the visualization in my head. So that's where I kind of like, put things even though thinking about is kind of counterintuitive, because without the profiles, you wouldn't have any data."
    - P7: "Again, any parameter really."
  - Use of exact data values and units as part of model
    - P7: "And it could be 1200, 1200 and clang, gcc. And that's the last part of this, is the general, all of this, is the [EnsembleAPI Object]"
    - P7: " . . . we have a single profile to get rid of the profile ID to main, and it would have say, time 50, cache misses, 3, that's one node."
    - P9: "And you want to know what's going on there, essentially. Right. So let's make it five and 20. It's not the numbers, obviously."


#### Structure is not important, it's just about access

  - P9 when pressed about [MeasurementAPI]'s output structure
    - "Well, [MeasurementAPI] to some extent, I mean, kind of can produce a whole range of data sets, right? So it can go from simple profiles like this one to full on."
    - "You're looking at a directory full of [MeasurementAPI] files."
    - "Well, we do have a bunch of different readers."

#### Data's relation to participant's problem

  - P7 "I like connecting it to the [Data Movement Tool] example, as a more practical example. Say the raw data represents all the data we have, for a particular run or a particular consumer in our workflow, we could then run that workflow multiple times, maybe slightly different parameters, get all these profiles for that one consumer, and then pass on this data model and analyze it that way. Using things like one thing that we I'm honestly, currently intending to use, is the query language to strip off all the application specific stuff and just focus on our [Data Movement Tool]."


#### Analysis Task Influences Mental Model or Awareness of Parts

  - P1: (In reference to architecture comparison task): "So that's, that's not in this table"
  - P2: (In reference to architecture comparison task) "Can I ammend my picture real quick? Sorry, I just realized something."




## What is a "part" of the Ensemble?

### Diversity of answers. (Consider splitting and merging around? ^)
  - Column 
    - P1 - "And then the second, probably second biggest part of, of when I'm like doing the ensemble is is going to be the column"
  - Nodes
    - P1 - "the main part or the most important part of the data that I work with is probably the nodes."
  - Profiles
    - P1 - "And then third, probably the profiles. That's the data itself, but it's kind of less important because we have that represented as like an inner index."
    - P7 - "So with  [EnsembleAPI Object], the general premise is you'll have a collection of profiles presenting different runs of a piece of software. "
  - Performance Data
    - P2 - "So it \[ the EnsembleAPI Object ] gets the performance data and metadata."
    - P2 - "then the other part would be the perform performance data, so it's kind of split in a sense there."
    - P3 - "So the first one is the performance data, this is stored in a multi index form"
    - P4 - "And then there's a part of the actual metrics that the instrumentation is gathering"
    - P5 - "So right now, the binaries that we have, is only capable of recording like timestamps, or like, time it took for specific annotated region. So that's all I'm working with right now"
    - P7 - "So you have performance data where you have which is indexed on both your profile ID and your nodes,"
    - P8 - ". But, you know, typically, it consists of something like a minimum time, a max time and an average time"
  - Metadata:
    - P2 -  "So it \[ the EnsembleAPI Object ] gets the performance data and metadata."
    - P2 - ". . . one part is going to be the metadata table where metadata table,"
    - P3 - " . . . there's a second component, which is the metadata"
    - P7 - "There's the metadata frame, which is only indexed on profile ID"
    - As "Runtime Context"
      - P4 - "So like, we have to capture to an extent in the in the data that we have for the [unintelligable], we have to capture the context so that we describe the context to the extent that we can run do the comparisons. So the context includes things like the compiler, libraries, build dependencies, the actual hardware that things are being run on."
    - As "Parameters"
      - P7 - "And those runs can be differentiated by almost any parameter, problem size compiler. Again, any parameter really."
      - P4 - " if we are looking at studying performance, for compute optimization, for example, then we will typically try to construct an ensemble that has varying parameters,"
    - As "Variants" and "Tunings":
      - P10 - "So out of the [BenchmarkSuite], we're wanting to run the kernels across different variants."
      - P10 - "And then I guess within that as well, we have different tunings that exists within the variants that might change the performance as well."
      - P10 - "I think the attributes that we've been thinking about is the tuning is one of them, maybe the variant as another"
  - Statistics
    - P2
    - P3
    - P7
  - Call Graph
    - P3 - "the statistics and the performance data table they also have a call graph component to it"
    - P4 - "we have as a structure in with data from coming from [MeasurementAPI] is typically what is called graph or call tree."
    - P5 - 
    - P7 - ", you load everything up into a single Python based data model, which consists of a graph or 'call tree' or 'call graph,'''
    - P8 - "So, you know, I get this this tree call tree, basically, we want to think about it like that, this call tree of timings, and maybe variances, too."
    - P10 - "so another metric here would be I guess we'll just call this the graph" 
  - Computation & Communication
    - P6 - "And then the communication part was where we were focusing on because that's, that's where we were seeing the noise."
    - P6 - "Essentially, fairly quickly, we kind of grouped computation by type where computation was one type, and we had an expectation of low noise there, always throughout actually, we ignored it"
    - P6 - "that would be that would be become an attribute on the communication node in the call graph."


## What elements of a data mental model are there, perhaps those we don't typically think of as part of data typologies? (e.g., causality between parts of the data) (Connor: Related to the relationships between data ^)

### Related: how do people connect multi-typology data?

  - In this ensemble, people use the nodes of the tree (i.e., the functions of the program) to connect the different datasets
      - P5: call tree/call graph provides context and insight into dependencies
      - "And the great thing about like how [EnsembleAPI] and [DatasetAPI] and altogether works together, is that now we can also look into dependencies between these annotated regions."
      - P5: For the Strong Scaling Study, P5 explained challenges in getting the trees to match so that tools are functional and helpful (e.g. don’t need All_Reduce for 1 thread)
      - P6: "the call tree should be the same or similar across the sets of runs. So we have a single representation of the call tree. And then for each node in the tree, we are basically recording the the multitude of runs, and the multitude of runs can be all of the runs for this picture."
      
      
  - In this ensemble, people use the profileID of the run to multi-index/connect into the different tables
      - P3: "the performance data is the mean data with multiple index and it's connected to to the two of these other tables through two of its indices from the muilt-index."


## Metadata (Connor: Big merging up in here)

  These codes have something to do with metadata.

### What do people consider Metadata?

  - P2: "Because you know, in the metadata, this is where we're kind of, you're kind of mapping the like, the information that you use to kind of run the job."
  - P3: "not strictly performance data, but kind of more information about the execution of the program for each of the profile."
  - P4: "So the context includes things like the compiler, libraries, build dependencies, the actual hardware that things are being run on."
  - P5: "For me, it's only like, we have basically only like nodes to access and row ID of, where the node is, this is all we have in the data frame itself, we need some metadata in order to make good selection of specific nodes that we are interested in. That's the only way I'm using metadata right now."
  - P6: It's what you can form groups by "So you're, you're grabbing, you're looking for machine one and this number of processors, right to to form a little group that you are now averaging and computing you error bars on. Right, and then you grab another one, right? And then you do the same thing for machine two."
  - P6: "you have an entry in your metadata that records all of the all the things you know about that run."
  - P6: "So what we put in the [EnsembleAPI Object] is up to us."
  - P6: "What comes from the metadata is which of the runs were on machine one, right."
  - P7: "There's the metadata frame, which is only indexed on profile ID. And that just contains information again, like compiler, problem size, the things that can differentiate the runs."
  - P8: States that domain specific configurations are not performance metadata
    - "You know, usually when you create and this is why it's not really meta data, that that kind of thing that's more of a you know, you create your mesh and when you create your when you define the problem . . ."
  - P8: "So average time per, in this case cycle, or example or something like that, right? There's could be average time per unknown, for example, right?"
  - P8: "So I consider made metadata to be I guess, sort of what I would call the basic characteristics of the problem."
  - P8: "And so usually what I'm really interested in seeing is something like average time divided by something that's in the metadata, right? So average time per, in this case cycle, or example or something like that, right? There's could be average time per unknown, for example, right? For total number of unknowns, and the problem that we're solving, so that that's usually it usually is average time, but it's not solely average time, it usually has some, you know, usually usually has another component that's buried in the metadata that you know, we're dividing out or something like that."
  - P8 "So I consider made meta data to be I guess, sort of what I would call the basic characteristics of the problem. So these are things like, like I said, architecture may be system name that you ran on a OS may be, but then those are all kind of. They're useful for things like plots and useful for organizing your data, but maybe not very useful for analysis"
  - P10 lists well-known columns specifically as metadata, but has other possible metadata like variants and tunings separated and not explicitly categorized

#### Specific Metadata Examples

  - P3: "information like, who who ran the program, how long, how long the program ran, when the launch date was, all that kind of information."
  - P7: "And that just contains information again, like compiler, problem size, the things that can differentiate the runs"
  - P8: ". . .things like world size, right? For an MPI problem, number of number of processors, number of cores, or maybe number of nodes, right"
  - P9: "the time it was recorded, all the metadata, like the number of threads that we use, the test case name, and other stuff, like compilers, and whatnot"
    

      
### Metadata is hazy.

  - P5 "this might also be really specific to [PhysicsAPI] and that it is a black box. But we get a lot of meta metadata. But it's really like, it's really hard to get an understanding out of that."
  - P6 when trying to figure out how to store allocation information as a list
  - P8: "the thing with the metadata is, it's very hard to predict what you're going to want to look at so . . .you just kind of throw a bunch of stuff in there, here. Here's, here are all the things that I think might be interesting, right? "
  - P8 "I don't think of the metadata really , as I guess, I guess I think of that is a separate piece from the actual timing, tree data, right? Those are kind of two separate things I get, I guess, to me, so the metadata is certainly part of the ensemble just like the timing data, but I kind of I guess, think of those two things as being two different things."
  - P8 "One of the things that I will say has been a challenge has been or can be metadata. I don't you know, and maybe all of the metadata really is wrapped up in the in the [EnsembleAPI] object. And maybe it's just, I just don't know, a good way to pull it out. But but getting metadata out of the [EnsembleAPI]  object in a useful way sometimes has has been a challenge. I don't guess I guess when I really think about it."
  - P10: (after multiple ammendments to drawing to add metadata A1 says:"The evergrowing metadatas")
  - P10: "Right now, we've been capturing  . . .the variant into the metadata. But I think there's this further to this further, more fine grained specification that we're trying to get after where we're putting tuning also into the metadata."



### Metadata is not (the) data.

  - P5 on being asked where it is: "Um, well right now it's kind of, detached in ways"
  - P8: "I guess, to me, so the metadata is certainly part of the ensemble just like the timing data, but I kind of I guess, think of those two things as being two different things."
  - P8: "I don't think of the metadata really, as I guess, I guess I think of that is a separate piece from the actual timing, tree data, right?"
  - P9: "And one thing that's pretty useful is we have like the details, exact amount of times. So for each of the test cases, we have our metadata annotations here, which shows well just, a bunch of things"


### Profiles are the real data. (Proposal: Merge with 'Metadata is not the data')

  - P1: "And then third, probably the profiles. That's the data itself"
  - P1: "without the profiles, you wouldn't have any data."
  - P2: "But you would have that information in the metadata, and then it would go, like the actual outputs, and the metadata."
  - P4: "there's a part of the actual metrics that the instrumentation is gathering"
  - P5: "Then in the background data is used to find all the nodes I'm asking for and the profiles, which was some specific metadata. But honestly, like, right now, I'm only using it to query for stuff, which I know its there but I'm not really using it to explore the application in a way that I know you could use metadata for."
  - P7: "Yeah, so the most important is definitely the performance data. That's your actual stuff, you have to analyze. "
  - P8 "And I, you know, I don't think of the metadata really, as I guess, I guess I think of that is a separate piece from the actual timing, tree data, right? Those are kind of two separate things I get, I guess, to me, so the metadata is certainly part of the ensemble just like the timing data, but I kind of I guess, think of those two things as being two different things."


### Metadata not explicitly stated but implied

  - P1 alludes to knowledge about profiles but not where it lives: " Your profile one would be corresponding to the data set from the run with two CPUs and then profile two correspond to the run with four CPUs"
  - P2 does Task 1 with metadata explicitly but in Task 2 does architecture as separate [EnsembleAPI] objects rather than metadata
  - P9: "the main thing that we're looking at is performance over time"

### Metadata as a reminder for analysis

  - P8 "But you know, the the thing with the metadata is, it's very hard to predict what you're going to want to look at, you know, so when you when you go through the code, you just kind of throw a bunch of stuff in there, here. Here's, here are all the things that I think might be interesting, right?"
    - Also: "kay, well, when I go to sit down and analyze this data, these are the things that I might actually be interested in. But it never fails. When you do that, that you're gonna come across something that well, why didn't I put that in there? Right? Or can I infer that from what I did put in there? And sometimes, yes, sometimes no."

### Assumed Availability of Metadata
  - P6: "And presumably, I should be able to figure out and this is going to be different on all the machines. So I haven't gotten there yet. But I should be able to figure out a mapping from the actual node IDs to the logical MPI ranks. And I should be able to on a per machine basis, figure out how many hops things are away in the actual network"
  - P6: "So on the x axes, I put the number of processes here, or you can think number of nodes, essentially, resources, right."

### Metadata is not really used (even if it is)
  - P5 "Then in the background data is used to find all the nodes I'm asking for and the profiles, which was some specific metadata. But honestly, like, right now, I'm only using it to query for stuff, which I know its there but I'm not really using it to explore the application in a way that I know you could use metadata for."
  - P5 "For me, it's only like, we have basically only like nodes to access and row ID of, where the node is, this is all we have in the data frame itself, we need some metadata in order to make good selection of specific nodes that we are interested in. That's the only way I'm using metadata right now. "
  - P8: [Metadata is not useful except for all these cases where I'm organizing my data by metadata]
    - "Yeah. So I consider made meta data to be I guess, sort of what I would call the basic characteristics of the problem. So these are things like, like I said, architecture may be system name that you ran on a OS may be, but then those are all kind of. They're useful for things like plots and useful for organizing your data, but maybe not very useful for analysis, you know, things that are more interesting for analysis is total memory usage or memory usage per MPI rank, or total number of dofs [degrees of freedom] or or number of dofs per MPI rank, you know, number of elements per MPI rank, or zones, you know, maybe, maybe things like, you know, material composition, that that's really not what I would consider metadata, I guess that that's really something different. You know, total, total execution time, for example, not not broken down, you know, in the tree, but just total overall execution time, I could see that being metadata. That thing, things like that."

### Metadata is Useful
  - P4: "But in certain sense, we always need some basis that we share so that we can do a useful comparison"
  - P6: "AWS does not give us that information, which upsets me. Because I do not know what I get in my allocation or how far things are or what is it right, I do not know anything about the allocation."
  - P7: [How it helps in control task 2] "So then you can use that metadata to help you decide, like reduce or do statistical calculations or visualize and that type of stuff."
  - P10: "So I think we're really interested in the tunings. I think the, you know, the variant helps us identify one kind of level of specificity. But it's really the tunings that we're after to understand how they're performing."

### Metadata can be used for further drilling down

  - P6 suggests looking into timestamsp and allocations
  - P8 "And so usually what I'm really interested in seeing is something like average time divided by something that's in the metadata, right? So average time per, in this case cycle, or example or something like that, right? There's could be average time per unknown, for example, right? For total number of unknowns, and the problem that we're solving, so that that's usually it usually is average time, but it's not solely average time, it usually has some, you know, usually usually has another component that's buried in the metadata that you know, we're dividing out or something like that."
  - P9 "And all that sort of stuff, my compiler, and we're only using it on one compiler and one system for now. But that possibly be an extension to run it on more of those things and compare more data. Right? Yeah. It's good to have actual, like, detailed data, because the differences can be rather subtle. And you want to know what's going on there, essentially."

### Metadata for grouping / operations

  - P7 "those runs can be differentiated by almost any parameter, problem size compiler."
  - P7 "There's the metadata frame, which is only indexed on profile ID. And that just contains information again, like compiler, problem size, the things that can differentiate the runs."
  - P8 "And so usually what I'm really interested in seeing is something like average time divided by something that's in the metadata, right? So average time per, in this case cycle, or example or something like that, right? There's could be average time per unknown, for example, right? For total number of unknowns, and the problem that we're solving, so that that's usually it usually is average time, but it's not solely average time, it usually has some, you know, usually usually has another component that's buried in the metadata that you know, we're dividing out or something like that."
  - P9 "And how it fits me visually, so well. Visually, it fits in that you can well slice through your whole data set by grouping it by different metadata flags. So specifically, I'm grouping it by the different test cases."

### Metadata requires derivation too (Connor: One quote -> Consider Merging)

  - P8 "sometimes I can't remember but it seems like early on there were issues with, with all of the metadata even being there and or having to create a new metadata member that was some, some combination of previously existing metadata. You know, like, well, I like time per cycle, for example, that's not a really a good one, because it's not solely metadata. But but there were there were some there were some cases where it seems like we had to go through some particularly grueling work to get some metadata columns in there that were constructed from from existing metadata, but you know, weren't weren't themselves, you know, there to start with so."

### Williams Metadata codes (Merge and/or create new codes)

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
like, time for instrumentation call, and also, the total runtime after benchmark again… compiler, system”


## Drawing


### Directionality (Connor: Is this 

- (Categorical Metadata -> Horizontal) P1 - "columnar join that we've talked about, but like, so instead of, in the previous case, where you're talking about different different amounts of CPUs, we tend to look at different architectures in a column going horizontally, you could do the same thing."

### Values & Indices

  #### No values
   
    - In table/list
      - P1, P3, P8, P10
    - In plot
      - P6, P9

  #### Example values

    - P2, P4, P5, P7

  #### Indices

    - P1, P2, P3, P5, P7

### Indicators of scale

  #### Uses ellipses to indicate more rows/columns

    - Rows
      - P1, P2, P7
    - Columns
      - P3, P4, P9
    - More Tree
      - P3
    - More profiles
      - P4

#### Uses etc to indicate more columns

    - P1, P3

  #### Uses arrows to indicate more columns

    - P3

  #### Distribution indicator

    - confidence envelope
      - P6 


### Abstractions & Components

  We first discuss the overlal depiction. Then we go into how individual
depictions were presented, including additions to the structure that some
participants used, like depictions of the input.

  #### Main Approach

    Tables were the most prevalent, sometimes with the tree/graph and
sometimes without. There were also more tree-centered value organizations. Two
participants drew line charts representing the data. One participant listed
what attributes went in each structure without making plain any structure
themselves.

    - Just Tables
      - P1, P2
    - Tables & Tree
      - P3, P5, P7
    - Tree w/ values
      - P4, P8
    - Line charts
      - P6, P9
    - Attribute lists
      - P10


  #### Tables

    - Spreadsheet style
      - Relations not shown
        - P9
      - Relations implied by index
        - P1, P2, P3
      - Relations implied by arrows
        - P2, P3
    - Rhomboidal Table that seems to have an implied time component
      - P4

  #### Tree / Graph

    - Indented
      - P3, P4, P5, P8
    - Node-link diagram
      - P7
    - With values
      - plus table
        - P3, P4
      - plus lists of values
        - P8
    - indication links exist
      - P10

  #### Lists of attributes
      
    - P10


  #### Drawing of HPC system

    - P4

  #### Drawing of raw input files

    - P2, P4, P7

  #### Drawing of outcome plot

    - Small multiples
      - P6, P9
    - Single line chart
      - P9
    - Multi-line chart
      - P6


### Connections between tables / structures

  - Implied by index
    - P1, P2
  - Implied by arrows/lines
    - P2, P3, P5
  - Implied by alignment
    - P4


### Drawing Dimensions

#### Dimensions are added by stacking.

  - P9 (stacks charts to show metadata variance)
  - P7 draws stack 

#### Dimensions are added by overplotting.

  - P6 puts multiple lines in one chart
  - P9 puts multiple lines in charts

#### Dimensions are added by duplication.

  - P1 describing Task 2 across architectures
  - P6 doing separate plots for comm and comp
  - P9 doing multiple plots per thread, per benchmark etc

#### Exact Dimensions specified

  - P9 gives tree dimensions in width and depth (verbally)

#### Dimensions shown on axis

  - P4's rhomboidal table


### Concretizing the Data Model when Drawing

#### Using Example Metric Names

  - P1 - "And then along the top, like I described metrics, like time exclusive, throughput cache misses, . . ."
  - P2 - "So like, for example, the performance data, so time, frontend latency, all go into what we call performance data frame, or perf, data DF"
  - P3 - "And then, you know, for performance counters, the time, frontend latency."
  - P7 - "And that just contains information again, like compiler, problem size, the things that can differentiate the runs."

#### Drawing Revision

  - P7: "I'll even even double line here to separate the index and the rest of it, don't know why I drew an arrow there."
  - P10: (In response to question where graph is in initial drawing) "I guess I would call it different, right. So the well, yeah, so the performance data is per kernel. Right? So. And then the graph is obviously all of its all aware of all kernels. Not the performance data, but it's just aware of, you know, who do I Who did I call next, who called me?"

## Controls

Codes and themes centered around the analysis based/task oriented questions

## Strong Scaling Study Task

  - Participants start with performance data, then include metadata.
      - P7: "so a lot of that data you care about, start with start off with performance data. So you'd have in this case, in fact, you probably have another index… So yeah the number of ranks in that case would be part of the metadata...it started with the metadata and performance data, then you go down to the statistics as needed.”
      - P10 uses performance data and metadata to determine time per kernel metric, plot ranks vs time with multiple lines showing different variant and tuning
      - P2 states metadata and performance data, then adds statistics as an afterthought
          * “Because you know, in the metadata, this is where we're kind of, you're kind of mapping the like, the information that you use to kind of run the job.”
      - P1 uses EnsembleAPI to load multiple profiels with differing numbers of threads

  - Participants implicitly describe the metadata but do not explicitly state "metadata" until prompted.
      - P8: KT: Says they need to use metadata (“for example, maybe from, you know, the individual runs in the ensemble… something like cycles…but also certainly things like world size, right? For an MPI problem, number of processors, number of cores, or maybe number of nodes, right?”), then draws a line graph
      - P8: Omits metadata but didn’t realize it. “You know, I actually did omit it? And I, you kow, I don’t think of the metadata really, as I guess, I guess I think of that as a separate piece from the actual timing, tree data, right?”

  - Participants discuss possible reasons for slowdowns
      - P4: “And that in the scheme of iterations that you work through, you are always taking more or less the same time to not waste resources, where all the other resources that are idling, they're still going to maybe consume some energy or they are blocking somebody else that could be doing useful work.”
      
  - P9: visually compare the graphs, side-by-side

### requires perf data and metadata   
  - P2
  - P4 (implied through language)
  - P5 (implied by 'scaling study') but not explicit... more focused on tree
  - P6 (implied through chart)
  - P7
  - P8 (metadata stated, perf data implied), also draws a plot of the results
  - P9 (implied, mentions metadata fields and time)
  - P10 (after adding another field ot the metadata list)

### misses metadata

  - P3

### tries to facet the data more

  - P4
  - P5

  - Participants use runtime metric to determine "better" but need additional data for why
      - P5 likes performance counters to help with the why (behind the runtime)
      
  - Participants need some similarity before comparison (e.g. similar architecture, same code run in different settings, only changing amount of threads but keeping other vars constant) 
      - P4: “But in certain sense, we always need some basis that we share so that we can do a useful comparison.”
      - P4: metrics also need to be comparable. “But it's not always completely possible, because sometimes we don't have the same performance counters. So that is maybe one problem to keep in mind. But considering we have similar performance counters, that we can collect from the systems, then, like, I think the key is that we have the same metrics that we can collect, and then do the runtime analysis.”
      - P3: says to "columnar join" on similar parts of performance data table.
          * "But I think it's called a columnar join. So use parts of the performance data table to kind of make that differences and compare it within the performance data table."
      - P1: also columnar join
      - P10: use Speedup to compare, which is CPU time divided by GPU time

  - Side-by-side
      - P2: side by side tables
      - P1: columnar join (side-by-side tables-esque)
      - P9: side by side graphs
      
      
  - Participants use the metadata to differentiate between the architectures
      * P7: "Kind of the same: “you'd have two systems, they'd be differentiated by, again, this metadata stuff.”
      

  - Participants say comparing two architectures is similar to strong scaling study
      * P8: says program will look similar to the strong scaling study
          * “It is basically going to look exactly like the last, the last response, right? The average time maybe divided by number of cycles, right? And you’ll have how many nodes or cores, whatever your interest added in there, and strong scaling plot of that, which I drew for the last one.”
      * P9: change fields but again, compare graphs side by side

    - P10


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

### requires perf data and metadata

  - P4 (implied thorugh language)
  - P6 (implied through language/similar chart)
  - P7
  - P8 (also notes similarities with Task 1)
  - P9 (also notes similarities with Task 1)

### requires perf data on multiple objects

  - P2

### misses metadata

  - P3


## Low exclusive time, high inclusive time

- Participants find the tree useful
    - P5: “to me personally the data frame is not really useful. It's more like it transportation layer to compute a visual view onto what's going on. So my first step would probably be to look into the tree side by side with, on one side, you have exclusive time. And on the other [. . .], you will have exclusive time. So that you actually come up with like, there is a difference, I think that would help me”
    - P7: uses the tree and performance data --> “then you'd pretty much just have to do a walk traversal of that subtree or sub graph.”
    - P4: traverse the tree “Yeah, I'm still not completely sure if I may have missed the core of the question, because for me, it's like, I don't know, like, I can kind of trust the instrumentation. And then I can just traverse the tree and kind of pick out the elements that I think are contributing to that.”
    - P6: looks at a hierarchy, but the tool they use doesn't distinguish between inclusive and exclusive time?
    - P10: “Let’s start with the tree.” Also query language to filter the tree, “if I knew which node had so I guess, you know, first step, I would still be printing the tree probably. And once I had identified what node, let me just assume one node has the high inclusive time I would use that query language with the kernel being the root node, and then just grab everything underneath it...down to the leaf nodes."

- Particpants draw tables of the times
    - P4 draws table

### requires the call tree
  - P3, P4, P5, P6, P8, P9, P10

### If I want to find out which function called another function, what portion of the data would be most important for that? 

- P3: Call tree, “we have a very basic implementation of queries.”


## ABC Tree

### draws some form of tree

  - P2 (on clarification)
  - P4
  - P5
  - P6
  - P7
  - P8
  - P9
  - P10

### casts the questions into the data they work with

  - P2

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
          
    - P3 (though clarifies they are related and says it doesn't have to be a
      table)


### Visualizing and Identifying patterns in ensemble data
  - P1: " And then the more profiles you have, you just be able to visualize more of that. Those patterns happening as you have no more to more data points to kind of extrapolate?"


#### Appropriate Data for X and Y Axes (I think there is more evidence of this)
  - P6: y = metric/dependent variable "And on the y axis, it's time."
  - P6: X = metadata/indpendent variable "So on the x axes, I put the number of processes here, or you can think number of nodes, essentially, resources, right."

#### Appropriate Visualizations for Ensemble Data

  - P2: "So like performance data table, multiple profiles, you can look at, like, say, a box plot. So kind of a variation."
  - P6 Frames their discussion of the data solely with visualizations; using line charts with error bars. Their model is primarily based around analysis and visualizations.
  - P7: "Box and Whisker is a common one that I've seen for also, I've seen them, the line plots with like shaded region on either side, indicate kind of how it varies between runs, if they just depends on what you want to do with it."
  - P7: "If so, that would be if you want to more statistical if you wanted it in other ways mean, some of the things that were useful is of course, plotting. So have your, your MPI ranks on the x axis time on the right. If you just had one run at each MPI rank, each MPI scale, you'd probably just do a line plot"
  - P9: Describes ideal analysis conditions in the context of a stacked area chart visualization
    - "And then will you get your own little curve, which looks like sort of this and hopefully more like this?"



## Tree Observations

### Using tree to relate functions/code to performance data

  - P5: Feeds performance metrics into the stats table for insight, but then the tree helps provide further insight
      * “And then we present into another data frame, where now we have a statistical view onto our, like, raw data set. And then this helps to this really helps with visualization, again, was a tree.”
    
### Using tree for hierarchy, relationships between functions

  - P4: Uses "call graph", "call tree", and "call stack" yet understands the nested nature of the call tree and placing the timing data/profiling data onto the tree?
      * “And then for each of the processes, we might be capturing multiple fields of data. And sometimes this data could have a hierarchy of itself. But for most of the data that we are working with, we don't really capture that hierarchy, it's kind of condensed into something that is relatively flat…So flattening the data, in many cases make things a lot easier to work with.”
  - P8: calls tree a hiearchy but does not state the relationship between the nodes or indicate why it's a hierarchy

### Difficulty in concisely/accurately describing the tree

  - P8: doesn’t remember the word node (“for each, I guess, leaf is not the right word.”)
      - Has difficulty describing the tree, “So, you know, function name, where you have a routine name or something like that, and then you have your timing data, and you have that for every level in the tree basically...I don’t think I’ve ever thought about it quite like that.”
      - In low exclusive/high inclusive question, P8 refers to the tree but also calls it a hierarchy
          * “Right, that that really does come all down to the tree. And, you know, we see that quite frequently. Um, but yeah, that that, that all comes down to the hierarchy.”


## Uncategorized as-of-yet observations

### Balanced node-link diagrams are trees, accept no substitutions

  - P6 until needing to add data
  - P8 "the particular tool that I use to generate the data, right, which is, which is [Lab]'s [[DatasetAPI]] tool, and it generates this, this, it's not what you would think of, in when you think of tree, right?"
  - P9 "Now I can use my favorite little [MeasurementAPI] tree print out, essentially, which is not really very graphic"

### Dangers of test dataset ([BenchmarkSuite]) (Connor: Needs to go into the ensembles is hard part)

  - does not seem to understand nodes are functions instead of applications
    - P1, P2
      - P2 "ut when I think nodes, I would think, like more like application, so there's like, an app here, the app here, and then when you run these applications, you know, you get, say, like for these two applications, there's ya know time for them."
    - P3 exhibits this to some extent though they are aware of the call tree
    - P10 lists variants/tunings separately from metadata during drawing
    - P10 "And based on the set of kernels that we're running in [BenchmarkSuite] are the type of kernel that we're running in [BenchmarkSuite]. You might have tuning or sorry, you might have default tuning and some, not in others, you might get the library that's being run, but not in others. So it's very, I guess we haven't yet figured out or uncovered, which tunings exist for what types of kernels?"

### Describing indices / database terms (Connor: How data parts are related merge maybe)
  
  - P3: "the performance data, this is stored in a multi index form"
  - P3: "And it's going to the first table, which is the performance data table with with that profile hash that we just talked about. So it's like a foreign key for for that table."
  - P3: "performance data is acts as sort of the main table, if you look at it from a relational database management system, our relational database management model"
  - P5 uses the term 'view' but not in a vis way.
  - P7 talks about indexing extensively
  - P7 "In a way [EnsembleAPI Object] is almost just like a, it's really almost as like a graph database to be honest."
  - P7: "So you have performance data where you have which is indexed on both your profile ID and your nodes. . ."
  - P7: "Even if you don't deal with the graph as a database, all of this is like this is literally a relational database. These are just the statistics about data forms. It's a relational database."
    
#### Drawing Anxiety/Test Anxiety

  - P1: "Yeah, so, I'm not an artist, but I think you'll probably get the idea", "Did I do good?"
  - P3: "Yeah, my handwriting is not the best, but this helps"
  - P4: "Okay, yeah, this is kind of tricky. It has potential to get very messy."
  - P5: "I'm really bad with drawing and let's try to come up as we go"
  - P6: "Did I pass?"


### Desire for context (Connor: Into limitations of ensemble structure)

  - P4: "I think there's this care the assumptions that you have to do in how you are setting up the measurements for your sample."
  - P6: "so for example, so I guess I was trying to describe CPU versus GPU. And I basically kept saying, This stays the same. This, you would have, you would have your computation much lower for the GPU, right. Which then means that the communication happens a lot more frequently. And I know that, and I can reason about it, but it is, I do not yet know how to represent that in ticket, the frequency of something occurring, right. So technically, I should be able to, just by that knowledge, right, I could divide this time by 10. Knowing that that's what happens, right? And then the total time would be less, right. But what I'm interested in as the person, you know, how frequently the communication happens, and the proportion of time it's taking. And actually, I liked that it would be the same. It wouldn't be the same notionally, except if you are communicating 10 times as often in the amount of data hasn't changed, right, the rest, the rest has not changed. You're creating more contention. And I don't yet know how to think about it in those terms."
  - P6: "So it's sort of like, you know, I will measure the communication time, just like I did on the CPUs, and I will get fairly similar graphs, they will probably go up a little because of the contention. But it's going to be difficult for me to draw that conclusion, just from the data. It's only because I know that's right. So I don't know, that that's clearly. I guess that's what I don't know, it's like you would have that data, right. But arriving at that conclusion, it's not clear to me that we have the means to arrive at that conclusion just from the data or you still need the human that understands that there is more traffic on the network, of course it's slower. "
  - P8: "Because you know, for example, rank zero, is almost always going to be slightly higher, or maybe consistently, then all the other ranks depending on what's going on, you know, MPI wise, and all kinds of things. So, but that was one that that for sure, was missing, that we needed. . ."
  - P10 " don't know. So [BenchmarkSuite] is the different kernels and [BenchmarkSuite] are being contributed by various people within the code teams. And I'm not sure if it's on the code, the person who is contributing the kernel to implement the different tunings, or if they just implement, you know, one version of their kernel. And then one of the maintainers of the [BenchmarkSuite] team is what implements the different tunings. Im not understood, I'm not sure yet how those two interplay. So I don't know that piece."

### Projecting Additional Information Into Control Tasks (TODO: Should go somewhere)

  - P4: [P4 Has a lot of this across the tasks] "I think I have an MPI application that has multiple ranks, then each of the ranks is, is going to take some time. So like, the application has to spawn some startup time, which might not even be accounted for in the instrumentation that we have, depending on how we do it."
  - P6: "And then, you know, you start throwing away things that may be irrelevant like IO, you can you can drop IO at different rates, so maybe you shouldn't really consider it as part of your just pure performance study and right."
  - P7: [Task 1] "So you'd have in this case, in fact, you probably have another index."

### Data Scale/Granularity (Connor: Move up ^)

  - P8: "And not just, you know, it might be nice to look at one individual, but really, this is this is really more about the ensemble than it is any single individual."

### Refrences to Ensemble Analysis (Validation -> Somewhere with the ensemble stuff at the top ^)

  - P4: "And also multiple measurements across different of these input parameters, for example, to see how the behavior and others is changing, in particular, how the performance might improve or degrade, according to that."
  - P8: "And so, you know, we do an ensemble of runs, typically, you know, I don't know, five or 10 different runs, right. Really important, especially for the cloud"

### Profile Level Metrics are Metadata (^Connor: Can merge up in metadata somewhere)

  - P8: "You know . . . just total overall execution time, I could see that being metadata."

### Retrieving data (^ Connor: merge up to limitations)

  - P8 " Um, and so part part of this is, is a little bit whether some, for some things, it's going to be hard for me to say, is this really captured by the [EnsembleAPI]  object? Or is it just the case that I don't know how to get it out?"

### How do people keep track of their analysis? (Merge Opportunity)

  - P5 wishes for a history of analysis
      - “But right now, I'm having like a lot of steps where I use this data to make some analysis on and all the time you like, have to handle the different [EnsembleAPI Object] and the different objects and all your calculations again, by yourself. And they kind of get lost in a way... But like after 20 notebook cells, you really get lost with what's going on where and, like, what I'm missing is like, not a [EnsembleAPI Object] object, but like a container, where you can add all your analysis to in a ways that this is also carrying some metadata for you to allow to, like, get back some specific analysis that you're done, like, two weeks prior that way.”


### Ensemble Analysis in Performance Analysis (Merge Opportuinity)

  - P5: And we also want to make different measurements, with different runs. Because of course, conditions in HPC can vary a lot, depending on node placement, or noisy neighbors, or whatever.
  - P6: Is there are the runs on AWS more noisy? And then also comparing the performance? So if you have essentially comparable hardware, you know, on pram, and then in the clouds, do you get the same performance? So that included basically lots of repeat runs to do attempt to tackle the noise question and runs at different scales to to attempt to see the difference in performance.
