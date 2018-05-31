@title[Networks and Digital History]
# Networks and Digital History
![There is no spoon](https://media.giphy.com/media/3o6Zt0hNCfak3QCqsw/giphy.gif)
Note: Welcome to this workshop! I know you had a lot of great options so I'm honored that you chose this one. 
---
@title[Say Hi 👋🏽]
# Say Hi 👋🏽
- Let's do introductions. Name, where you are from, what you work on...
- I'm Zoe LeBlanc. @Zoe_LeBlanc / zgleblanc@gmail.com / zgl3n@virginia.edu

Note: Hi I'm Zoe. Digital Humanities Developer by day at the Scholars' Lab at UVA. By night/any free moment I have, I'm also getting my doctorate in history at Vanderbilt University. Let's do some introductions 5-10 minutes
---
@title[What can you expect out of today?]
#### What can you expect from today's workshop...
- Short answer: a lot of breadth |
- Some depth on networks |
- But even more discussion around why/when networks are useful for DH |
- and of course when they aren't |
- lastly (hoping), we can talk about your research and what you hope to do with networks & DH |

Note: So we only have two hours today so we're going to try and do as much as we can, while also realizing that there's some serious limits. Today I hope we can achieve the following goals. Some introduction to networks. What they are and aren't. How do you turn historical research into data and then networks, and what are some of the pitfalls when you're going from data collection and cleaning to data modeling and visualization. Some discussion of what types of historical problems are amenable to networks and how we can critique networks. Finally if we have time, I want to spend some time thinking through how networks might fit in your research agenda. Obviously this is a lot so we'll see how far we can get, but I'm going to have a long list of resources and tutorials online, and I'm also offering up my email so that if you ever want to discuss your research. I came from a school with very little DH infrastructure and it was people agreeing to skype me that go my interest off the ground so I'm paying it forward.
---
@title[So where to start]
### Where to start...
![Keanu wants to go](https://media.giphy.com/media/V2ojLo7PvhVug/giphy.gif)

- [Survey Time](https://drive.google.com/open?id=1NjAeaBTHwuXyuVjnTq1wRoOFBtb09KUEVb8rTMXhsT8) |

Note: Dig into the data > had you fill out this survey and it's going to be our first data set > So let's take a look at some of the metrics google forms provides. What's note worthy? We can see the overall distribution, we have some charts > bar and pie charts > So how do we turn this data into an a network? 
--- 
@title[Basics of a network]
### What is a network?
- nodes -> entities |
- edges/links -> relationships |
- attributes -> descriptive information about entities and relationships (could also be statistical) |
- weights -> strength of connection between nodes |
- directed network -> asymmetrical relationship, eg. twitter |
- undirected network -> symmetrical relationship , eg. facebook |

Note:so this is a bit of word vomit let's put it into practice to see what it means 
---
@title[Palladio]
[Palladio App from Stanford](http://hdlab.stanford.edu/palladio-app/#/upload)
- Let's spend a few minutes together making a graph
- Get the data from our [survey](https://docs.google.com/spreadsheets/d/1nLrreGzsp0fHWl2oGJozWeXM0_swQfhk24N5gqxXMTc/edit?usp=sharing)

Note: let's open up palladio > tool developed by stanford > load in data  > make a graph > is this a network? yes > is this meaningful though? probably not > what's missing? hypothesis SPEND 5-8 minutes
---
@title[Digital History First Steps]
### First Step in Digital History
- HYPOTHESIS!!! |  
- What sort of questions can we ask about this data? |

Note: if we think of this as a social network what types of things can we ask? we can think about hypotheses but we also need to talk about methods and hypotheses. but can we really make a hypothesis without understanding our methods? hypotheses are great but also need to understand our methods > chicken and egg of digital history > where do you start > has to be both
---
@title[Networks First Steps]
### First Questions When Starting Network Analysis
[Marten Düring, "From Hermeneutics to Data to Networks: Data Extraction and Network Visualization of Historical Sources," The Programming Historian 4 (2015)](https://programminghistorian.org/en/lessons/creating-network-diagrams-from-historical-sources)
- What defines a relationship between two actors?
- Who is part of the network? Who is not?
- Which types of relationships do you observe?
- Which attributes are relevant?
- What do you aim to find?

Note: Let's take a look at this programming historian tutorial > some great questions for thinking through our hypothesis>  who is most likely to collaborate? how do we define that?places, years of program so we've taken our survey data and abstracted these relationships, operationalized our hypothesis what palladio is great for but pretty limited what makes networks interesting is largely the relationships between the entities > whole branches of statistics known as network science have developed algorithms for understanding these relationships
---
@title[Network Modeling]
### Next Step: Network Modeling
[John Ladd, Jessica Otis, Christopher N. Warren, and Scott Weingart, "Exploring and Analyzing Network Data with Python," The Programming Historian 6 (2017)](https://programminghistorian.org/en/lessons/exploring-and-analyzing-network-data-with-python)
- What is the overall structure of the network?
- Who are the important people, or hubs, in the network?
- What are the subgroups and communities in the network?

Note: Great tutorial on programming historian. which if you don't know about it, it's a great resource for DHers. This tutorial has some great questions for social network analysis so let's try and answer them
---
@title[Network Navigator]
### Network Navigator tool
[Network Navigator by John Ladd & CMU](http://dh-web.hss.cmu.edu/network_navigator/)
- degree -> sum edges connected to a node (node with large degree = hub) |
- eigenvector centrality -> sum node' edges and edges of node's neighbors (more influential to other nodes, eg. PageRank) |
- betweeness centrality -> all shortest paths through a node (nodes/brokers that connect groups) |
- [Game of Thrones Dataset from Melanie Walsh's Sample Datasets](https://github.com/melaniewalsh/sample-social-network-datasets/tree/master/sample-datasets/game-of-thrones) |

Note: A great tool to answer that question is CMU's network navigator, which let's us take a csv version of our data that we have to message a bit first to make it work. First we have to select the entites and relationships we are most interested in.  What do you see? We can see degree, which is pretty straightfoward as sum of edges connected to each node, larger nodes are hubs. But notice that the rest of the metrics aren't generating. Why might that be? How could we figure what's going on? Read documentation or test different data set. Melanie Walsh has a great set of network analysis data sets. We're gonna use the game of thrones one. Now we can see other metrics. 
---
@title[Network Metrics]
#### Network Metrics Continued
- density -> actual edges / possible edges | 
- clustering coefficient -> average across network of how likely nodes will cluster |
- transivity -> all triangles/ all possible triangles |

Note:what's the shape > strucuture or topology tells you about how centralized/decentralized, sparse or dense your network is > helps identify components or connected nodes, let's look at some of the metrics available in network navigator > shape of the network (topology) > all of these metrics are helping us understand how the network is representing this dataset > difference between dataset and network (abstract vs concrete relationships) > proabilities over certainties > idea of homophilly > Network homophily refers to the theory in network science which states that, based on node attributes, similar nodes may be more likely to attach to each other than dissimilar ones.
---
@title[NetworkX]
### NetworkX
[NetworkX Library](https://networkx.github.io/documentation/stable/reference/algorithms/bipartite.html)
- bipartite -> a network where nodes only have relationships with another group of nodes |
- [Networks Demystified 9: Bimodal Networks by Scott Weingar](http://scottbot.net/networks-demystified-9-modality/) |
- [Bipartite Graph](https://bl.ocks.org/ZoeLeBlanc/25dffd0935ab26bf3235b8226c32a8bc) |

Note: why didn't our initial network though? thoughts? it's because it's a bipartite network. very common in DH, but has a lot of issues. Scott has a great piece about working with bipartite networks and their issues. We can check if a network is bipartite by looking through our table of data or more easily using networkx. NetworkX is a python library that is designed for building networks and analyzing them. Up to now we've looked at out of the box tools for studying networks. A few others that are really common are Gephi and Cytoscape. I'm going to give you a link to a notebook running python code in the cloud from our github repo so that you can follow along. We'll go along the script a bit > launch binder second notebook
---
# BREAK
Note: 10 minutes for breaks
---
@title[Algorithms]
### Networks Next Steps
- Final piece for networks -> ALGORITHMS |
- ![Good stuff](https://media.giphy.com/media/WuVdPqDSsRbjy/giphy.gif) | 
- louvain community detection -> assigns a community to each node based on density of edges inside communities |

Note: what makes networks so powerful is a) how they represent relationships b) algorithms designed to leverage those representations >  visualize the output of this algorithm with our dataset and the game of thrones dataset > what do we see? going to use d3 > open community detection notebook
---
@title[Sorta]
> "Put simply: digital humanists do not need to understand algorithms *at all*. They do need, however, to understand the transformations that algorithms attempt to bring about. If we do so, our practice will be more effective and more likely to be truly original." 
> [Do Digital Humanists Need to Understand Algorithms? Ben Schmidt (one of your instructors), Debates in Digital Humanities (2016)](http://dhdebates.gc.cuny.edu/debates/text/99)

Note: Thing to understand about most algorithms and stats is that it is generally looking for measurements of centrality or varience, and that simply is often better > Community detection assigns a community to each node in a network to analyze how closely connected nodes are internally to a network
---
+++?image=https://media.giphy.com/media/3o7btNhMBytxAM6YBa/giphy.gif
---
![matrix](https://cdn.kastatic.org/googleusercontent/9XeqQ2stwpGbXuli1TWSbnHQwITfrYV_AtmjMFEtQZbAo9VvWQ0KYNBnyRx5x9Ekpwh_Pdwzu4dC6b3Y0Wb0Qsu5)
is the Matrix 
![whoa](https://media.giphy.com/media/uPnKU86sFa2fm/giphy.gif)
---
### Final Exercise:  Code Review
- what sorts of research questions work well with networks? how can networks further historical arguments?
- what sorts of critiques can we make of networks? what might we do next with these data sets to actually make historical arguments?
- what would you want to learn more about for networks or digital history? how might you go about doing that?
[https://github.com/ZoeLeBlanc/Networks_and_Digital_History/projects/2](https://github.com/ZoeLeBlanc/Networks_and_Digital_History/projects/2)
Note: spend 15 minutes with each other and then some time talking together
---
### Scott Weingart's Lessons for Digital Historians
Culled from two blog posts: [Lessons From Digital History's Antecedents](http://scottbot.net/lessons-from-digital-historys-antecedents/) and [Argument Clinic](http://scottbot.net/argument-clinic/)
- Uncareful Appropriation –> Collaboration 
- Reliance on Imports –> Statistical Training
- False Precision & Certainty – Simulation & Triangulation 
- Quantitative Blinders –> Rejecting Digital History 
- Focus on Data -> Focus on Historical Context  

Note: "sidestep the issue of accidentally misusing a method by collaborating with someone who knows how the method works." "Avoiding quantitative blinders – that is, the tendency to only care about what’s easily countable"
---
> "Without having a ground against which to contextualize our results, a base map like general population, the fact of which cities voted in which direction gives us little historical meat to chew on. **The above boils down into two possible points of further research: deviations from expectation, or deviations from internal consistency.**"


Note: 
no one is an impostor. 
we're all starting from somewhere
consider missing data, 
look at ways to 
Even if no alternate hypothesis presents itself, and all of your tests agree with your hypothesis, you still do not have causal proof.
 Be sure to take time to consider what’s missing from the dataset, due to archival lacunae, bias, etc.
 To convincingly make arguments from a historical data description, you must back it up using triangulation–approaching the problem from many angles. That triangulation may be computational, archival, archaeological, or however else you’re used to historying, but we’ll focus here on computational.
---
![You are the spoon](https://media.giphy.com/media/hVKz6wRT0POuI/giphy.gif)
### Thanks!
