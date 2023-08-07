Conventions
===========

During early stages, please add recklessly. Possible dupes are okay. We will
split/merge in later rounds through discussion/affinity diagramming etc.

## Themes are written as first-level headers
  - Codes are written as next level, subcodes as the following level
  - Evidence is listed as bullet points, ideally quotes but at least
    references to participants.

Themes & Codes
==============

## Ensemble Elephants

These codes have something to do with the mental model of the data. This
probably needs to be split or at least made hierarchical at some point, but
for now let's put everything here.


### What is an ensemble?
  - Multiple profiles 
    - P1: "Purposely multiple profiles of data as in comparison to [DatasetAPI], where it may be only or usually is only one profile?"
    - P3: "we allow multi runs, multi run performance data, which is basically multiple profiles to be stored into an object."
    - P5: "It's also a good idea to have multiple rounds in order to model anything, basically, this also helps us in a way that we can take, like 10 rounds, and then we would have two profiles, we would generate a stats frame for that have like an aggregated or statistical relevant view on the data that we have."
  - Examples of different things to collect
    - P4: "for the performance data, we are basically dealing with different programs, executions, and there's different these programs are instrumented and they typically collect different performance counters, these might be exposed to the CPU, these can be software counters that are kind of made up just for the purpose of a special investigation into some performance question"
      - Also: "And typically the applications we are working with, and they will be implemented this way, they do have a few parameters of themselves."
      - "And we are working on different architectures and platforms. And this leads to these counters being expressed differently."
    - P5 also lists possible data to collect
  - Hazy / Flexible
    - P4: "I tend to be very flexible and fuzzy in the definition there, because my experience has just said, it doesn't even make too much sense to constrain it so so much."
    - P4: "So there's a few different structures to data, but I think this is two things that I've commonly seen."
  - Multidim
    - P4: "But it's basically a multi dimensional space of, of parameters to care about."
    - P4: "I think it makes sense to look what is kind of distributed across the MPI ranks. And typically, we have some application domains. So this might be a volume or space."


### Pieces of the EnsembleAPI were forgotten.
  - For each participant and each EnsembleAPI piece, list when, if ever, the
    participant alluded to the piece and how. 
  - For this code, there are four pieces: Performance Data, Metadata, Stats
    Data, and Call Tree (Call Graph).
  - For this code, there are four places it can appear: initial verbal
    question, drawing, tasks, and never. It may be useful to mark when
something appeared in one but was later forgotten.
  - P1
    - Performance data: 
      - Spoken
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
     - Drawn

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

### The Data Hierarchy

#### Measured data/metrics/dependent variables is most important
- P2: "performance data as the most important piece of the ensemble data, just because most of the work that I do is on the performance side"
- P3: "performance data is acts as sort of the main table"
- P7: "Yeah, so the most important is definitely the performance data."

### Ensemble data structure pieces are linked structurally

  - P1, P2 (drawing, speaking), P3 (drawing, speaking)
  - P4: "we're nesting multiple contexts into each other"
  - P5: Draws arrows from perf frame to stats frame and stats frame to tree
  - P2: Two parts share a similar structure "So \[the stats table] is kind of the same kind of format as the performance table."
  - P3: "And it's going to the first table, which is the performance data table with with that profile hash that we just talked about. So it's like a foreign key for for that table."
  - P3: ".You can see the relationship between these is through the profiles the profile hash."
  - P7: "So you have performance data where you have which is indexed on both your profile ID and your nodes, that contains your actual metrics, the data, so time memory usage, stuff like that. There's the metadata frame, which is only indexed on profile ID."



### Ensemble data structure pieces are linked meaningfully
  -  P1 ". Your profile one would be corresponding to the data set from the run with two CPUs and then profile two correspond to the run with four CPUs, and then you'd see in your times, well, you should see that the time for profile one is gonna be higher than the time for profile two, because it had more CPUs"
  - P2 "Obviously, they kind of affect each other, like, in some kind of formats, because, you know, certain metadata like compilier optimization, things like that will directly affect the values 
  - in the performance data table."
  - P5: ". . .the data frame is not really useful. It's more like it transportation layer to compute a visual view onto what's going on."
  - P5 "And the great thing about like how [[EnsembleAPI]] and [[DatasetAPI]] and altogether works together, is that now we can also look into dependencies between these annotated regions."

