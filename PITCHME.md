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
- short answer: a lot of breadth |
- But still some depth on what are networks |
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
### But first, what is a network?
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

Note: let's open up palladio > tool developed by stanford > load in data  > make a graph > is this a network? yes > is this meaningful though? probably not > what's missing? hypothesis SPEND 5-8 minutes
---
@title[Digital History First Steps]
### First Step in Digital History
- HYPOTHESIS!!! |  
- What sort of questions can we ask about this data? |

Note: if we think of this as a social network > spend some time writting these into github issues, is this enough though... we can think about hypotheses but we also need to talk about methods and hypotheses. but can we really make a hypothesis without understanding our methods? hypotheses are great but also need to understand our methods > chicken and egg of digital history > where do you start > has to be both
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

Note:what's the shape > strucuture or topology tells you about how centralized/decentralized, sparse or dense your network is > helps identify components or connected nodes, let's look at some of the metrics available in network navigator > shape of the network (topology) > all of these metrics are helping us understand how the network is representing this dataset > difference between dataset and network (abstract vs concrete relationships) > proabilities over certainties > idea of homophilly
---
@title[NetworkX]
### NetworkX
[NetworkX Library](https://networkx.github.io/documentation/stable/)
- bipartite -> a network where nodes only have relationships with another group of nodes |
<!-- binder link -->

Note: why didn't our initial network though? thoughts? it's because it's a bipartite network. very common in DH, but has a lot of issues. Scott has a great piece about working with bipartite networks and their issues. We can check if a network is bipartite by looking through our table of data or more easily using networkx. NetworkX is a python library that is designed for building networks and analyzing them. Up to now we've looked at out of the box tools for studying networks. A few others that are really common are Gephi and Cytoscape. I'm going to give you a link to a notebook running python code in the cloud from our github repo so that you can follow along. We'll go along the script a bit > launch binder
---
### Algorithms & Networks
- Return to our initial questions |
- How might an algorithm help us answer them? |
- Better yet what is an algorithm even? |
![Hugo Weaving Boss](https://media.giphy.com/media/saD01LsKDzxL2/giphy.gif)
---
<!-- gif of scared face at mention of algorithms -->
Note: what makes networks so powerful is a) how they represent relationships b) algorithms designed to leverage those representations
---
> "Put simply: digital humanists do not need to understand algorithms *at all*. They do need, however, to understand the transformations that algorithms attempt to bring about. If we do so, our practice will be more effective and more likely to be truly original." 
> [Do Digital Humanists Need to Understand Algorithms?
Ben Schmidt (one of your instructors), Debates in Digital Humanities (2016)](http://dhdebates.gc.cuny.edu/debates/text/99)
- louvain community detection -> optimization of modularity, which is the density of edges inside communities to edges outside communities. |
- visualize the output of this algorithm with our dataset and the game of thrones dataset |
Note: Thing to understand about most algorithms and stats is that it is generally looking for measurements of centrality or varience, and that simply is often better
---
### first code review:
- what sorts of research questions work well with networks? 
- how can networks further historical arguments?
- what sorts of critiques can we make of networks?
- what might we do next with these data sets to actually make historical arguments?
 http://scottbot.net/argument-clinic/
- "Without having a ground against which to contextualize our results, a base map like general population, the fact of which cities voted in which direction gives us little historical meat to chew on."
#### CORE OF DIGITAL HISTORY: deviations from expectation, or deviations from internal consistency.
---
BREAK
---
# What's left?
### Time to Enter the Matrix
Note: Data curation & data visualization
---
### No like literally let's talk about adjancency matrices
Note: Who is working on social networks? Whose data is nicely formatted in tables?
alternative network data: text
great option for automatted data collection. also let's us think of other 
---
show off NER and counting
---
matrices and vectors
Note: Many undirected networks csn be represented by matrices. Benefits lot easier to understand what's happening, a very different way of thinking/making an argument about networks. Matrices are also a really foundational data structure for any digital history project > use it image analysis, text mining, etc... 
---
network visualizations
bokeh with python
d3
Note: thinking beyond force layout helps think how visualization is part of your arguments > start thinking about networks not simply as force layouts but actually
---
Scott's lessons for digital historians

1. Uncareful Appropriation – Collaboration "sidestep the issue of accidentally misusing a method by collaborating with someone who knows how the method works."
2. Reliance on Imports – Statistical Training

3. Naive Scientism – Humanities History "If we want to combat the uncareful use of proxies in digital history, we need only to teach the history of the humanities; why the cultural turn happened, what’s gone wrong with positivistic approaches to history in the past, etc."
4. False Precision & Certainty – Simulation & Triangulation "means trying to reach the same conclusion using multiple different methods in parallel, and seeing if they all agree. "
5. Quantitative Blinders – Rejecting Digital History "Avoiding quantitative blinders – that is, the tendency to only care about what’s easily countable"
http://scottbot.net/lessons-from-digital-historys-antecedents/
---
Final code review:
what would you want to learn more about?
how might you go about doing that?
what data do you need to collect?
--- 
no one is an impostor. 
we're all starting from somewhere

Even if no alternate hypothesis presents itself, and all of your tests agree with your hypothesis, you still do not have causal proof.
 Be sure to take time to consider what’s missing from the dataset, due to archival lacunae, bias, etc.
 To convincingly make arguments from a historical data description, you must back it up using triangulation–approaching the problem from many angles. That triangulation may be computational, archival, archaeological, or however else you’re used to historying, but we’ll focus here on computational.

 Todo:
 network navigator
 bipartite network
 community detection

d3 network colorized

 matrices
 ner vs. set list
 count co-occurences
 look at communities detected
bokeh vs d3
how do we critique networks as historians?
how do we understand visualizations as part of our argumentation?
or statistics and measurements for that matter?
micki kaufman project
