
### Post Interview Reflections

### Pilot - 04/12/2023
- Pilot seemed to go well
- I learned about some interesting techniques for visualizing ensemble data
- A contour boxplot could work for [LAB]
	- If we can identify the most interesting dependant variables and independant variable then we can identify which independant variables are more normal to the mean/median of our dependent vairable and which are outliers or tend more twards producing outlier measurments
	- This does not show correlation however. . . necessarily
	- This may not apply actually, but we'll see
- The questions seemed fine although I was not able to ask my task dependant questions for obvious reasons
- D produced a table for the control question which is cool
	- And multiple styles of visualization
- His description of the dataset was very narrative. He went from the source on to the resulting data and then through transformations done to make it suitable for an ensemble
- User defined thresholds could be helpful when visualizing our data

----

### Participant 1 
- Heads up display thing
- or K2's work
	- [A5] described A's role in the last project like this
	- K2 has all sorts of ideas
- 1/2 hour
	- Get people like O and Kevin Huck to explain a profile ensemble
- Backup plan if [EnsembleAPI] goes sideways
- Tahoe Tools 
- Add for additional groups
	- What do people use for thier primary toolkit?
- Add drawing to when it was spoken
- 3 Datapoints
- My best guess of what he was drawing
	- Did not imply a graph; node link diagram
	- Did he think it was implied that there was relationships between things
	- Does he just not work with the graph
	- "Why did we call them nodes"
- O at some point 
- Data Stampede
- Metadata is not the data
	- Ask about the metadata at the end
- We felt that O was dropping dimensions while trying to make the vis
- Sketching is the visualization -> Here's where all the dimensions got dropped
- Stronger way to say the entire data related to this dataset
	- "Sketch out what the entierity of the data stored for this dataset"
- ![[Pariticpant 1.png]]
- Drawings Annotations
	- 1 
		- Was used to describe the dataset broadly
		- There may have been ambiguity as to what was meant by data vs. metadata
		- The "stats" dataframe was not mentioned at all
	- 2
		- This is a visual description of the columnar join where the dimensionality of the columns is increased by one
		- Its not clear what exactly makes one independant variable columnar appropriate vs. row appropriate
			- Perhaps it's the implicit number of possible variables?
	- 3 Simple dataset description
- Followup Question:![[Pasted image 20230412170348.png]]

----

### Participant 2
- Def dropped a dimension when relating data to stats frame
- 2 for 2 on ignoring the call tree
- The victims of raja know no bounds
- Finally a tree!
- Debrief
	- Hes so on top of what he does
	- But he's missing context
	- He doesn't have a mental model of performance data
	- The fact that he doesn't know that A is functions
	Add a call tree task
	- They need to use a call tree task
	Everything is in the context of I need to calc stats with this
	Subsetting the metadata table
	- V's responsibility
	- Real elephants and very big
	- Causality between the metadata and the data table!
	- Thinking about data over time
		- D may be pulling from provenance
	- "We have no hope of really understanding data without drawing it"

Hypothesis:
- Folks at the high level will have a similar view of it because they are more interested in it on a conceptual level. And people closer to the code will understand the data more specific to the role they take in coding. (Furthermore, they may be very removed from the context of the data)

-----

### Pariticpant 3 - 04/17/2023
- Neat that she used terminology
- Can see the holes 
- V had the most robust version of the data model
	- But doesn't seem to understand what performance analysis is
	- She has an overview of the data but doesn't have the internals
- There is more [BenchmarkSuite] influence
- They may have started talking to each other
- How do people talk about corner cases

Who has tablets?

**Can you show me what an atypical dataset one looks like.** 
**PUT CONNECT FROM IPAD WITH TABLET CASE IN EMAIL**


### Participant 6 -

- Multiprofile Stats Profile
- Deep questions
	- Design of the [EnsembleAPI] Datastructure
	- What does this say about the design of datastructures like this
- Related work:
	- Datastructures like this
	- Software Engineering?
		- Algortihms
		- Data structure expertise
- "Digesting" the data structure of the HUD
- Design the thing scenario style - possibly
- O goes from datastructure to the graphs she wants implicitly
- Everyone stores metadata in very different ways.
	- It's not "the data"
	- O recognizes that there is information that is not captured which is crucial to the job
- One thing we have to worry about.
	- K2 presented data in paragraphs
	- O: here we concieve of the data as being the data in the [EnsembleAPI] object
	- She was interested in the organization of the object
- We have to have a very high level of sophistication in HPC
- I don't think that someone who did not already know about the project could conduct these
- The positionality is very important to these ones
- There is clearly a lot of reductions going in peoples head that they are not vocalizing
	- Sometimes those reductions are happening where they shouldn't
- Catchy Titles
	- The ghost of metadata present
	- The spectre  of metadata 
	- The dark matter of data: Metadata
	- The aether of data
	- The platonic realm of data:
	- Here there be Metadata dragons
- The [EnsembleAPI] diagram is underpowered
	- Take a note that she means this 
	- Get those old diagrams from everyone
- An emergent metadata theme is really emerging
- Related work on ensembles and metadata