### Influences on importance

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

  #### What leads to insight

    - P2: "I think, you know, with what we're kind of working towards on the project, performance data kind of provides insights into your data. More, so I think then possibly metadata does because you can, you know, perform correlations, perform time series analysis and things like that. So you can kind of get a much better insight, in my opinion, using the performance data rather than the metadata."
    - P4: "I think it boils down to the question that you're investigating what is important, and that basically informs us the granularity I was mentioning, but also the parameters that you are capturing."
    - P4: "If you want to optimize for energy to solution, then you have to look for for different metrics, and even some things that we are not currently capturing. But it really depends on the objectives that you want to take into account."
    - P7: "Yeah, so the most important is definitely the performance data. That's your actual stuff, you have to analyze."
    - P8: "the timing data is, is is very general, right, you can do a whole lot of things with that, depending on what you're trying to, you know, get out of the ensemble, right all kinds of different things,"
    - P10: "But it's really the tunings that we're after to understand how they're performing."

  #### Feature maturity

    - P3: "And then once we talk about the entire table, I bring the call call tree because that's a functionality we're still working on. And making sure like changes can be propagated to that data structure. So it's still a work in progress compared to the tables."

  #### Easy to understand

    - P5: "So right now my favorite favorite metric, I say, because like I guess, so it's really easy to understand what you want to optimize for, because you're obviously looking for the lowest runtime."


### Participants dropped or reduced dimensions of the data.
  
  - by accident
  - on purpose
    - P2 describes how the Stats table is in some sense for this purpose
    - P4 "But like, in principle, there's a full spectrum of aggregated data that is kind of profiling a region and just preserving some characteristics that are kind of accumulated over time."
    - P4 "So like this happens on multiple rings, or in multiple processes. So there might be multiple values attached to that. And then for each of the processes, we might be capturing multiple fields of data. And sometimes this data could have a hierarchy of itself. But for most of the data that we are working with, we don't really capture that hierarchy, it's kind of condensed into something that is relatively flat."
    - P4 "So, I mean, I think that the data is hierarchical, is often an artifact, how we are designing systems, and they just tend to be hierarchical, because it's manageable."
    - P4: "So we are using this collapse view because we can still kind of for for a particular call, say like we added a second cog function, we can look at the stack, and then we can aggregate around that, but like, we're doing this mostly because we have to, because we can't afford to, to store like this at the exact granularity that we have in most cases."
    - P5 talking about the stats table.

### Multi-dimensional aspect of ensembles is hard / Ensembles all the way down
  
  - P1: "if you have two CPU four CPU for AWS, and then a two CPU four CPU for LC, then you're kind of in trouble. Because how do you kind of extend, you know, if you've said everything vertically, you kind of, you're getting things mixed up."
  - P2 uses duplication of [EnsembleAPI] objects for Task 2
  - P4: "Also, because it becomes a little bit easier with some of the tooling that we are developing to automate things if there is not additional hierarchy to take care of, because like, each level of hierarchy might be sort of a convention that one has sent to accommodate. So flattening the data, in many cases make things a lot easier to work with."
  - P5 ends up with multiple objects: "Okay, let's give me please all the "group by"s of MPI ranks, so that I would retrieve like sub-[EnsembleAPI Object]. Only like one example of a [EnsembleAPI Object], but you can get more [EnsembleAPI Object] out of them, by creating sub-[EnsembleAPI Object], because of group by clauses really are similar to databases"
  - P5 "the data frame itself was only like a storage container for data. And it's hard to really read, because there's so much going on. So it's even harder to see like, if there's even behaviors that you are interested in, it's only obviously obvious that some parts take more time. And some take a lot of time. And you don't really get the view behind that."
  - P5 "But right now, I'm having like a lot of steps where I use this data to make some analysis on and all the time you like, have to handle the different [EnsembleAPI Object]  and the different objects and all your calculations again, by yourself. And they kind of get lost in a way."


