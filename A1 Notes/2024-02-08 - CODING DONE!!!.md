
Now that the bulk of low level coding is done I want to reflect substantially on the common ideas I found across codes which will be built up into larger themes or point to larger themes.

### Metadata and Data

A substantial point of interest that many discussions revolved around is the role of metadata in LHDs; where it lies in relation to other parts of the LHD, how useful it is and how important it is. The intuition I have from this round of coding as well as last rounds is that metadata is explicitly seen as useful for organizing data but not for analysis. On its face this seems intuitive because we cannot meaningfully analyze the attributes of a problem, or the parameters which often define "metadata." However, we absolutely require these variables for making any sense of the data. Realistically, since so much analysis is comparative and intentional there is no value whatsoever to the data without some organization of it. 

I can see that two different profiles have different metrics but on it's own this is meaningless. Even extracting patterns of behavior across many data points does not tell me a great deal about the performance of a system without organization or cross referencing metadata values. Of course we could observe that there is variance and implicit clusters in the data but that's about it and without context these implicit organizations may be meaningless.

This complicated conception of metadata is not made simpler by the broad use of the term in the performance analysis domain. In many cases metadata variables are attributes of a problem or runtime parameters. However they are just as commonly global metrics produced from runs of software and thus should be analyzed like data. Or, at the very least, cannot really be used for meaningfully correlating or organizing the data in the way that other metadata is.

### Sensemaking

In this most recent round of analysis I found a term to describe the engagement with the dataset which we have observed especially among more senior or analytically focused participants: sensemaking. My engagement with prior work has led me to believe that sensemaking roughly describes ( I need to do more research on this ) the behavior analysts exhibit when they are engaging with a dataset during EDA. They are taking something unfamiliar and engaging with it to make it familiar.

What's fascinating is that this appears to be something hardwired into their thought processes. When supplied with the most simple, toy examples they inject meaning to understand it better. Sensemaking in this sense is something of a conversation between data and analyst.

### Domain specific insights

There are many domain specific insights which can be used as guidance for my next project and should be discussed as actionable guidance on how to develop an overview/recommender system for LHDs of this type. Among the observed codes, there were insights into **what visualizations** our collaborators thought in. They also frequently citied example variables which can give us guidance on what might be the best variables or parts of an LHD to highlight

Many participants critiques of the [EnsembleAPI] also provides us with significant guidance on gaps which our potential UI can fill. Among these are discoverability of relevant attributes for organizing, grouping and filtering data. Similarly, an overview should provide a clearer window into what attributes are available and provide simple means to extrapolate them.