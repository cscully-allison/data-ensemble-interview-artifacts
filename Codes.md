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


### Pieces of the EnsembleAPI were forgotten.
  - For each participant and each EnsembleAPI piece, list when, if ever, the
    participant alluded to the piece and how. 
  - For this code, there are four pieces: Performance Data, Metadata, Stats
    Data, and Call Tree.
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

### Ensemble data structure pieces are linked structurally

  - P1, P2


### Ensemble data structure pieces are linked meaningfully
  -  P1 ". Your profile one would be corresponding to the data set from the run with two CPUs and then profile two correspond to the run with four CPUs, and then you'd see in your times, well, you should see that the time for profile one is gonna be higher than the time for profile two, because it had more CPUs"
  - P2 "Obviously, they kind of affect each other, like, in some kind of formats, because, you know, certain metadata like compilier optimization, things like that will directly affect the values in the performance data table."

### Influences on importance

  #### Presence

    - P1: "throughout all the different kinds of data that I work with, there's always nodes"
    - P1: "the metrics themselves is another dimension of that, that I'm adjacent to the nodes that I'm expecting to see when I'm working with the data"

  #### Indexing power

    - P1: "but it's kind of less important because we have that represented as like an inner index . So it's kind of like, subsequent to the nodes, I guess, in the visualization in my head."

  #### What participant interacts with

    - P1: "Yeah, I order it because that's kind of like the when I'm developing the significance of what what I'm interacting with the most, it's probably in that order."
    - P2: "I see the performance data as the most important piece of the ensemble data, just because most of the work that I do is on the performance side."
    - P3: "And personally, I've worked mainl-b jy with metadata table. So that's why it took precedence compared to the statistics table. So I'm guessing if somebody from my team has worked on the statistics table, more would probably introduce the performance data, and then how the aggregate statistics table is connected to that"

  #### What leads to insight
    - P2: "I think, you know, with what we're kind of working towards on the project, performance data kind of provides insights into your data. More, so I think then possibly metadata does because you can, you know, perform correlations, perform time series analysis and things like that. So you can kind of get a much better insight, in my opinion, using the performance data rather than the metadata."


### Participants dropped or reduced dimensions of the data.
  - P2 describes how the Stats table is in some sense for this purpose.

### Multi-dimensional aspect of ensembles is hard.
  - P1: "if you have two CPU four CPU for AWS, and then a two CPU four CPU for LC, then you're kind of in trouble. Because how do you kind of extend, you know, if you've said everything vertically, you kind of, you're getting things mixed up."
  - P2 uses duplication of [EnsembleAPI] objects for Task 2



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

  #### Data's relation to the domain is part of the model

  #### Data is described based on how it is stored

    - P2: "we just take ensembles of data and load them into pandas data frames, and then using those pandas data data frame, perform analysis on that data."

  #### Data is described based on how it is accessed

    - P1: "Yeah, so I'm just doing a performance data table, kind of because that's the way I think about when I read in a data set, and I'm working with a data set."

  #### Data is described based on how it is used

  #### Exact data is not important

    - P1: "so the data I work with, it's sort of arbitrary as a developer"
    - P1: "the columns themselves are kind of arbitrary"
    - P1: "And then third, probably the profiles. That's the data itself, but it's kind of less important because we have that represented as like an inner index. So it's kind of like, subsequent to the nodes, I guess, in the visualization in my head. So that's where I kind of like, put things even though thinking about is kind of counterintuitive, because without the profiles, you wouldn't have any data."


Analysis Task Influences Mental Model or Awareness of Parts
- P1: (In reference to architecture comparison task): "So that's, that's not in this table"
- P2: (In reference to architecture comparison task) "Can I ammend my picture real quick? Sorry, I just realized something."
- 

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

## Metadata

These codes have something to do with metadata.

### What is Metadata?

  - P2: "Because you know, in the metadata, this is where we're kind of, you're kind of mapping the like, the information that you use to kind of run the job."

		
### Metadata is hazy.


### Metadata is not data.


### Profiles are the real data.

  - P1: "And then third, probably the profiles. That's the data itself"
  - P1: "without the profiles, you wouldn't have any data."
  - P2: "But you would have that information in the metadata, and then it would go, like the actual outputs, and the metadata."


### Metadata not explicitly stated but implied
  - P1 alludes to knowledge about profiles but not where it lives: " Your profile one would be corresponding to the data set from the run with two CPUs and then profile two correspond to the run with four CPUs"
  - P2 does Task 1 with metadata explicity but in Task 2 does architectuer as separate [EnsembleAPI] objects rather than metadata

### Metadata as an analysis question repository





## Drawing

### Directionality
- (Categorical Metadata -> Horizontal) P1 - "columnar join that we've talked about, but like, so instead of, in the previous case, where you're talking about different different amounts of CPUs, we tend to look at different architectures in a column going horizontally, you could do the same thing."
### Scale is implied

### Indicators of scale

#### Uses ellipses to indicate more rows

    - P1, P2

#### Uses etc to indicate more columns

    - P1
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


  ## Task 2 

  ### requires perf data and metadata

  ### requires perf data on multiple objects

    - P2


  ## Task 3 

  ### requires the call tree



  ## ABC Tree

  ### draws some form of tree

    - P2 (on clarification)
  
  ### casts the questions into the data they work with

    - P2

   


## Uncategorized as-of-yet observations

  ### Balanced node-link diagrams are trees, accept no substitutions

  ### Dangers of test dataset ([BenchmarkSuite])

    - does not seem to understand nodes are functions instead of applications
      - P1, P2
        - P2 "ut when I think nodes, I would think, like more like application, so there's like, an app here, the app here, and then when you run these applications, you know, you get, say, like for these two applications, there's ya know time for them."

Drawing Anxiety
- P1 - "Yeah, so, I'm not an artist, but I think you'll probably get the idea"
- P3 - "Yeah, my handwriting is not the best, but this helps"
- P4 - "Okay, yeah, this is kind of tricky. It has potential to get very messy."
- P5 - "I'm really bad with drawing and let's try to come up as we go"

Visualizing and Identifying patterns in ensemble data
- P1 - " And then the more profiles you have, you just be able to visualize more of that. Those patterns happening as you have no more to more data points to kind of extrapolate?"
- 