### Tension with the casting of the data
  
  - P4 is anti-tree, P5 is pro-tree
  - P5 "the data frame itself was only like a storage container for data. And it's hard to really read, because there's so much going on. So it's even harder to see like, if there's even behaviors that you are interested in, it's only obviously obvious that some parts take more time. And some take a lot of time. And you don't really get the view behind that."


### Differences between ensemble makes things hard

  - P4 speaks extensively about comparison basis
  - P5 "So the challenge there was and still is that when we try to measure, take measurements with only one node, we have annotations that do not occur when we have like two nodes. Because a lot of MPI communication is missing, though, we even have completely missing regionals because obviously, like you don't need an all reduce with only one MPI rank. So these nodes are then missing."
  - P5 "I would fall back to like getting more insights out of the performance counters. But of course, they are completely different. If we compare like, Intel top-down metrics with AMD metrics, Performance Counters, then we have to, then we would have like different counters, and some counters are not available on AMD architectures, and some not available on Intel,"



### Influences on model

#### Data model is tool-dependent

   - P1: "Does it matter in the way I think about it, because I think about it in a [EnsembleAPI] way versus like, a [MeasurementAPI] way or like, it's, I get to choose in what way I want to look at it."
   - P1: "And then, so does it matter whether I look at this through [EnsembleAPI] lens or [DatasetAPI] lens, or yeah, so. . ."
   - P1: (In refrence to drawing) "On the left, I just called that "profile one dot [MeasurementAPI]." Because that's how you think about it kind of."
   - P2: "Um, so I mean, there's kind of two parts, there's one part where, when it's well before. . . do you mean, like, when it's like, what the [MeasurementAPI] files are once it's actually loaded into a [EnsembleAPI] with that with our like, what we kind of look at?"
   - P2 talks about [MeasurementAPI] format as messay while pandas format is easier to read/work with, see block starting with "Yeah, I don't I'll describe"
   - P5 (Implying data will come from an annotation-based tool like [MeasurementAPI]) ". . .now we can also look into dependencies between these **annotated regions**."
   - P8 - "Okay, so, so, yeah, the way I think about the staff that and this has been this has really been driven by the tools that I use, it's very hierarchical, right?"

#### Data sourcing is part of the model

   - P1: "[PhysicsCode]'s like one example or like some [BenchmarkSuite] run where you have like time as a column, maybe exclusive time, inclusive time."
   - P2: Draws the initial sourcing from [MeasurementAPI]
   - P4 speaks extensively on all the collection factors of the model, starting with "I mean, it's kind of"
   - P4 "So in that sense, if we are looking at studying performance, for compute optimization, for example, then we will typically try to construct an ensemble that has varying parameters, and would construct the instrumentation so that we are not capturing things that are subject to resource to too much noise or to share resources."
   - P4: "but there's actually a lot of thought that should go into the measurement process to begin with."
   - P4: "And then there's a part of the actual metrics that the instrumentation is gathering. And this is typically constrained by the architectures to an extent. So there's a relationship between the instrumentation and execution environment."
   - P4: Draws the data sourcing
   - P5: Includes [MeasurementAPI] in a flow chart in the drawing

  #### Data's relation to the domain is part of the model
   - P4 speaks extensively on all the collection factors of the model, starting with "I mean, it's kind of"
   - P4 draws the domain, speaks extensively about the application and ties to it throughout

#### Data is described based on how it is stored

- P2: "we just take ensembles of data and load them into pandas data frames, and then using those pandas data data frame, perform analysis on that data."
- P3: "Do you want to know the kind of the structure of the data the way it's stored?"

#### Data is described based on how it is accessed