## Emerging Themes

A strong theme related to metadata is beginning to emerge. Although some participants (P3) have identified metadata and placed it in the data structure or in their mental model of the data, the overall observed theme seems to obfuscate it. It is often ignored outright, and when it is not, it is referred to as a sort of ideal. A realm where relevant information can be plucked ad hoc to modify and contextualize the data without signficant thought given to its limitations and its interaction with the data. This was especially prevalent with P6 but also P1 and P2 eschewed making significant refrences to metadata. P5 also? I'll have to see.

Before this can be declared a full theme however this has to hold up to our coding. I'm unsure if it will or not.


## P7
- Patterns emerging that the task based questions
	- They want to go past what data they use but they think 
- P7 did not draw a single indented tree and saw the graphs
- Concerns about Dyad being too much 
- There is an inherent ordering to node over profile
- Only O has been the only one to mention scalar data
- Data abstractions
	- Assertions about network
	- Data abstraction eicitation needs a series of asserts
		- Is this field a always a number?
		- What is the range of this field?
	- **The idea of data abstraction assertions could be something we propose at the end of the paper**
		- With each assert there is a multiple-choice answer
		- We would propose this at a high level as perscriptive advice
		- **Yagoda Best Paper**
- Ask K2 anonymize the transcripts
	- If she wants to
	- NBD if not
- Is this a latitudinal study? :p

## P8
- So much is being put in the metadata
- Metadata is anything that does not fit in the tree
	- Just put it all in this abstract bucket
- Parallel thicket objects under one metadata
- If it fits in the tree its the real data
- Metadata is "not useful for analysis"
- Work framing
	- Ensemble as a word
		- We wont put it in the title
		- Complexity of data dimensions
	- Send an email about Metadata
		- "Follow up question. What is your personal definition of metadata in the thicket object?"
	- "Collection of Datasets" not an ensemble :p
	- Identifying the limitation of the thicket object
- People are forced to organize things by the language we use
- [P8] points out "I have trouble accessing the metadata"
	- It is not well structured
- HUD
	- This is what you 
- Metadata in thicket works like kind of a Key Value store
- The indented tree is not a tree
- P8's trouble with word description validates the fact that we have sketching
- Metadata has no clear structure + it's also not real data
- Assassin's Creed
	- Nothing is structured, everything is permitted
- Consequences for Thicket
	- Re-Think thicket object to carry other structures
	- Per-rank things people are talking about now
		- There is metadata per rank
		- P6: I want to add lists to the nodes
	- Per-run and per-rank and per-region
		- Could be helpful to articulate
		- Per region is always collapsed on rank
	- [A5]
		- This comes back to dimensions
		- What dimensions are we dropping
			- Rank
			- Regions
			- Runs
		- Providing structure to this doesn't necessarily help with P8's problem
	- We have a structure like a tree
		- Which way's it extends and which ways it doesn't
		- Could extend in the rank dimension
			- But its already collapsed
	- People will need a text search and a hierarchical structure
		- Does this exist
		- Do key word google search and google scholar search
		- Foundational work
	- We asked everyone
		- We cannot conjure more people
	- Dropped dimensions
	- Platonic Ideal Realm is Metadata
		- Look at some relationships here
		- "Metadata as the Platonic Ideal:"
- Take the time to think about this


## Participant 9
- [P9] is a secret [DataExplorationGUI] user
- [P9] was much more on the [P6] side of things
- No thought given to the data structure at all
- People who care about the format are working on it
- People who work with the data 
	- They never go back to the data format
- Should there be no data abstractions?
- Is there a spectrum between the raw data format, the abstraction and things inbetween
	- Especially when you need to understand where the data is going
- Abstraction that makes the most sense for the problem
- When people have to manipulate the data to fit the abstraction
	- There must be a mental model somewhere
- Affordances on mental models where he is thinking about the tool
- [P9]'s Data Abstraction is [DataExplorationGUI]
- [P9] did affirm the stuff that we saw in [P6]'s interview: esp the user perspective
- Bring up anyone who has touched the project
- Anonymization (being careful)
	- We asked x and got the vast majority of people
	- This is the max level of description we can do without losing anonymization
	- **Redact [DataExplorationGUI] discussion**
- [A3] and [A4] as co-authors
- Send transcripts as a google doc to everyone once we get to that point
- Obvious things
	- People think in the tools they already have
- Side Discussion
	- Is the "Calling Context Worth It?"
	- Provocations
		- 3 sides
- Plan the most suprising findings
	- Alt.HPC: Provocations for the Scalable Tools Workshop
- Other big narrative
	- The divide between how different actors think about the data from consumer vs. producers
	- The valley between the format of the data and the visualizations
		- The data abstraction fits this
		- Plushie paper
			- The problem was not that people have the data
			- Touches on the data wrangling 
			- The metadata becomes a facet of this gap
			- We need to make the metadata apparent and structured
				- At some point the metadata stops becoming metadata and just is 
		- Interfaces and Data
	- [P6] had one misconception
- The drawings are so helpful
- Techniques for convincing people to draw
- This is the data