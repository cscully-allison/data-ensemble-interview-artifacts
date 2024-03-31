# 08-07-2023 (revised 08-10-2023)

~~Ok everything is roughly coded now and they need to be organized into big themes but there are a lot of interesting insights here worth investigating in detail.~~ Arranged in no particular order:
1.  Metadata - There is a tension between the utility of metadata, both implied and expressed by participants and the general idea that it's not necessary to the analysis/not what we are analyzing. An additional idea of interest is the haziness of metadata. In some instances its a grab bag of whatever a analyst may want to investigate; data post-it notes. Its metrics measured at the performance level and also the runtime contexts which may affect those metrics. It's domain specific configurations and not.
2. Ensemble Elephants - We have so much about this but not sure exactly what to write; Something about ensembles and their high dimensionality being particularly unique and frustrating 
    1. What is a part of data - We originally chose the term "part" for our interview because the word dimension is overloaded and leading. However we found that although people's choices of data parts can fit into fairly standard categories, they varied significantly in their granularity and specificity.
    2. Dropping Dimensions - This was the original purpose of this research. To identify where and when people were dropping dimensions when thinking about the data and communicating what charts would be useful for visualizing the data. This is kind of a sub bullet point under data mental model but, the mental model itself doesn't fit a narrative.
3. Drawings - There is some part of the drawing narrative that is interesting from a methodological point of view (Eg it provoked people to think about their data much more in depth than if we had only asked questions) but also it provided us with insights into how participants are thinking about thier data from a visualization standpoint. Do they see the data as a chart--something produced after reading in and formatting and aliging data? Do they see it from a workflow perspective of how the data is obtained and all the steps required to load it into a data structure. How much is elided or stored in the participants mind even if they have the opportunity to write everything down?
    1. We get to have figures, yay
    2. Diversity is an interesting point here because it was a few months after the paper was published and the month that it was presented on
4. Controls - Not intrinsically interesting but will be useful to have some tables and breakdowns of whether people were able to do the requested task with what they had drawn. Its another way to highlight what people are forgetting/dropping. 

Outside of observations we need clear proscriptive advice to readers. Some which may be useful to recall:
1. Consider interviewing software developers and users alike to uncover biases, gaps and assumptions about data when developing a complex data tool. Newer developers may not have any biases and may not need to understand the data in detail. This can cause problems however (see example of P1-P3 and new changes to [EnsembleAPI] maybe idunno)


# 08-10-2023

## Thoughts on positionality and argumentation. 

### What is the positionality.

Broad:

- Ensembles are multi-dimensional, context-dependant datasets, that are difficult to track ([cite needed] < are we this citation? does this exist? is this our thesis?) so we need to understand them better (but why the CHI community? lizards are complex but CHI doesn't need to understand them better)

- There exists prior work in CHI examining data mental models, however it does not examine mental models of a large complex dataset [Data Elephants]

Narrow:

- Ensemble analysis (tools dedicated to ensemble analysis?) are still new to the HPC performance field [citation needed] and mental models are not well understood by performance tool developers


## Paper Goals/Problems to Resolve/Gaps

- *If* we better understand mental models of ensemble datasets *then* we (as a community) can build better tools for users
    - May run into (do the future work issues we talked about in last HCC meeting)

- Visualizations, in general, 
    - rely on mental models to make meaningful abstractions about: 
        1. the data (plotting/showing data) (overviews?)
        2. relationships between datapoints and datasets
        3. how to highlight interesting parts of the data
    - By understanding the mental models of *(certian subgroups of) ensemble users and tool developers, we can:
        1. Validate that designing visualizations and tools for these datasets is hard
        2. Provide inisght into commonalities shared by a slice of the data analysis population
            1. Which can maybe be used as guidancce for developing visualizationss

- 