- P1: "Yeah, so I'm just doing a performance data table, kind of because that's the way I think about when I read in a data set, and I'm working with a data set."
- P4: "for example, they have an instrumentation solution that looks particularly at higher libraries, not so much CPU counters, and we ran into similar analysts problem there because we are dealing with multi dimensional data. And then we have to slice and cut through the data to get like a view that allows for fair comparisons."

#### Data is described based on how it is used

- P4: "So we would like if we want to do comparative studies to inform maybe the choice of a library or compiler, we would look at multiple measurements of that. And also multiple measurements across different of these input parameters, for example, to see how the behavior and others is changing, in particular, how the performance might improve or degrade, according to that."
- P4: "for example, they have an instrumentation solution that looks particularly at higher libraries, not so much CPU counters, and we ran into similar analysts problem there because we are dealing with multi dimensional data. And then we have to slice and cut through the data to get like a view that allows for fair comparisons."
- P4: "So in that sense, if we are looking at studying performance, for compute optimization, for example, then we will typically try to construct an ensemble that has varying parameters, and would construct the instrumentation so that we are not capturing things that are subject to resource to too much noise or to share resources."

  #### Exact data is not important

    - P1: "so the data I work with, it's sort of arbitrary as a developer"
    - P1: "the columns themselves are kind of arbitrary"
    - P1: "And then third, probably the profiles. That's the data itself, but it's kind of less important because we have that represented as like an inner index. So it's kind of like, subsequent to the nodes, I guess, in the visualization in my head. So that's where I kind of like, put things even though thinking about is kind of counterintuitive, because without the profiles, you wouldn't have any data."

#### Analysis Task Influences Mental Model or Awareness of Parts
- P1: (In reference to architecture comparison task): "So that's, that's not in this table"
- P2: (In reference to architecture comparison task) "Can I ammend my picture real quick? Sorry, I just realized something."

### What factors lead to remembering dimensions/aspects of the data?

KT: P6 trying to recall actual results, or at least draw similar graphs to what they have seen. Grounding their choices in prior knowledge.
    - P5 also trying to recall performance metrics
 
- Looking for common core, something to orient the data around
    - P4: “there needs to be some common core, because like, the example would be structured about something that has some commonality, and then you will do perturbations to the input parameters or the execution environment like this, there's really no limit to what you could consider that”
    - P1: looking for consistency to orient the mental model of runs, “Because that's a very, like, throughout all the different kinds of data that I work with, there's always nodes.”


## What is a "part" of the Ensemble? 
### Diversity of answers.
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

## What elements of a data mental model are there, perhaps those we don't typically think of as part of data typologies? (e.g., causality between parts of the data)

### Related: how do people connect multi-typology data?

- In this ensemble, people use the nodes of the tree (i.e., the functions of the program) to connect the different datasets
    - P5: call tree/call graph provides context and insight into dependencies
    - "And the great thing about like how [EnsembleAPI] and [DatasetAPI] and altogether works together, is that now we can also look into dependencies between these annotated regions."
    - P5: For the Strong Scaling Study, P5 explained challenges in getting the trees to match so that tools are functional and helpful (e.g. don’t need All_Reduce for 1 thread)
    - P6: "the call tree should be the same or similar across the sets of runs. So we have a single representation of the call tree. And then for each node in the tree, we are basically recording the the multitude of runs, and the multitude of runs can be all of the runs for this picture."
    
    
- In this ensemble, people use the profileID of the run to multi-index/connect into the different tables
    - P3: "the performance data is the mean data with multiple index and it's connected to to the two of these other tables through two of its indices from the muilt-index."

## Metadata

These codes have something to do with metadata.

### What is Metadata?

  - P2: "Because you know, in the metadata, this is where we're kind of, you're kind of mapping the like, the information that you use to kind of run the job."
  - P3: "not strictly performance data, but kind of more information about the execution of the program for each of the profile."
  - P4: "So the context includes things like the compiler, libraries, build dependencies, the actual hardware that things are being run on."
  - P5: "For me, it's only like, we have basically only like nodes to access and row ID of, where the node is, this is all we have in the data frame itself, we need some metadata in order to make good selection of specific nodes that we are interested in. That's the only way I'm using metadata right now."

		
