And new narratives and ideas are forming about this work. It's still very squishy but there is a though that is evolving about the core narrative and how it relates to data abstractions.

We have this thread that [EnsembleAPI] is the development of some data abstractions and functions for aiding analysis. But the abstractions are not useful to analysts and may get in their way, and don't reflect the way they think about data? Is this helpful to exploratory data analysis or structured analysis?

Ok I was working on the related work and I feel like I had an idea of how to tie our findings together with the narrative in a way that will be of genuine interest to the visualization community.

I think that the emphasis of this work should be on *data abstractions* in particular. More specifically on the fact that the abstractions chosen by our collaborators were not sufficient to describe many important aspects of complex data , not reflective of our collaborators' mental models, and not useful for communicating the data between us and them. Its a failure of data design, but also enables us to contribute to scholarship on the importance of data abstractions and how critical they are to tool and visualization design. 

Findings wise, we can tie our themes to this discussion very well, I argue. Our themes seem to at least hint ant the why and can be developed from there. The abstractions appear to be well chosen and logically organized however *(we observed)* that
1. they failed to meaningfully capture the metadata other than shoving it in a giant bag;
	1. this conflicts with the varying utility of metadata (where some is useless and others are commonly used)
	2. reinforces the erroneous idea that metadata is "unimportant" and disconnected from the data
2. the dataset being abstracted is more complicated and more fuzzy than this tidy organization suggests
	1. thus analytically minded individuals do not see their data in it and rely more on mental models (or particular variables ) to communicate their thoughts of the data
3. people forgot aspects of the abstracted data although there were so few parts, again suggesting a lack of salience

**This does rely on the assumption that one value and benefit of data abstractions is providing us not only with a shared model to use (for visualizations and tool design) but also to discuss and reason about specific datasets in general ways**
	1. A's and your paper on data abstractions seems to support this take however and I'm finding other related works to support this
