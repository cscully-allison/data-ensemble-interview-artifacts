### Pilot - 04/12/2023
- Pilot seemed to go well
- I learned about some interesting techniques for visualizing ensemble data
- A contour boxplot could work for LLNL
	- If we can identify the most interesting dependant variables and independant variable then we can identify which independant variables are more normal to the mean/median of our dependent vairable and which are outliers or tend more twards producing outlier measurments
	- This does not show correlation however. . . necessarily
	- This may not apply actually, but we'll see
- The questions seemed fine although I was not able to ask my task dependant questions for obvious reasons
- D produced a table for the control question which is cool
	- And multiple styles of visualization
- His description of the dataset was very narrative. He went from the source on to the resulting data and then through transformations done to make it suitable for an ensemble
- User defined thresholds could be helpful when visualizing our data

----

### Pariticpant 1 
- Heads up display thing
- or Katy's work
	- Kate described Alex's role in the last project like this
	- Katy has all sorts of ideas
- 1/2 hour
	- Get people like Olga and Kevin Huck to explain a profile ensemble
- Backup plan if Thicket goes sideways
- Tahoe Tools 
- Add for additional groups
	- What do people use for thier primary toolkit?
	- David Boheme
- Add drawing to when it was spoken
- 3 Datapoints
- My best guess of what he was drawing
	- Did not imply a graph; node link diagram
	- Did he think it was implied that there was relationships between things
	- Does he just not work with the graph
	- "Why did we call them nodes"
- Onur at some point 
- Data Stampede
- Metadata is not the data
	- Ask about the metadata at the end
- We felt that Olga was dropping dimensions while trying to make the vis
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
	- Vanessa's responsibility
	- Real elephants and very big
	- Causality between the metadata and the data table!
	- Thinking about data over time
		- Devin may be pulling from provenance
	- "We have no hope of really understanding data without drawing it"

Hypothesis:
- Folks at the high level will have a similar view of it because they are more interested in it on a conceptual level. And people closer to the code will understand the data more specific to the role they take in coding. (Furthermore, they may be very removed from the context of the data)

-----

### Pariticpant 3 - 04/17/2023
- Neat that she used terminology
- Can see the holes 
- Vanessa had the most robust version of the data model
	- But doesn't seem to understand what performance analysis is
	- She has an overview of the data but doesn't have the internals
- There is more Raja influence
- They may have started talking to eachother
- How do people talk about corner cases

Who has tablets?

**Can you show me what an atypical dataset one looks like.** 
**PUT CONNECT FROM IPAD WITH TABLET CASE IN EMAIL**


### Participant 6, O -

- Multiprofile Stats Profile
- Deep questions
	- Design of the Thicket Datastructure
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
	- Katy presented data in paragraphs
	- O: here we concieve of the data as being the data in the Thicket object
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
- The Thicket diagram is underpowered
	- Take a note that she means this 
	- Get those old diagrams from everyone
- An emergent metadata theme is really emerging
- Related work on ensembles and metadata

![[Pasted image 20230523133538.png]]
![[Pasted image 20230523142118.png]]
![[Pasted image 20230523135406.png]]

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
- Ask Katy anonymize the transcripts
	- If she wants to
	- NBD if not
- Run asking Mchela by Ian
- Is this a latitudinal study? :p