### Metadata is hazy.

  - P5 "this might also be really specific to [PhysicsAPI] and that it is a black box. But we get a lot of meta metadata. But it's really like, it's really hard to get an understanding out of that."


### Metadata is not (the) data.

  - P5 on being asked where it is: "Um, well right now it's kind of, detached in ways"


### Profiles are the real data.

  - P1: "And then third, probably the profiles. That's the data itself"
  - P1: "without the profiles, you wouldn't have any data."
  - P2: "But you would have that information in the metadata, and then it would go, like the actual outputs, and the metadata."
  - P4: "there's a part of the actual metrics that the instrumentation is gathering"
  - P5: "Then in the background data is used to find all the nodes I'm asking for and the profiles, which was some specific metadata. But honestly, like, right now, I'm only using it to query for stuff, which I know its there but I'm not really using it to explore the application in a way that I know you could use metadata for."


### Metadata not explicitly stated but implied

  - P1 alludes to knowledge about profiles but not where it lives: " Your profile one would be corresponding to the data set from the run with two CPUs and then profile two correspond to the run with four CPUs"
  - P2 does Task 1 with metadata explicity but in Task 2 does architectuer as separate [EnsembleAPI] objects rather than metadata

### Metadata as a reminder for analysis
- P8 

### Metadata is not really used (even if it is)

  - P5 "Then in the background data is used to find all the nodes I'm asking for and the profiles, which was some specific metadata. But honestly, like, right now, I'm only using it to query for stuff, which I know its there but I'm not really using it to explore the application in a way that I know you could use metadata for."
  - P5 "For me, it's only like, we have basically only like nodes to access and row ID of, where the node is, this is all we have in the data frame itself, we need some metadata in order to make good selection of specific nodes that we are interested in. That's the only way I'm using metadata right now. "



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


## Drawing

### Directionality
- (Categorical Metadata -> Horizontal) P1 - "columnar join that we've talked about, but like, so instead of, in the previous case, where you're talking about different different amounts of CPUs, we tend to look at different architectures in a column going horizontally, you could do the same thing."
### Scale is implied

### Indicators of scale

#### Uses ellipses to indicate more rows

- P1, P2

#### Uses etc to indicate more columns

- P1
- 
### Dimensions are added by stacking.

### Dimensions are added by overplotting.

### Dimensions are added by duplciation.
- P1 describing Task 2 across architectures

### Concretizing the Data Model when Drawing

#### Using Example Metric Names
- P1 - "And then along the top, like I described metrics, like time exclusive, throughput cache misses, . . ."
- P2 - "So like, for example, the performance data, so time, frontend latency, all go into what we call performance data frame, or perf, data DF"
- P3 - "And then, you know, for performance counters, the time, frontend latency."
- P7 - "And that just contains information again, like compiler, problem size, the things that can differentiate the runs."

#### Using example Data
- P7 -
## Controls

  ## Task 1 

  ### requires perf data and metadata

- P2
- P4 (implied through language)
- P5 (implied by 'scaling study') but not explicit... more focused on tree

  ### misses metadata

    - P3

  ### tries to facet the data more

    - P4
    - P5
### Comparing two architectures

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

  ## Task 2 

  ### requires perf data and metadata

    - P4 (implied thorugh language)

  ### requires perf data on multiple objects

    - P2

  ### misses metadata

    - P3


### Low exclusive time, high inclusive time

- Participants find the tree useful
    - P5: “to me personally the data frame is not really useful. It's more like it transportation layer to compute a visual view onto what's going on. So my first step would probably be to look into the tree side by side with, on one side, you have exclusive time. And on the other [. . .], you will have exclusive time. So that you actually come up with like, there is a difference, I think that would help me”
    - P7: uses the tree and performance data --> “then you'd pretty much just have to do a walk traversal of that subtree or sub graph.”
    - P4: traverse the tree “Yeah, I'm still not completely sure if I may have missed the core of the question, because for me, it's like, I don't know, like, I can kind of trust the instrumentation. And then I can just traverse the tree and kind of pick out the elements that I think are contributing to that.”
    - P6: looks at a hierarchy, but the tool they use doesn't distinguish between inclusive and exclusive time?
    - P10: “Let’s start with the tree.” Also query language to filter the tree, “if I knew which node had so I guess, you know, first step, I would still be printing the tree probably. And once I had identified what node, let me just assume one node has the high inclusive time I would use that query language with the kernel being the root node, and then just grab everything underneath it...down to the leaf nodes."



- Particpants draw tables of the times
    - P4 draws table

  ## Task 3 

  ### requires the call tree

    - P3, P4, P5
	
### If I want to find out which function called another function, what portion of the data would be most important for that? 

- P3: Call tree, “we have a very basic implementation of queries.”

  ## ABC Tree

  ### draws some form of tree

    - P2 (on clarification)
    - P4
    - P5
  
  ### draws a table

    - P3 (though clarifies they are related and says it doesn't have to be a
      table)

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

   

## How do people keep track of their analysis?

- P5 wishes for a history of analysis
    - “But right now, I'm having like a lot of steps where I use this data to make some analysis on and all the time you like, have to handle the different [EnsembleAPI Object] and the different objects and all your calculations again, by yourself. And they kind of get lost in a way... But like after 20 notebook cells, you really get lost with what's going on where and, like, what I'm missing is like, not a [EnsembleAPI Object] object, but like a container, where you can add all your analysis to in a ways that this is also carrying some metadata for you to allow to, like, get back some specific analysis that you're done, like, two weeks prior that way.”


## Uncategorized as-of-yet observations

  ### Balanced node-link diagrams are trees, accept no substitutions

  ### Dangers of test dataset ([BenchmarkSuite])

- does not seem to understand nodes are functions instead of applications
	- P1, P2
		- P2 "ut when I think nodes, I would think, like more like application, so there's like, an app here, the app here, and then when you run these applications, you know, you get, say, like for these two applications, there's ya know time for them."
	- P3 exhibits this to some extent though they are aware of the call tree

  ### Describing indices / database terms
  
    - P3: "the performance data, this is stored in a multi index form"
    - P3: "And it's going to the first table, which is the performance data table with with that profile hash that we just talked about. So it's like a foreign key for for that table."
    - P3: "performance data is acts as sort of the main table, if you look at it from a relational database management system, our relational database management model"
    - P5 uses the term 'view' but not in a vis way.

Drawing Anxiety/Test Anxiety
- P1: "Yeah, so, I'm not an artist, but I think you'll probably get the idea", "Did I do good?"
- P3: "Yeah, my handwriting is not the best, but this helps"
- P4: "Okay, yeah, this is kind of tricky. It has potential to get very messy."
- P5: "I'm really bad with drawing and let's try to come up as we go"
- P6: "Did I pass?"

### Visualizing and Identifying patterns in ensemble data
- P1: " And then the more profiles you have, you just be able to visualize more of that. Those patterns happening as you have no more to more data points to kind of extrapolate?"
#### Appropriate Visualizations for Ensemble Data
- P2: "So like performance data table, multiple profiles, you can look at, like, say, a box plot. So kind of a variation."
- P6 Frames their discussion of the data solely with visualizations; using line charts and error bars. Their model is primarily based around analysis and visualizations.
- P7: "Box and Whisker is a common one that I've seen for also, I've seen them, the line plots with like shaded region on either side, indicate kind of how it varies between runs, if they just depends on what you want to do with it."
- P7: "If so, that would be if you want to more statistical if you wanted it in other ways mean, some of the things that were useful is of course, plotting. So have your, your MPI ranks on the x axis time on the right. If you just had one run at each MPI rank, each MPI scale, you'd probably just do a line plot"

  ### Desire for context

    - P4: "I think there's this care the assumptions that you have to do in how you are setting up the measurements for your sample."

## Performance
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
