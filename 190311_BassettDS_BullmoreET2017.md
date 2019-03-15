<!--
Filename: 	190311_BassettDS_BullmoreET2017.md
Project: 	/Users/shume/Documents/Cahier
Author: 	shumez <https://github.com/shumez>
Created: 	2019-03-11 20:23:9
Modified: 	2019-03-15 21:40:44
-----
Copyright (c) 2019 shumez
-->

# 19-03-11 Small-World Brain Networks Revisited

Bassett, D.S. and Bullmore, E.T., 2017. Small-world brain networks revisited. The Neuroscientist, 23(5), pp.499-516.

[Original][orig] | [Mendeley][mend]

## Contents

00. [Abstract](#Abstract)
01. [Small Worlds, Watts and Strogatz](#Small-Worlds,-Watts-and-Strogatz)
	* [Small-World Brain Graphs](#Small-World-Brain-Graphs)
02. [What Have We (Not) Learnt Since 2006?](#What-Have-We-(Not)-Learnt-Since-2006?)
	* [Universality](#Universality)
	* [Economical Small-World Networks](#Economical-Small-World-Networks)
	* [Small-Worldness Is Not the Whole Story](#Small-Worldness-Is-Not-the-Whole-Story)
03. [Challenges to Small-Worldness](#Challenges-to-Small-Worldness)
	* [Binary Graphs](#Binary-Graphs)
	* [Weighted Graphs](#Weighted-Graphs)
	* [The Small-World Propensity](#The-Small-World-Propensity)
04. [Twenty-First Century Tract-Tracing](#Twenty-First-Century-Tract-Tracing)
	* [Small-Worldness of Binary Tract-Tracing Networks](#Small-Worldness-of-Binary-Tract-Tracing-Networks)
	* [Small-Worldness of Weighted Tract-Tracing Networks](#Small-Worldness-of-Weighted-Tract-Tracing-Networks)
	* [Weighted Small-Worldness and the Role of Edge Weights](#Weighted-Small-Worldness-and-the-Role-of-Edge-Weights)
05. [The Utility of Weak Connections](#The-Utility-of-Weak-Connections)
06. [Conclusions](#Conclusions)

## 0. Abstract

> It is nearly 20 years since the concept of a small-world network was first quantitatively defined, by a combination of high clustering and short path length; and about 10 years since this metric of complex network topology began to be widely applied to analysis of neuroimaging and other neuroscience data as part of the rapid growth of the new field of connectomics. Here, we review briefly the foundational concepts of graph theoretical estimation and generation of small-world networks. We take stock of some of the key developments in the field in the past decade and we consider in some detail the implications of recent studies using high-resolution tract-tracing methods to map the anatomical networks of the macaque and the mouse. In doing so, we draw attention to the important methodological distinction between topological analysis of binary or unweighted graphs, which have provided a popular but simple approach to brain network analysis in the past, and the topology of weighted graphs, which retain more biologically relevant information and are more appropriate to the increasingly sophisticated data on brain connectivity emerging from contemporary tract-tracing and other imaging studies. We conclude by highlighting some possible future trends in the further development of weighted small-worldness as part of a deeper and broader understanding of the topology and the functional value of the strong and weak links between areas of mammalian cortex.


## 1. Small Worlds, Watts and Strogatz

> Small-worldness now seems to be a ubiquitous characteristic of many complex systems; but its first, and still most familiar, appearance was in the form of social networks. We know that as individual agents (nodes) in a social network, we are connected by strong familial and friendship ties (edges) to a relatively few people who are likely also strongly connected to each other, forming a social clique, family or tribe. Yet we also know that we can travel far away from our tribal network, to physically remote cultures and places, and sometimes be surprised there to meet people—often “friends-of-friends”—who are quite closely connected to our home tribe: “it’s a small world,” we say. This common intuition was experimentally investigated by [Milgram (1967)][1967MilgramS], who asked people in the Midwest of the United States (Omaha, Nebraska) to forward a letter addressed to an unknown individual in Boston by posting it to the friend or acquaintance in their social network that they thought might know someone else who would know the addressee ([Fig. 1][fig01]). It was discovered, on average over multiple trials of this procedure, that the letters successfully reaching Boston had been passed through 6 intermediate postings, which was considered much less than expected given the geographical distance between source and target addresses. In the language of graph theory, the characteristic path length of Milgram’s social networks was short.

[![figure.1][fig01]][fig01]
> Figure 1. An illustration of the shortest path between Omaha and Boston in [Milgram’s social network experiment, published in Psychology Today in 1967][1967MilgramS]. Here, the results of multiple experiments are represented as a composite shortest path between the source (a person in Omaha) and the target (a person in Boston). A letter addressed to the target was given to the source, who was asked to send it on (with the same instructions) to the friend or acquaintance that they thought was most likely to know the target, or someone else who might know the target personally. It was found that most letters that eventually reached the correct address in Boston passed through six intermediaries between source and target (denoted 1st remove, 2nd remove, etc.), popularizing the notion that each of us is separated by no more than “six degrees of freedom” from any other individual in a geographically distributed social network. Reproduced with permission from [Milgram (1967)][1967MilgramS].

> Famously, [Watts and Strogatz (1998)][1998StrogatzSH_WattsDJ] combined this concept of path length (the minimum number of edges needed to make a connection between nodes) with a measure of topological clustering or cliquishness of edges between nodes ([Fig. 2][fig02]). More formally, clustering measures the probability that the nodes ![][j] and ![][k] which are both directly connected to node ![][i] are also directly connected to each other; this is equivalent to measuring the proportion of closed triangular three-node motifs in a network ([Sporns and Kötter 2004][2004KötterR_SpornsO]). **Watts and Strogatz (WS)** explored the behavior of path length and clustering in a simple generative model (henceforth the **WS model**) ([Fig. 3][fig03]). Starting with a binary lattice network of ![][N] nodes each connected to the same number of nearest neighbors, by edges of identical weight (unity), the WS model iteratively rewires the lattice by **randomly deleting an existing edge, between nodes ![][i] and ![][j] and replacing it by a new edge between node ![][i] and any node ![][k\neq&space;j]**. They found that as the probability of random rewiring was incrementally increased from zero, so that the original lattice was progressively randomized, sparsely rewired networks demonstrated both high clustering (like a lattice) and short path length (like a random graph). By analogy to social networks, these algorithmically generated graphs were called small-world networks.

[![figure.2][fig02]][fig02]
> Figure 2. Diagrams of clustering and path length in binary and weighted networks. (A) In a binary network, all edges have the same weight, and that is a weight equal to unity. In this example of a binary graph, if one wishes to walk along the shortest path from the orange node to the green node, then one would choose to walk along the edges highlighted in red, rather than along the edges highlighted in blue. We also note that the clustering coefficient of the green node is equal to 1 (all neighbors are also connected to each other to form a closed triangular motif), while the clustering coefficient of the orange node is =1 (only three out of five neighbors are also connected to each other). (B) In a weighted graph, edges can have different weights. In this example, edges have weights of ![][\frac{3}{3}=1], ![][\frac{2}{3}=0.66], and ![][\frac{1}{3}=0.33]. If one wishes to traverse the graph from the orange node to the green node along the shortest path, one would choose to follow the path along the edges with weight equal to unity (stronger weights are equivalent to shorter topological distance). Note also that because the edges are now weighted, neither the orange nor the green nodes has a clustering coefficient equal to unity.

[![figure.3][fig03]][fig03]
> Figure 3. The Watts–Strogatz model and the generation of small-world networks. The canonical model of a small-world network is that described by Duncan Watts and Steve Strogatz in their 1998 article in Nature. The model begins with a regular lattice network in which each node is placed along the circumference of a circle, and is connected to its k nearest neighbors on that circle. Then, with probability p edges are rewired uniformly at random such that (1) at ![][p=0] the network is a lattice and (2) at ![][p=1] the network is random. Interestingly, at intermediate values of p the network has so-called “small-world” characteristics with significant local clustering (from the lattice model) and short average path length facilitated by the topological short-cuts created during the random rewiring procedure. Because this architecture can be defined mathematically, small-world graphs have proven fundamental in understanding game theory ([Li and Cao 2009][2009CaoL_LiX]) and even testing analytical results in subfields of mathematics ([Konishi and Hara 2011][2011HaraN_KonishiK]). Yet, while this work provided a qualitative model of a small-world graph, it did not give a statistic to measure the degree of small-worldness in a particular data set. As a simple scalar measure of “small-worldness,” Humphries and colleagues defined the small-world index, σ to be the ratio of the clustering coefficient (normalized by that expected in a random graph) to the average shortest path length (also normalized by that expected in a random graph) ([Humphries and others 2006][2006PrescottTJ_HumphriesMD]). The intuition here is that this index should be large (in particular, ![][\sigma>1] when the clustering coefficient is much greater than expected in the random graph, and the average shortest path length is comparable to that expected in a random graph. Since this initial definition, other extensions have been proposed and utilized ([Telesford and others 2011][2011LaurientiPJ_TelesfordQK]; [Toppi and others 2012][2012AstolfiL_ToppiJ]), building on the same general notions.


> In addition to introducing this generative model, [Watts and Strogatz (1998)][1998StrogatzSH_WattsDJ] also showed how small-worldness could be estimated in naturally occurring networks. The hybrid combination of high clustering and short path length that emerged in sparsely rewired WS networks was proposed as a general quantitative measure of small-worldness in other networks. It was shown immediately that a nervous system was among the real-world networks that shared the small-world pattern of topological organization. Using data on the synaptic and gap junction connectivity between all ![][N=302] neurons in the nervous system of Caenorhabditis elegans ([White and others 1986][1986WhiteJG]), a binary undirected graph was constructed representing each neuron as an identical node and each synapse (~5000) or gap junction (~600) as an identical, unweighted and undirected edge between nodes. This graph of about 5600 edges between 302 nodes was sparsely connected: only about 12% of the maximum possible number of synaptic connections, ![][\frac{N^2-N}{2}=45451], actually existed. Compared with a random graph of ![][\frac{N^2-N}{2}=45451] nodes, C. elegans had **high clustering ![][\Gamma\sim5.6]** and **short path length ![][\Lambda\sim1.18]**. Thus the C. elegans connectome was small-world, in the same quantitative sense as the networks generated by the WS model at low rewiring probabilities, less than 10%. But note that does not necessarily mean that the C. elegans connectome was biologically generated by the WS algorithm of random rewiring of established connections (axonal projections) between neurons. To put it another way, the WS model can generate small-world networks but not all small-world networks were generated by a WS model. (And the WS model does not seem like a biologically plausible generative model for brain networks ([Betzel and others 2016a][2016VanDenHeuvelM_BetzelRF]; [Vértes and others 2012][2012BullmoreET_VértesPE]; [Vértes and others 2014][2014BullmoreET_VértesPE]).)


### Small-World Brain Graphs

> Following the small-world analysis of C. elegans, pioneering topological studies of mammalian cortical networks used databases of tract-tracing experiments to demonstrate that the cat and macaque interareal anatomical networks shared similar small-world properties of short path length and high clustering ([Hilgetag and Kaiser 2004][2004KaiserM_HilgetagCC]; [Sporns and Zwi 2004][2004ZwiJD_SpornsO]). The first graph theoretical studies of neuroimaging data demonstrated that large-scale interareal networks of functional and structural connectivity in the human brain also had small-world properties ([Bassett and others 2006][2006BullmoreE_BassettDS]; [Salvador and others 2005][2005BullmoreE_SalvadorR]; [Vaessen and others 2010][2010BackesWH_VaessenMJ]). These and other seminal discoveries were central to the emergence of connectomics as a major growth point of network neuroscience ([Sporns and others 2005][2005KötterR_SpornsO]).

> About 10 years ago, we reviewed these and other data in support of the idea that the brain is a small world network ([Bassett and Bullmore 2006][2006BullmoreE_BassettDS]). Here, we aim to take another look at the concept of small-worldness, one or two decades since it was first formulated quantitatively and applied to brain network analysis at microscopic and macroscopic scales of anatomical resolution. First, we review some of the key questions about small-worldness that have been a focus of work in the period 2006–2016; then we review the technical evidence for small-worldness in high resolution tract-tracing data from the macaque and the mouse; finally, we highlight some likely trends in the further evolution of small-worldness as part of a deeper understanding of the topology of weighted brain graphs.


## 2. What Have We (Not) Learnt Since 2006?

> We have learnt a lot about complex topological organization of nervous systems since 2006, as evidenced by rapid growth in research articles, reviews, and citations related to “brain graphs” and “connectomes” ([Bullmore and Bassett 2011][2011BassettDS_Bullmore]; [Bullmore and Sporns 2009][2009SpornsO_BullmoreE]; [Pessoa 2014][2014PessoaL]); by the publication of several textbooks ([Fornito and others 2016][2016BullmoreET_FornitoA]; [Sporns 2011][2011SpornsO]); and by the recent launch of new specialist journals for network neuroscience. This emerging field of brain topology has grown much bigger than the foundational concept of small-worldness. But what have we learnt more specifically about brain small-worldness since 2006, and what do we still have to learn?


### Universality

> There is no doubt that small-worldness—the combination of non-random clustering with near-random path length—has been very frequently reported across a wide range of neuroscience studies. Small-world topology has been highly replicated across multiple species and scales from structural and functional MRI studies of large-scale brain networks in humans to multielectrode array recordings of cellular networks in cultures ([Bettencourt and others 2007][2007GrossGW_BettencourtLM]) and intact animals ([van den Heuvel and others 2016][2016SpornsO_VanDenHeuvelMP]). It seems reasonable to conclude that small-worldness is at least very common in network neuroscience; but is it a universal property of nervous systems? Universality is a strong claim and difficult to [affirm](. "断言する") conclusively. As Popper noted in his philosophy of science by hypothetical [refutation](. "論破") ([Popper 1963][1963PopperKR]), the universal hypothesis that “all swans are white” can only be affirmed conclusively by a complete survey of every swan in the world. Whereas it can be immediately and decisively refuted by the observation of a single black swan. Similarly, the claim that all brains have small-world topology has not yet been (and never will be) affirmed by a complete connectomic mapping of every brain in the world. Some apparent counter-examples of brain networks that do not have small-world topology have been reported and deserve careful consideration as possible *Popperian black swans* ([see below][]). However, we can provisionally conclude that enough evidence has [amassed](. "蓄える") to judge that small-worldness is a nearly universal property of nervous systems. Indeed, it seems likely that brains are only one of a large “universality class” of small-world networks comprising also many other non-neural or non-biological complex systems. Such near-universality of small-worldness, or any other brain network parameter, has a number of implications.

> First, near-universality implies **self-similarity**. If the macroscale interareal network of the human brain is small-world, as is the microscale interneuronal network of the worm or the fly, then we should expect also that the microscale interneuronal network of the human brain is small-world. Self-similarity of small-worldness would be indexed by scale invariance of network path length and clustering parameters as the anatomical resolution “zooms in” from macro- to microscales. Although there is abundant evidence for scaling, fractal or self-similar statistics in many aspects of brain network topology ([Bassett and others 2010][2010BullmoreET_BassettDS]; [Bullmore and others 2009][2009SucklingJ_BullmoreET]; [Klimm and others 2014][2014MuchaPJ_KlimmF]), experimental data do not yet exist that could support a multiscale, macro-to-micro analysis of small-worldness (and other network properties) in the same (human or mammalian) nervous system ([Bassett and Siebenhuhner 2013][2013SiebenhuhnerF_BassettDS]).

> Second, near-universality suggests some very general selection pressures might be operative on the **evolution and development** of nervous systems across scales and species. This line of thinking has led to the formulation of generative models that can simulate brain networks by some probabilistic growth rule or genetic algorithm. It has been found that simple generative models, that add edges to a network based on the spatial distance and the topological relationships between nodes, can [recapitulate](. "要約する") small-worldness and many other properties of the connectome on the basis of two (spatial and topological) parameters ([Betzel and others 2016a][2016VanDenHeuvelM_BetzelRF]; [Vértes and others 2012][2012BullmoreET_VértesPE]; [Vértes and others 2014][2014BullmoreET_VértesPE]). This serves as a reminder that the network phenotype of small-worldness can be generated by many different mechanisms and the biological mechanisms controlling formation of small-world properties in brain networks currently remain unknown.

> Third, and from a somewhat more controversial perspective, universality might seem [tantamount to](. "同然だ") **triviality**. If the brain is everywhere small-world, and so are almost all other complex systems in real life ([Bassett and Bullmore 2006][2006BullmoreE_BassettDS]; [Bullmore and others 2009][2009SucklingJ_BullmoreET]; [Gaiteri and others 2014][2014SibilleE_GaiteriC]; [Moslonka-Lefebvre and others 2011][2011PautassoM_Moslonka-LefebvreM]; [Sizemore and others 2016][2016BassettDS_SizemoreA]) (for a few exceptions, see [Koschutzki and others 2010][2010SchreiberF_KoschutzkiD]), then what is the small-worldness of the brain telling us that’s of any interest specifically to neuroscience? There are two main answers to this important question, as we discuss in more detail below: (1) studies have recently succeeded in linking network topological metrics to biological concepts, like wiring cost ([Bassett and others 2010][2010BullmoreET_BassettDS]; [Bassett and others 2011a][2011GraftonST_BassettDS]; [Bullmore and Sporns 2012][2012SpornsO_BullomoreET]; [Rubinov and others 2015][2015BullmoreET_RubinovM]), and to biological phenotypes, like neuronal density ([Aćimović and others 2015][2015LinneML_AćimovićJ]; [van den Heuvel and others 2015][2015deReusMA_VanDenHeuvel]) or gene expression ([Fulcher and Fornito 2016][2016FornitoA_FulcherBD]) and (2) small-worldness is not the whole story of brain network organization ([Wang and Kennedy 2016][2016KennedyH_WangXJ]).


### Economical Small-World Networks

> At the risk of stating the obvious, small-worldness is a purely topological quantity that tells us nothing about the physical layout of the nodes or edges that constitute the graph ([Bassett and others 2010][2010BassettDS]; [Pessoa 2014][2014PessoaL]). However, it is equally obvious that brain networks are embedded in anatomical space ([Bassett and others 2011a][2011BassettDS]; [Klimm and others 2014][2014KlimmF]; [Lohse and others 2014][2014LohseC]). Somehow the abstract, dimensionless topology of small-worldness must be [reconciled](. "一致させる") to the anatomy of the brain. It turns out that the small-world topology of brain networks is (almost) always economically embedded in physical space ([Bullmore and Sporns 2012][2012SpornsO_BullmoreE]; [Kaiser and Hilgetag 2006][2006HilgetagCC_KaiserM]).

> For both clustering and path length, the two topological metrics combined in the hybrid small-world estimator, there is a strong relationship with brain anatomical space ([Bassett and others 2010][2010BassettDS]; [Bassett and others 2011a][2011BassettDS]; [Rubinov and others 2015][2015RubinovM]). The edges between clustered nodes tend to be shorter distance whereas the edges that mediate topological short cuts tend to traverse longer anatomical distances. Interpreting the **Euclidean distance** between brain regional nodes or neurons as a [proxy](. "委任状, 代理") for the wiring cost, that is, the total biological cost of building a physical connection and maintaining communication between nodes, it has been argued that the brain is an economical small-world network ([Bullmore and Sporns 2012][2012SpornsO_BullmoreE]; [Latora and Marchiori 2001][2001MarchioriM_LatoraV]). Economical in this sense does not simply mean parsimonious or cheap; it is more closely related to the common-sense notion of “value for money”. Topologically clustered nodes are anatomically co-located and thereby nearly minimize wiring cost. But small-world brain networks are not naturally lattices and if they are computationally rewired strictly to minimize wiring cost then brain networks are topologically penalized, losing integrative capacity indexed by increased characteristic path length and thus reduced **small-worldness scalar** ![][\sigma]

> The economical idea is that brain networks have been selected by the competition between a pressure to minimize biological cost versus a pressure to maximize topological integration. More formally,

> ![eq.01][P_{i,j}\sim&space;f(d_{i,j})f(k_{i,j})]
<!-- \[ P_{i,j} ~ f(d_{i,j})f(k_{i,j})\], -->

> the probability of a connection between nodes ![][i] and ![][j], ![][P_{i,j}], is a product of: a function of the physical distance in mm between nodes ![][d_{i,j}]—often used as a proxy for **wiring cost**—and a function of the topological relationship between nodes ![][k_{i,j}].

> Typically, the functions of cost and topology are each parameterized by a single parameter, for example, simple exponential and power law functions. Several variants of this approach have been published, exploring a range of different topological relationships ![][k_{i,j}] between nodes, for example, clustering and homophily ([Betzel and others 2016a][2016SpornsO_BetzelRF]; [Vértes and others 2012][2012BullmoreET_VértesPE]; [Vértes and others 2014][2014BullmoreET_VértesPE]). Economical models can generally reproduce the small world properties of brain networks quite realistically: clustering and path length are both increased as a function of the cost parameter (Avena-Koenigsberger and others 2014). In other words, as the cost penalty becomes the dominant factor predicting the probability of a connection between nodes, economical models generate increasingly lattice-like networks, with strong spatial and topological clustering of connected nodes, approximating in the limit the minimal cost configuration of the network. The emergence of more integrative network features—such as hubs mediating many intermodular connections—typically depends on some degree of relaxation of the cost penalty (reduced distance parameter) relative to the parameter controlling the importance of (integrative) topological relationships between nodes in predicting their connectivity. Thus, small-world networks can be generated by economical models for a certain range of the two parameters controlling the competitive factors of **(wiring) cost** and **(topological) value**.



### Small-Worldness Is Not the Whole Story

> Before getting further into the details of small-worldness, as we do below in relation to recent tract-tracing results, it is important to acknowledge that the specific metrics of **path length ![][\Lambda]** and **clustering ![][\Gamma]** introduced by [Watts and Strogatz (1998)][1998StrogatzSH_WattsDJ], and the **small-worldness scalar** derived from them ![][\sigma=\frac{\Gamma}{\Lambda}] ([Humphries and others 2006][2006PrescottTJ_HumphriesMD]), are a few global topological metrics that have been of central importance to the growth of complex network science generally. But more than 15 years after the first discovery of small-world properties in brain networks, the field of connectomics now extends into many other areas of topological analysis. There is much important recent work on topological properties like **degree distribution** and **hubness** ([Achard and others 2006][2006BullmoreE_AchardS]), **modularity** ([Bassett and others 2011b][2011GraftonST_BassettDS]; [Chen and others 2008][2008EvansAC_ChenZJ]; [Mattar and others 2015][2015BassettDS_MattarMG]; [Meunier and others 2009][2009BullmoreE_MeunierD]; [Simon 1962][1962SimonH]; [Sporns and Betzel 2016][2016BetzelRF_SpornsO]; [Stoop and others 2013][2013StoopR_StoopR]), **core/periphery** organization ([Bassett and others 2013][2013GraftonST_BassettDS]; [Senden and others 2014][2014VanDenHeuvelMP_SendenM]; [van den Heuvel and Sporns 2011][2011SpornsO_VanDenHeuvelMP]), **controllability** ([Betzel and others 2016b][2016BassettDS_BetzelRF]; [Gu and others 2015][2015KahnAE_GuS]; [Muldoon and others 2016b][2016BassettDS_MuldoonSF]) and **navigability** ([Gulyás and others 2015][2015KrioulovD_GulyásA]) that are not simply related to small-worldness. It is nothing like a complete description of the brain to say it is small world; we now turn to a more technical discussion of the evidence for small-worldness as a common property of nervous systems.


## 3. Challenges to Small-Worldness

> About 3 to 4 years ago, an important series of papers began to be published that could be regarded as “black swans” refuting the general importance of small-worldness in an understanding of brain networks ([Knoblauch and others 2016][2016ToroczkaiZ_KnoblauchK]; [Markov and others 2013][2013KennedyH_MarkovNT]; [Markov and others 2014][2014SalletJ_MarkovNT]; [Song and others 2014][2014WangXJ_SongHF]):

>> Previous studies of low density inter-areal graphs and apparent small-world properties are challenged by data that reveal **high-density cortical graphs** in which economy of connections is achieved by weight heterogeneity and distance-weight correlations. ([Markov and others 2013][2013KennedyH_MarkovNT])

>> Recent connectomic tract tracing reveals that, contrary to what was previously thought, **the cortical inter-areal network has high density**. This finding leads to a necessary revision of the relevance of some of the graph theoretical notions, such as the small world property . . ., that have been claimed to characterise the inter-areal cortical network. ([Knoblauch and others 2016][2016ToroczkaiZ_KnoblauchK])

> These remarks carried weight because they were based on sophisticated and highly sensitive measurements of mammalian cortical connectivity ([Fig. 4][fig04]). In each one of multiple carefully standardized experiments in the macaque monkey, a fluorescent tracer was injected into a (target) cortical region where it was taken up by synaptic terminals and actively transported to the cell bodies of neurons projecting to the target region. When the animal’s brain was subsequently examined microscopically, the retrograde transport of the tracer from the injection site resulted in a fluorescent signal in the (source) regions of cortex that were directly connected to the target region. The basic technology of anatomical tract-tracing had been used by neuroanatomists since the late 20th century; but in the first decades of the 21st century it was possible to increase the scale and precision of the measurements dramatically, enabling the construction of connectivity matrices that summarized the strength or weight of axonal projections between a large number of cortical areas. These next-generation tract-tracing data thus represented a new standard of knowledge about mammalian cortical connectivity, that was more continuously quantified than the binary or ordinal rating of connectivity from traditional tract-tracing experiments ([Stephan and others 2001][2001KötterR_StephanKE]), and much less ambiguously related to the cellular substrates of brain networks than the statistical measures of functional connectivity ([Achard and others 2006][2006BullmoreET_AchardS]; [Zhang and others 2016][2016BassettDS_ZhangZ]) and structural covariance ([Alexander-Bloch and others 2013][2013BullmoreET_Alexander-BlochA]; [Bassett and others 2008][2008Meyer-LindenbergA_BassettDS]) used to build graphs from human neuroimaging data. It is clearly important to understand in some detail how the topology of brain networks can be modelled in contemporary tract-tracing data from the macaque (and subsequently the mouse ([Oh and others 2014][2014MortrudMT_OhSW]; [Rubinov and others 2015][2015BullmoreET_RubinovM])) and what these results tell us about the small-worldness of brain networks.

[![figure.4][fig04]][fig04]
> Figure 4. High density of the macaque cortical graph excludes sparse small world architecture. (A) Comparison of the average shortest path length and density of the macaque cortical graph from (Markov and others 2013) with the graphs of previous studies (Felleman and Van Essen 1991; Honey and others 2007; Jouve and others 1998; Markov and others 2012; Modha and Singh 2010; Young 1993). Sequential removal of weak connections causes an increase in the path length. Black triangle: macaque cortical graph from Markov and others (2013); gray area: 95% confidence interval following random removal of connections from the macaque cortical graph from Markov and others (2013). Jouve et al., 1998 predicted indicates values of the graph inferred using the published algorithm. (B) Effect of density on Watts and Strogatz’s formalization of a small-world network. Clustering and path length variations generated by edge rewiring with probability range indicated on the x-axis applied to regular lattices of increasingly higher densities. The pie charts show graph density encoded via colors for path length (![][L]) and clustering coefficient (C). The y-axis indicates the path length ratio (![][\frac{L_p}{L_o}]) and clustering ratio (![][\frac{C_p}{C_o}]) of the randomly rewired network, where ![][L_o] and ![][C_o] are the path length and clustering of the regular lattice, respectively. The variables ![][L_p] and ![][C_p] are the same quantities measured for the network rewired with probability ![][P]. Hence, for each density value indicated in the ![][L] and ![][C] pie charts, the corresponding ![][\frac{L_p}{L_o}] and ![][\frac{C_p}{C_o}] curves can be identified. Three diagrams below the x-axis indicate the lattice (left), sparsely rewired (middle), and the randomized (right) networks. (C) The small-world coefficient σ (Humphries and others 2006) corresponding to each lattice rewiring. Color code is the same as in panel (B). Dashed lines in (B) and (C) indicate 42% and 48% density levels, respectively. Reproduced with permission from Markov and others (2013).


### Binary Graphs

> In general, a node represents a component of a system and an edge represents a connection or interaction between two nodes. Mathematically, we can capture these ideas with a graph ![][G=(V,E)] composed of a node set ![][V] and an edge set ![][E]([Bollobás 1979][1979BollobásB], [1985][1985BollobásB]). We store this information in an association or weight matrix ![][W], whose ![][ij]th element indicates the strength or weight ![][w_{i,j}] of the edge between node ![][i] and node ![][j] A simple way of building a graph from such an association matrix is to apply a threshold ![][\tau] to each element of the matrix, such that if ![][w_{i,j}≥\tau] then an edge is drawn between the corresponding nodes, but if ![][w_{i,j}<\tau] no edge is drawn ([Achard and others 2006][2006BullmoreET_AchardS]). This thresholding operation thus binarizes the weight matrix and converts the continuously variable edge weights to either 1 (suprathreshold) or 0 (subthreshold). It was on this basis that almost all brain graphs were constructed in the 15 years or so following the seminal small-world analysis of a binary graph representing the cellular connectome of C. elegans ([Watts and Strogatz 1998][1998StrogatzSH_WattsDJ]). Most of the neuroimaging evidence for small-worldness in human brain networks, for example, is based on analysis of binary graphs constructed by thresholding a correlation coefficient or equivalent estimator of the weight of functional or structural connectivity or structural covariance between regions ![][i] and ![][j] ([van Wijk and others 2010][2010DaffertshoferA_vanWijkBC]). It is well recognized that construction of binary graphs represents an extreme simplification of brain networks; indeed, a binary undirected graph of homogenous nodes is as simple as it gets in graph theory ([Bassett and others 2012a][2012LimKO_BassettDS]). However, this approach has historically been preferred in neuroimaging because of limited signal-to-noise ratio in the data ([Achard and others 2006][2006BullmoreET_AchardS]).

> By varying the threshold ![][\tau] used to construct a binary graph from a continuous weight matrix, the connection density of the network is made denser or sparser. If the threshold is low and many weak weights are added to the graph as edges then the connection density will increase; if the threshold is high and only the strongest weights are represented as edges, then the connection density will decrease. The connection density ![][D] is quantified by the number of edges ![][E] in the graph as a proportion of the total number of edges in a fully connected network of the same number of nodes ![][N]:

<!-- \[D=\frac{E}{\frac{N^2−N}{2}}\] -->
![][D=\frac{E}{\frac{N^2-N}{2}}]

> Often, this proportion is translated into a percentage. In many neuroimaging studies, the threshold is set to a large value to control for the high levels of noise in MRI data, resulting in connection densities in the range 5% to 30% ([Lynall and others 2010][2010BullmoreE_LynallME]). In many of the first generation tract tracing studies, the connectivity data were collected on a binary or ordinal scale, and not all possible connections had been experimentally measured, so these data were naturally modelled as binary graphs with connection densities ~30% a value that was constrained by the completeness and quality of the data ([Bassett and Bullmore 2006][2006BullmoreE_BassettDS]).

> The small-world topology of a binary brain graph is defined by estimating two parameters in the data, **path length** ![][L] and **clustering** ![][C] ([Fig. 2A][fig02]), and comparing each of these observed parameters to their distributions under a specified null model ([Humphries and others 2006][2006PrescottTJ_HumphriesMD]). More specifically,

<!-- \[L=\frac{1}{N}\sum l_{i,j}\] -->
![][L=\frac{1}{N}\sum&space;l_{i,j}]

> is the global or characteristic path length, where ![][l_{i,j}] is the **shortest path (geodesic)** between nodes ![][i] and ![][j]; and

<!-- \[C=\frac{1}{N}\sum c_{i,j}\] -->
![][C=\frac{1}{N}\sum&space;c_{i,j}]

(![][c_i:=\frac{L_i}{\frac{k_i(k_i-1)}{2}}])

> is the global **clustering coefficient**, where ![][c_{i,j}] is the number of closed triangular motifs including node ![][i]. Each of these parameters is normalized by its value in a binary graph representing the null hypothesis. For example, if the null hypothesis is that clustering of brain networks ![][C_{\text{brain}}] is no different from the clustering of a random graph, then it is reasonable to generate an **Erdös–Renyí graph** for ![][N] nodes and ![][D] connection density, measure the clustering coefficient in the random graph ![][C_{\text{random}}], and use the ratio between brain and random graph clustering coefficients as a test statistic for non-random clustering. We note that there are many other possible ways in which a null model could be sampled, besides using the classical Erdös–Renyí model, and this is an active area of methodological research (Muldoon and others 2016a). However, in general one can define the **normalized clustering coefficient** as

<!-- \[Γ=\frac{C_{\text{brain}}}{C_{\text{random}}}\] -->
![][\Gamma=\frac{C_{\text{brain}}}{C_{\text{random}}}].


> Likewise, the path length of the brain graph can be normalized by its value in a comparable random graph

<!-- \[Λ=\frac{L_{\text{brain}}}{L_{\text{random}}}\] -->
![][\Lambda=\frac{L_{\text{brain}}}{L_{\text{random}}}].

> A small-worldness scalar can then be simply defined as

<!-- \[σ=\frac{Γ}{Λ}\] -->
![][\sigma=\frac{\Gamma}{\Lambda}].

 With these definitions, small-world networks will have ![][\sigma>1], ![][\Gamma>1] and ![][\Lambda\sim1] ([Humphries and others 2006][2006PrescottTJ_HumphriesMD]).



### Weighted Graphs

> Although binary graph analysis has predominated to date in analysis of brain networks, this certainly does not represent the methodological limit of graph theory for connectomics. For example, provided the data are of sufficient quality, there is no need to threshold the weight matrix to estimate topological properties like clustering, path length, and small-worldness. Indeed, while the binarization procedure was common in early applications of graph theory to neural data ([van Wijk and others 2010][2010DaffertshoferA_vanWijkBC]), it remains fundamentally [agnostic](. "曖昧な, はっきりしない") to architectural principles that may be encoded in edge weights ([Rubinov and Sporns 2011][2011SpornsO_RubinovM]). This realization has more generally motivated the field to develop methods that remain sensitive to the patterns of weights on the edges ([Ginestet and others 2011][2011SimmonsA_GinestetCE]), and to the topologies present in weak versus strong weights ([Rubinov and Sporns 2011][2011SpornsO_RubinovM]). These efforts have included the development of alternative thresholding schemes ([Bassett and others 2012a][2012LimKO_BassettDS]; [Lohse and others 2014][2014CarlsonJM_LohseC]) and fully weighted graph analysis ([Bassett and others 2011b][2011GraftonST_BassettDS]; [Rubinov and Sporns 2011][2011SpornsO_RubinovM]).

> The mathematical tools exist to estimate and simulate the topological properties of weighted networks, and analysis of weighted networks is akin to studying the geometry of the graph, rather than simply its topology ([Bassett and others 2012b][2012PorterMA_BassettDS]; [Bassett and others 2013][2013GraftonST_BassettDS]). For example, weighted analogues of binary metrics of clustering, path length and small-worldness can be defined formally ([Fig. 2B][fig02]). First, the weighted **clustering coefficient** of node ![][i] can be defined as 

<!-- \[C_{\text{weighted}} = \frac{1}{k_i(k_i−1)} \sum_{j,k}(\hat{w}_{ij}\hat{w}_{jk}\hat{w}_{ik})^{\frac{1}{3}}\] -->
![][C_{\text{weighted}}=\frac{1}{k_i(k_i-1)}\sum_{j,k}(\hat{w}_{ij}\hat{w}_{jk}\hat{w}_{ik})^{\frac{1}{3}}],

> where ![][k_i] is the number of edges connected to node ![][i], or degree of node ![][i] ([Onnela and others 2005][2005KaskiK_OnnelaJP]) (but see also [Barrat and others 2004][2004VespignaniA_BarratA]; [Zhang and Horvath 2005][2005HorvathS_ZhangB] for other similar definitions). The weighted path length can be defined as

<!-- \[L_{\text{weighted}} = \frac{1}{N(N−1)} \sum_{i≠j}δ_{ij}\] -->
![][L_{\text{weighted}}=\frac{1}{N(N-1)}\sum_{i\neq&space;j}\delta_{ij}],

> where the topological distance between two nodes is given by ![][\delta_{ij}=\frac{1}{w_{ij}}] ([Newman 2001][2001NewmanMEJ]). These two statistics can be combined to construct a weighted metric of small-worldness ([Bolaños and others 2013][2013AviyenteS_BolañosM]):

<!-- \[σ_{\text{weighted}}=\frac{Γ_{\text{weighted}}}{Λ_{\text{weighted}}}\] -->
![][\sigma_{\text{weighted}}=\frac{\Gamma_{\text{weighted}}}{\Lambda_{\text{weighted}}}].

> With these definitions, small-world networks will have ![][\Gamma_{\text{weighted}}>1], ![][\Lambda_{\text{weighted}}\sim1], and ![][\sigma_{\text{weighted}}>1] ([Humphries and others 2006][2006PrescottTJ_HumphriesMD]).


### The Small-World Propensity

> There are several important limitations to the definitions of small-worldness described in the previous sections. First, the small-world scalar ![][\sigma] (whether binary or weighted) can be greater than 1 even in cases when the normalized path length is much greater than one; because it is defined as a ratio, if ![][\gamma>>1] and ![][\lambda>1], the scalar ![][\sigma>1] This means that a small-world network will always have ![][\sigma>1], but not all networks with ![][\sigma>1] will be small-world (some of them may have greater path length than random graphs). Second, the measure is strongly driven by the density of the graph, and denser networks will naturally have smaller values of ![][\sigma] even if they are in fact generated from an identical small-world model. To address these and other limitations, Muldoon and colleagues recently developed a metric called the **small-world [propensity](. "傾向")**. Specifically, the small-world propensity, ![][\phi], reflects the deviation of a network’s clustering coefficient, ![][C_{\text{brain}}], and characteristic path length, ![][L_{\text{brain}}], from both lattice (![][C_{\text{lattice}}], ![][L_{\text{lattice}}]) and random (![][C_{\text{random}}], ![][L_{\text{random}}]) networks constructed with the same number of nodes and the same degree distribution:

<!-- \[ϕ=1−\sqrt{\frac{Δ^2_C+Δ^2_L}{2}}\] -->
![][\phi=1-\sqrt{\frac{\Delta^2_C+\Delta^2_L}{2}}],

> where

<!-- \[ΔC=\frac{C_{\text{lattice}}−C_{\text{brain}}}{C_{\text{lattice}}−C_{\text{random}}}\] -->
![][\Delta&space;C=\frac{C_{\text{lattice}}-C_{\text{brain}}}{C_{\text{lattice}}-C_{\text{random}}}]

and

<!-- \[ΔL=\frac{L_{\text{brain}}−L_{\text{random}}}{L_{\text{lattice}}−L_{\text{random}}}\] -->
![][\Delta&space;L=\frac{L_{\text{brain}}-L_{\text{random}}}{L_{\text{lattice}}-L_{\text{random}}}].

> The ratio ![][\Delta_{C/L}] represents the fractional deviation of the metric ![][C_{\text{brain}}] or ![][L_{\text{brain}}]) from its respective null model (a lattice or random network). This quantity can be calculated for binary networks (using binary definitions of clustering and path length) or for weighted networks (using weighted definitions of clustering and path length). Networks are considered small-world if they have small-world propensity \(0.4<ϕ≤1\). However, this metric should be viewed as a continuous metric of small-worldness rather than a hard threshold (Muldoon and others 2016a).

> Importantly, the small-world propensity overcomes several limitations of previous scalar definitions of small-worldness (Muldoon and others 2016a). First, it can incorporate weighted estimates of both the clustering coefficient and path-length, thus being generally applicable to any neural data that can be represented as a weighted network. Second, it is density independent, meaning that it can be used to compare the relative small-worldness between two networks that have very different densities from one another. Third, the metric is informed by spatially-constrained null models (Bassett and others 2015; Expert and others 2011; Papadopoulus and others 2016) in which nodes have physical locations and the edges that correspond to the smallest Euclidean distance between nodes are assigned the highest weights (Barthélemy 2011) (Fig. 5).

[![figure.5][fig05]][fig05]
> Figure 5. Small-world propensity in weighted networks. Here, we illustrate an example of a generative small-world model, and its utility in estimating an empirical network’s small-world propensity. (A) We can extend the concept of a Watts–Strogatz model to weighted graphs by first building a lattice in which the edges are weighted by distance such that edges between spatially neighboring nodes have more strongly weighted than edges between spatially distant nodes. These edge weights can then be rewired with a probability, P, to create a weighted small-world network. (B) Weighted clustering coefficient and weighted path length can be estimated as a function of the rewiring parameter, P, and used to derive the small-world propensity of the graph compared with random and lattice benchmarks (Eq. 11). (C) Weighted small-world propensity calculated for the same network as in panel (B). Error bars represent the standard error of the mean calculated over 50 simulations, and the shaded regions represent the range denoted as small-world. (D) Weighted small-world propensity as a function of network density for a graph of 1000 nodes. Reproduced with permission from Muldoon and others (2016a).




## 4. Twenty-First Century Tract-Tracing

> The scale and quality of contemporary tract-tracing data, in both the macaque and the mouse, represents a step change in terms of sensitivity in detecting anatomical connections, or axonal projections, between cortical areas. Using retrograde tracer experiments it has proven possible to demonstrate reliably that pairs of regions in the macaque brain may be connected by one or a few axonal projections. Likewise, anterograde tracer experiments in the mouse have demonstrated that the minimal detectable weight of connectivity between cortical regions, that just exceeds the noise threshold, is equivalent to the projection of one or a few axons (Ypma and Bullmore 2016). This high sensitivity has led immediately to the recognition of a large number of weak and previously unreported axonal connections. In the macaque, it was estimated that 36% of connections identified by contemporary tract tracing were so-called new found projections (NFPs) that had not been described in the prior literature (Markov and others 2014). The existence of so many weak connections is reflected in the log normal distributions of connectivity weight, ranging over five to six orders of magnitude, in both the macaque and the mouse (Ercsey-Ravasz and others 2013; Oh and others 2014). In short, tract-tracing can now resolve connections approximately equivalent to a single axonal projection and approximately a million times weaker than the strongest anatomical connections or white matter tracts.

> How can we use graph theory to model the network organization of such highly sensitive, highly variable data? Perhaps the simplest approach, borrowing from prior studies of less high quality datasets, is to apply a threshold and convert the log-normal weight matrix into a binary adjacency matrix. If the threshold is defined by the noise distribution of the measurements then it will be very close to zero for these sophisticated experiments, and correspondingly the connection density of the binary graph will be high. In the macaque, the connection density of a binary graph of 29 visual cortical areas was estimated to be 66% (Markov and others 2013), considerably higher than historical estimates in the range of 25% to 45% (Fellemen and Van Essen 1991). In the mouse, the connection density of a binary graph of 308 areas of the whole cortex was estimated to be 53% (Rubinov and others 2015).

> In other words, the binary graphs generated from 21st century tract-tracing data are about twice as dense as the much sparser networks derived from human neuroimaging and 20th century tract-tracing. They are also considerably denser than brain networks constructed at a finer grained (ultimately cellular) resolution. For example, the connection density of the C elegans nervous system, which is still the only completely mapped synaptic connectome, is about 12%. It is easy to see that the connection density of a binary network depends on the number of neurons comprising each node. In the limit, if the nervous system is parcellated into two large nodes the connection density will certainly be 100%; as the same system is parcellated into a larger number of smaller nodes its connection density will monotonically decrease (Bassett and others 2011a; Zalesky and others 2010). Thus, the current interval estimate of mammalian cortical connection density ~55% to 65% is conditional both on the anatomical resolution of the parcellation scheme used to define the nodes and the sensitivity of the tract-tracing methods used to estimate the weights of the edges.


### Small-Worldness of Binary Tract-Tracing Networks

> Having constructed a high-density binary graph from tract-tracing data on mammalian cortex, it is straightforward to estimate its clustering and path length, using the same metrics as for sparser binary graphs. However, simply because there is a larger number of connections in the denser network, its clustering will be considerably higher (there will be more closed triangular motifs) and its path length will be shorter (there will be more direct, pairwise connections) than a sparser network. Indeed, the clustering and path length of any binary graph at 60% connection density will be close to the maximal clustering and minimal path length of a fully connected graph; and therefore the clustering and path length of a 60% dense brain network will be very similar to the clustering and path length of a 60% random network (Bassett and others 2009).

> This means that when clustering and path length in brain networks are normalized by their corresponding values in equally dense random networks, the scaled metrics \(Γ\) and \(Λ\) will both be close to 1, and the small-world scalar \(σ\) will be close to its critical value of 1 (Markov and others 2013). For the macaque, at 66% connection density, \(Γ=1.21±0.014\), \(Λ=1.00±0.000\), and \(σ=1.21±0.014\); for the mouse, at 53% connection density, \(Γ=1.31±0.004\), \(Λ=1.00±0.000\), and \(σ=1.31±0.004\) (all given in mean ± standard deviation; Fig. 6A and C; Table 1). Since small-worldness has been traditionally defined as \(σ>1\), these results suggest that dense binary graphs constructed from tract tracing data are small-world, although the macaque is more similar to a random network than the mouse.

[![figure.6][fig06]][fig06]
> Figure 6. Binary and weighted small-worldness in mouse and macaque connectomes. For the macaque connectome reported in Markov and others (2013), we show (A) the binary network, a random graph of the same size and density, and the estimated small-world parameters \(Γ\) (normalized clustering coefficient), Λ (normalized path length), σ (classical small-world scalar) and φ (small world propensity). In panel (B) we show a weighted network analysis for the same data. For the mouse connectome reported in Rubinov and others (2015), we show (C) the weighted network, a random graph of the same size and density, and the estimated small-world parameters Γ (normalized clustering coefficient), Λ (normalized path length), \(σ\) (classical small-world scalar) and φ (small world propensity). In panel (D), we show a binary network analysis for the same data. In the boxplots, the gray dotted line shows the threshold value of σ = 1, and the purple area shows the range of values of 0.4 < φ ≤ 1 in which a network is considered small-world.

[![table.1][tbl01]][tbl01]

> These results do not look like a “black swan” that refutes universal claims that the brain always embodies small-world network topology. Nor do they undermine the credibility of previous studies demonstrating small-worldness in sparser brain graphs. However, our view is that binary graph models are very unlikely to be an optimal strategy for network analysis of tract-tracing data, because they fail to take account of the extraordinary range of connectivity weights, distributed log normally over 6 orders of magnitude, that has been discovered in mammalian cortical networks (Ercsey-Ravasz and others 2013). The weakest connection between cortical areas is about a million times less weighted than the strongest connection: does it really make sense to set all these weights equivalently to 1 as edges in a binary graph? To ask the question is to answer it.


### Small-Worldness of Weighted Tract-Tracing Networks

> A weighted small-world analysis is easily done for these data (Fig. 6B and D). The weighted clustering and weighted path length metrics (Eqs. 8 and 9) are estimated directly from the weight matrices, and the ratio of weighted clustering to weighted path length is the scalar summary of weighted small-worldness \(σ_{\text{weighted}}>1\). In Figure 6, we directly compare binary and weighted graph theoretical results for the mouse (Oh and others 2014; Rubinov and others 2015) and macaque (Markov and others 2013) connectomes. Compared with the results of binary graph analysis, both mouse and macaque networks have increased clustering for the weighted graph analysis, and \(σ\) is increased for the macaque (see Table 1).

> The weighted graph of the mouse connectome is similarly small-world compared to the weighted macaque graph, as measured by \(σ\), but is significantly more small-world as measured by the small-world propensity \(ϕ\). However, classical estimates of small-worldness may depend in a non-trivial way on the density of the graph. This relationship becomes obvious if we estimate the topology of both weighted graphs as a function of connection density (Fig. 7). The classical small-world scalar \(σ\) is greatest when it is estimated for a sparse graph comprising less than 20% to 30% of the most strongly connected edges, and decreases progressively as the graph becomes denser. This might suggest that the macaque connectome seems less small-world than the mouse simply because it is denser. However, the small world propensity \(ϕ\) has the useful property that it is independent of network density and it is significantly greater, indicating more small-worldness, for the mouse than the macaque. This could be related to differences between the datasets in number of cortical areas and completeness of cortical coverage: the macaque dataset comprises fewer nodes of mostly visual cortex than the larger number of nodes across the whole mouse cortex.

[![figure.7][fig07]][fig07]
> Figure 7. Dependence of small-world characteristics on network density. (A) Macaque and (B) mouse connectivity matrices in their natural state (left), as well as after thresholding to retain the 5% strongest (middle) or 25% strongest (right) connections. Weighted small-world metrics including the normalized clustering coefficient (Γ), normalized path length (Λ), small-world index (σ), and small-world propensity (φ) as a function of network density for the (C) macaque and (D) mouse connectivity matrices.


### Weighted Small-Worldness and the Role of Edge Weights

> Why does a weighted graph analysis provide stronger evidence for non-random clustering than a binary graph analysis applied to the same tract-tracing data? The most strongly weighted connections generally span the shortest physical distances between cortical areas (Ercsey-Ravasz and others 2013; Klimm and others 2014; Rubinov and others 2015). This is not surprising based on what we know about the importance of cost constraints on brain organization (Bassett and others 2009; Bassett and others 2010; Bullmore and Sporns 2012; Fornito and others 2011). Strong connectivity weights indicate a large number of axonal projections, a big bandwidth bundle, perhaps macroscopically visible as a white matter tract. Building and resourcing a high-bandwidth axonal signaling bundle is a significant biological cost that will increase as a function of connection distance: it is parsimonious to wire high bandwidth over short distances. Short distance connections are not only strongly weighted but also topologically clustered. So the strongest weights in both cortical networks define a topologically segregated and anatomically localized organization. A map of the sub-network formed by the strongest weights shows spatial and topological clusters of regions (Fig. 8). In the mouse, the strongly weighted clusters each comprise functionally specialized areas of cortex (visual, motor, etc.) that are known to be densely interconnected and anatomically localized (Rubinov and others 2015; Ypma and Bullmore 2016). Thus it is not surprising that weighting the topological analysis of mammalian cortical networks will provide stronger evidence for non-random clustering than unweighted analysis of binary graphs.

[![figure.8][fig08]][fig08]
> Figure 8. The existence of weak links and their topology in the mouse connectome. Here, we show the properties of the 5% weakest and 5% strongest edges of the mouse cortical network. (A, B) Axial view of the mouse cortical network, red dots represent brain regions, blue lines represent the connections between them. Drawn are the (A) 5% weakest or (B) 5% strongest edges. Dot size corresponds to degree, the total number of incoming and outgoing edges connected to a node. In (B), the three nodes with highest degree have been labeled as follows: VISp, primary visual area; MOp, primary motor area; SSs, supplemental somatosensory area. The strong connections are spatially organized, mainly connecting spatially adjacent or contralaterally homologous regions. The weak connections span longer distances and are topologically more random than the strongest connections. (C) The distance distributions for (blue) the 5% weakest edges, (red) the 5% strongest edges, and (black) a random graph of the same size and connection density. (D) The degree distributions for the weakest and strongest connections of the mouse connectome, and a comparable random graph, color-coded as in panel (C). Reproduced with permission from Ypma and Bullmore (2016).

> The most weakly weighted connections are an area of active, ongoing research (discussed in more detail below) and it is inevitable that there is still much to learn about a feature of network organization—replicable but very weak connections between large cortical areas—that had not been measurable until recent advances in tract-tracing methodology. However, it is clear that weaker connections tend to subtend longer distances, and can be either more topologically random (Ypma and Bullmore 2016) than or similarly topologically organized to strong connections (Bassett and others 2012a).

> We conclude that graph theoretical analysis of tract-tracing connectomes should respect the quality of the data and use weighted topological metrics to reflect the wide ranging variation in anatomical connectivity, from single fibers to major tracts, that is now measurable in the mammalian brain (Wang and Kennedy 2016). Weighted graph analysis demonstrates clearly that both the macaque and mouse connectomes are small-world networks, as are the human, cat, and nematode brains (Muldoon and others 2016a). Binary graph analysis has usefully measured high connection density, due to the existence of many new anatomical connections, but binarization of these data is not the best way to understand their complex topology and its economical embedding in anatomical space (Bassett and others 2011a; Bassett and others 2012a; Klimm and others 2014; Rubinov and others 2015; Rubinov and Sporns 2011). Future studies will likely also pay more attention to the fact that most tract-tracing markers are axonally transported only in one direction: anterograde or retrograde. This means that the weight matrix could be modelled more completely as a weighted and directed graph, representing a further evolution in the use of graph theoretical methods to capture a richer and biologically more meaningful model of brain network organization than can be provided by binary graphs of unweighted and undirected edges.


## 5. The Utility of Weak Connections

> At this juncture, one might naturally ask, “From a neuroscientific perspective, do we need techniques that account for edge weights? Do these weights indeed capture information of relevance for cognition and behavior?” Neuroanatomical data suggest that the weights of structural connections may be driven by developmental growth rules (Ercsey-Ravasz and others 2013; Kaiser and Hilgetag 2006; Klimm and others 2014; Lohse and others 2014; Markov and others 2013), energetic and metabolic constraints (Bassett and others 2010), and physical limitations on the volume of neural systems, particularly brains encapsulated by bone (Sherbondy and others 2009). Yet the role of these edge weights in neural computations (Schneidman and others 2006) and higher order cognition has been less well studied.

> Recent studies have begun to elucidate the role of edge weights—and particularly of weak connections—in human cognition. In resting-state fMRI data, weak functional connections from lateral prefrontal cortex to regions within and outside the frontoparietal network have been shown to display individual differences in strength that predict individual differences in fluid intelligence (Cole and others 2012). The same general relationship was observed in a separate study in which individual differences in moderately weak, long-distance functional connections at rest were strongly correlated with full scale, verbal, and performance IQ (Santarnecchi and others 2014). Neither of these correlations were observed when considering strong connections. Indeed, the utility of weak edges appears to extend to psychiatric illness, where the highly organized topology of weak functional connections—but not strong functional connections—in resting-state fMRI were able to classify people with schizophrenia from healthy controls with high accuracy and specificity (Bassett and others 2012a). Interestingly, individual differences in these weak connections were significantly correlated with individual differences in cognitive scores and symptomatology. Together these results demonstrate that, indeed, methods that are sensitive to the strength (or weakness) of individual connections are imperative for progress to be made in understanding individual differences in cognitive abilities, and their alteration in psychiatric disease.

> Importantly, the utility of weak connections is not only evident at the large scale in human brains but also at the neuronal scale as measured in non-human species. In an influential article published in 2006 with Bialek and colleagues, Schneidman demonstrated that weak pairwise correlations implied strongly correlated network states in a neural population, suggesting the presence of strong collective behavior (Schneidman and others 2006). This result was initially counterintuitive as one might expect that weak correlations would be associated with the lack of collective behavior. However, the original observation has withstood the test of time, and has been validated in several additional studies including work at the level of tract tracing in macaque monkeys (Goulas and others 2015). Intuitively, the juxtaposition of weak correlations and cohesive, collective behavior is thought to be driven by the underlying sparsity of neuronal interactions (Ganmor and others 2011b), which contain a few non-trivial higher-order interaction terms (Ganmor and others 2011a). Indeed, these higher-order interactions are the topic of some interest both from a computational neuroscience perspective (Giusti and others 2016; Sizemore and others 2016), and from the perspective of neural coding (Giusti and others 2015).

> But perhaps the claim that weak connections are critically important for our understanding of neural systems should not be particularly surprising. Indeed, it is in fact an old story, first published at the inception of network science. In 1973, Granovetter wrote a seminal paper, titled “The strength of weak ties,” which highlighted the critical importance of weakly connected components in global system dynamics (Granovetter 1973). Such weak connections are ubiquitous in many systems, from physician interactions (Bridewell and Das 2011) to ecosystem webs (Ulanowicz and others 2014) and atmospheric pathways (Lee and Su 2014). Looking forward, critical open questions lie in how these weak connections drive global dynamics, and how one can intervene in a system to manipulate those processes (Betzel and others 2016b; Gu and others 2015; Muldoon and others 2016b).

> Acknowledging the role of weak connections, weighted small-world organization plays a critical role in system functions that are particularly relevant to neural systems: including coherence, computation, and control and robustness (Novkovic and others 2016). Perhaps the most commonly studied function afforded by small-world architecture is the ability to transmit information, a characteristic that is common in networks of coupled oscillators (Barahona and Pecora 2002; Hong and others 2002; Nishikawa and others 2003) (although see Atay and others 2006, for a few notable exceptions). This capability supports enhanced computational power (Lago-Fernández and others 2000), via swift flow and transport (Hwang and others 2010). In dynamic networks, oscillators coupled on small-world networks are much more sensitive to link changes than their random network counterparts (Kohar and others 2014), the time taken to reach synchronization is lowered, and the synchronized state is less stable over time, potentially enabling greater diversity of function. When such a system has both small-world topology and geometry, it directly impacts the network’s ability to speed or slow spreading (Karsai and others 2011), a potentially useful characteristic for resilience to dementia which is thought to be caused by the spread of prions (Raj and others 2012; Raj and others 2015).

> The value of small-world architecture is not limited to its support of synchronization and information flow. Instead, it also supports a wide range of computations in neural circuits. From early neural network studies, it is clear that the exact topology of connectivity patterns between network elements directly supports trade-offs in the network’s ability to learn new information versus retain old information in memory (Hermundstad and others 2011). When these patterns are organized in a small-world manner, evidence suggests that local computations can be integrated across distributed cell assemblies to support functions as diverse as somatosensation (Zippo and others 2013) and olfaction (Imam and others 2012). The mechanism by which small-worlds support these computations may stem from the fact that their topological structure tends to contain both large cavities and high-dimensional cliques (Sizemore and others 2016), which when embedded in a physical space can strongly constrain the geometric properties of the computation (Giusti and others 2015).

> While small-world structure can offer non-trivial advantages in terms of both communication and computation, it also directly informs the sorts of interventions that one could use to guide network dynamics and by extension system function. Indeed, computational studies have demonstrated that small-world network architecture requires specific control strategies if one wishes to stem the propagation of seizure activity (Ching and others 2012), control the spread of viruses (Kleczkowski and others 2012), or enhance recovery following injury (Hübler and Buchman 2008). To gain an intuition for how topology impacts control, we can consider the broad-scale degree distribution also characteristic of brain networks. Based on the Laplacian spectrum, one can observe that weakly connected nodes have the greatest potential to push the system into distant states, far away on an energy landscape (Pasqualetti and others 2014); conversely, strongly connected hubs have the greatest potential to push the system into many local states, nearby on the energy landscape (Gu and others 2015). Thus, control energy (such as that provided by brain stimulation) may be targeted to different locations in a small-world brain network to affect a specific change in brain dynamics (Muldoon and others 2016b).


## 6. Conclusions

> Small-worldness remains an important and viable concept in network neuroscience. Nearly 20 years on from the first analysis of the complex topology of a binary graph representing the nervous system of C. elegans, it has been established that small-worldness is a nearly universal and functionally valuable property of nervous systems economically embedded in anatomical space. Recent advances in tract-tracing connectomics do not refute small-worldness; rather they considerably enrich and deepen our understanding of what it means in the brain. The extraordinary precision of contemporary tract tracing, and the important discovery that mammalian cortical networks are denser than expected, mandates the adoption of more sophisticated techniques for weighted graph theoretical modeling of interareal connectomes. On this basis, we expect the next 10 years to yield further insights into the functional value of weak as well as strong connections in brain networks with weighted small-worldness.







## 

[ref][ref01]


<!-- <style type="text/css">
	img{width: 50%; float: right;}
</style> -->

<!-- eq -->
<!-- 01 -->
[j]: https://latex.codecogs.com/gif.latex?\inline&space;j
[k]: https://latex.codecogs.com/gif.latex?\inline&space;k
[i]: https://latex.codecogs.com/gif.latex?\inline&space;i
[N]: https://latex.codecogs.com/gif.latex?\inline&space;N
[k\neq&space;j]: https://latex.codecogs.com/gif.latex?\inline&space;k\neq&space;j
[\frac{3}{3}=1]: https://latex.codecogs.com/gif.latex?\inline&space;\frac{3}{3}=1
[\frac{2}{3}=0.66]: https://latex.codecogs.com/gif.latex?\inline&space;\frac{2}{3}=0.66
[\frac{1}{3}=0.33]: https://latex.codecogs.com/gif.latex?\inline&space;\frac{1}{3}=0.33
[p=0]: https://latex.codecogs.com/gif.latex?\inline&space;p=0
[p=1]: https://latex.codecogs.com/gif.latex?\inline&space;p=1
[\sigma>1]: https://latex.codecogs.com/gif.latex?\sigma>1
[N=302]: https://latex.codecogs.com/gif.latex?\inline&space;N=302
[\frac{N^2-N}{2}=45451]: https://latex.codecogs.com/gif.latex?\inline&space;\frac{N^2-N}{2}=45451
[\Gamma\sim5.6]: https://latex.codecogs.com/gif.latex?\inline&space;\Gamma\sim5.6
[\Lambda\sim1.18]: https://latex.codecogs.com/gif.latex?\inline&space;\Lambda\sim1.18

<!-- 02 -->
<!-- Economical Small-World Networks -->
[\sigma]: https://latex.codecogs.com/gif.latex?\sigma
[P_{i,j}]: https://latex.codecogs.com/gif.latex?P_{i,j}
[d_{i,j}]: https://latex.codecogs.com/gif.latex?d_{i,j}
[k_{i,j}]: https://latex.codecogs.com/gif.latex?k_{i,j}
[P_{i,j}\sim&space;f(d_{i,j})f(k_{i,j})]: https://latex.codecogs.com/gif.latex?P_{i,j}\sim&space;f(d_{i,j})f(k_{i,j})

<!-- Small-Worldness Is Not the Whole Story -->
[\Lambda]: https://latex.codecogs.com/gif.latex?\Lambda
[\Gamma]: https://latex.codecogs.com/gif.latex?\Gamma
[\sigma=\frac{\Gamma}{\Lambda}]: https://latex.codecogs.com/gif.latex?\sigma=\frac{\Gamma}{\Lambda}


<!-- 03 -->
[L]: https://latex.codecogs.com/gif.latex?L
[\frac{L_p}{L_o}]: https://latex.codecogs.com/gif.latex?\frac{L_p}{L_o}
[\frac{C_p}{C_o}]: https://latex.codecogs.com/gif.latex?\frac{C_p}{C_o}
[L_o]: https://latex.codecogs.com/gif.latex?L_o
[C_o]: https://latex.codecogs.com/gif.latex?C_o
[L_p]: https://latex.codecogs.com/gif.latex?L_p
[C_p]: https://latex.codecogs.com/gif.latex?C_p
[P]: https://latex.codecogs.com/gif.latex?P
[C]: https://latex.codecogs.com/gif.latex?C

<!-- Binary Graphs -->
[G=(V,E)]: https://latex.codecogs.com/gif.latex?G=(V,E)
[V]: https://latex.codecogs.com/gif.latex?V
[E]: https://latex.codecogs.com/gif.latex?E
[W]: https://latex.codecogs.com/gif.latex?W
[ij]: https://latex.codecogs.com/gif.latex?ij
[w_{i,j}]: https://latex.codecogs.com/gif.latex?w_{i,j}
[\tau]: https://latex.codecogs.com/gif.latex?\tau
[w_{i,j}≥\tau]: https://latex.codecogs.com/gif.latex?w_{i,j}≥\tau
[w_{i,j}<\tau]: https://latex.codecogs.com/gif.latex?w_{i,j}<\tau
[D]: https://latex.codecogs.com/gif.latex?D
[D=\frac{E}{\frac{N^2-N}{2}}]: https://latex.codecogs.com/gif.latex?D=\frac{E}{\frac{N^2-N}{2}}
[L=\frac{1}{N}\sum&space;l_{i,j}]: https://latex.codecogs.com/gif.latex?L=\frac{1}{N}\sum&space;l_{i,j}
[l_{i,j}]: https://latex.codecogs.com/gif.latex?l_{i,j}
[C=\frac{1}{N}\sum&space;c_{i,j}]: https://latex.codecogs.com/gif.latex?C=\frac{1}{N}\sum&space;c_{i,j}
[c_{i,j}]: https://latex.codecogs.com/gif.latex?c_{i,j}
[C_{\text{brain}}]: https://latex.codecogs.com/gif.latex?C_{\text{brain}}
[C_{\text{random}}]: https://latex.codecogs.com/gif.latex?C_{\text{random}}
[\Gamma=\frac{C_{\text{brain}}}{C_{\text{random}}}]: https://latex.codecogs.com/gif.latex?\Gamma=\frac{C_{\text{brain}}}{C_{\text{random}}}
[\Lambda=\frac{L_{\text{brain}}}{L_{\text{random}}}]: https://latex.codecogs.com/gif.latex?\Lambda=\frac{L_{\text{brain}}}{L_{\text{random}}}
[\sigma=\frac{\Gamma}{\Lambda}]: https://latex.codecogs.com/gif.latex?\sigma=\frac{\Gamma}{\Lambda}
[\Gamma>1]: https://latex.codecogs.com/gif.latex?\Gamma>1
[\Lambda\sim1]: https://latex.codecogs.com/gif.latex?\Lambda\sim1
[C_{\text{weighted}}=\frac{1}{k_i(k_i-1)}\sum_{j,k}(\hat{w}_{ij}\hat{w}_{jk}\hat{w}_{ik})^{\frac{1}{3}}]: https://latex.codecogs.com/gif.latex?C_{\text{weighted}}=\frac{1}{k_i(k_i-1)}\sum_{j,k}(\hat{w}_{ij}\hat{w}_{jk}\hat{w}_{ik})^{\frac{1}{3}}
[k_i]: https://latex.codecogs.com/gif.latex?k_i
[L_{\text{weighted}}=\frac{1}{N(N-1)}\sum_{i\neq&space;j}\delta_{ij}]: https://latex.codecogs.com/gif.latex?L_{\text{weighted}}=\frac{1}{N(N-1)}\sum_{i\neq&space;j}\delta_{ij}
[\delta_{ij}=\frac{1}{w_{ij}}]: https://latex.codecogs.com/gif.latex?\delta_{ij}=\frac{1}{w_{ij}}
[\sigma_{\text{weighted}}=\frac{\Gamma_{\text{weighted}}}{\Lambda_{\text{weighted}}}]: https://latex.codecogs.com/gif.latex?\sigma_{\text{weighted}}=\frac{\Gamma_{\text{weighted}}}{\Lambda_{\text{weighted}}}
[\Gamma_{\text{weighted}}>1]: https://latex.codecogs.com/gif.latex?\Gamma_{\text{weighted}}>1
[\Lambda_{\text{weighted}}\sim1]: https://latex.codecogs.com/gif.latex?\Lambda_{\text{weighted}}\sim1
[\sigma_{\text{weighted}}>1]: https://latex.codecogs.com/gif.latex?\sigma_{\text{weighted}}>1

<!-- The Small-World Propensity -->
[\gamma>>1]: https://latex.codecogs.com/gif.latex?\gamma>>1
[\lambda>1]: https://latex.codecogs.com/gif.latex?\lambda>1
[\phi]: https://latex.codecogs.com/gif.latex?\phi
[L_{\text{brain}}]: https://latex.codecogs.com/gif.latex?L_{\text{brain}}
[C_{\text{lattice}}]: https://latex.codecogs.com/gif.latex?C_{\text{lattice}}
[L_{\text{lattice}}]: https://latex.codecogs.com/gif.latex?L_{\text{lattice}}
[L_{\text{random}}: https://latex.codecogs.com/gif.latex?L_{\text{random}}

[\phi=1-\sqrt{\frac{\Delta^2_C+\Delta^2_L}{2}}]: https://latex.codecogs.com/gif.latex?\phi=1-\sqrt{\frac{\Delta^2_C+\Delta^2_L}{2}}
[\Delta&space;C=\frac{C_{\text{lattice}}-C_{\text{brain}}}{C_{\text{lattice}}-C_{\text{random}}}]: https://latex.codecogs.com/gif.latex?\Delta&space;C=\frac{C_{\text{lattice}}-C_{\text{brain}}}{C_{\text{lattice}}-C_{\text{random}}}
[\Delta&space;L=\frac{L_{\text{brain}}-L_{\text{random}}}{L_{\text{lattice}}-L_{\text{random}}}]: https://latex.codecogs.com/gif.latex?\Delta&space;L=\frac{L_{\text{brain}}-L_{\text{random}}}{L_{\text{lattice}}-L_{\text{random}}}

[\Delta_{C/L}]: https://latex.codecogs.com/gif.latex?\Delta_{C/L}



[c_i:=\frac{L_i}{\frac{k_i(k_i-1)}{2}}]: https://latex.codecogs.com/gif.latex?c_i:=\frac{L_i}{\frac{k_i(k_i-1)}{2}}



<!-- -------------------------------------------- -->
[orig]: https://journals.sagepub.com/doi/10.1177/1073858416667720 "Bassett, D.S. and Bullmore, E.T., 2017. Small-world brain networks revisited. The Neuroscientist, 23(5), pp.499-516."
[mend]: https://www.mendeley.com/viewer/?fileId=20ffa31b-b0b8-9359-1c79-19b5e2dfe5db&documentId=98b4e3af-4e66-3b8c-9edf-55882df8982c
[figs]: .
[fig01]: https://journals.sagepub.com/na101/home/literatum/publisher/sage/journals/content/nroa/2017/nroa_23_5/1073858416667720/20170913/images/medium/10.1177_1073858416667720-fig1.gif ""
[fig02]: https://journals.sagepub.com/na101/home/literatum/publisher/sage/journals/content/nroa/2017/nroa_23_5/1073858416667720/20170913/images/medium/10.1177_1073858416667720-fig2.gif ""
[fig03]: https://journals.sagepub.com/na101/home/literatum/publisher/sage/journals/content/nroa/2017/nroa_23_5/1073858416667720/20170913/images/medium/10.1177_1073858416667720-fig3.gif ""
[fig04]: https://journals.sagepub.com/na101/home/literatum/publisher/sage/journals/content/nroa/2017/nroa_23_5/1073858416667720/20170913/images/medium/10.1177_1073858416667720-fig4.gif ""
[fig05]: https://journals.sagepub.com/na101/home/literatum/publisher/sage/journals/content/nroa/2017/nroa_23_5/1073858416667720/20170913/images/medium/10.1177_1073858416667720-fig5.gif ""
[fig06]: https://journals.sagepub.com/na101/home/literatum/publisher/sage/journals/content/nroa/2017/nroa_23_5/1073858416667720/20170913/images/medium/10.1177_1073858416667720-fig6.gif ""
[tbl01]: https://journals.sagepub.com/na101/home/literatum/publisher/sage/journals/content/nroa/2017/nroa_23_5/1073858416667720/20170913/images/medium/10.1177_1073858416667720-table1.gif ""
[fig07]: https://journals.sagepub.com/na101/home/literatum/publisher/sage/journals/content/nroa/2017/nroa_23_5/1073858416667720/20170913/images/medium/10.1177_1073858416667720-fig7.gif ""
[fig08]: https://journals.sagepub.com/na101/home/literatum/publisher/sage/journals/content/nroa/2017/nroa_23_5/1073858416667720/20170913/images/medium/10.1177_1073858416667720-fig8.gif ""

[ref01]: .


[1967MilgramS]: http://files.diario-de-bordo-redes-conecti.webnode.com/200000013-211982212c/AN%20EXPERIMENTAL%20STUDY%20by%20Travers%20and%20Milgram.pdf "Milgram, S., 1967. The small world problem. Psychology today, 2(1), pp.60-67."
[1979BollobásB]: .
[1985BollobásB]: .
[1986WhiteJG]: https://pdfs.semanticscholar.org/62d3/6f23580ae0c822ebc7de69ae603d85441bfc.pdf?_ga=2.198902187.568766748.1552464667-1255646428.1552464667 "White, J.G., Southgate, E., Thomson, J.N. and Brenner, S., 1986. The structure of the nervous system of the nematode Caenorhabditis elegans. Philos Trans R Soc Lond B Biol Sci, 314(1165), pp.1-340."
[1998StrogatzSH_WattsDJ]: http://leonidzhukov.net/hse/2014/socialnetworks/papers/watts-collective_dynamics-nature_1998.pdf "Watts, D.J. and Strogatz, S.H., 1998. Collective dynamics of ‘small-world’networks. nature, 393(6684), p.440."
[2004KötterR_SpornsO]: https://journals.plos.org/plosbiology/article?id=10.1371/journal.pbio.0020369 "Sporns, O. and Kötter, R., 2004. Motifs in brain networks. PLoS biology, 2(11), p.e369."
[2006BullmoreE_AchardS]: http://www.jneurosci.org/content/jneuro/26/1/63.full.pdf "Achard, S., Salvador, R., Whitcher, B., Suckling, J. and Bullmore, E.D., 2006. A resilient, low-frequency, small-world human brain functional network with highly connected association cortical hubs. Journal of Neuroscience, 26(1), pp.63-72."
[2006PrescottTJ_HumphriesMD]: https://www.ncbi.nlm.nih.gov/pmc/articles/PMC1560205/ "Humphries, M.D., Gurney, K. and Prescott, T.J., 2005. The brainstem reticular formation is a small-world, not scale-free, network. Proceedings of the Royal Society B: Biological Sciences, 273(1585), pp.503-511."
[2009CaoL_LiX]: https://journals.aps.org/pre/abstract/10.1103/PhysRevE.80.066101 "Li, X. and Cao, L., 2009. Largest Laplacian eigenvalue predicts the emergence of costly punishment in the evolutionary ultimatum game on networks. Physical Review E, 80(6), p.066101."
[2010BullmoreE_LynallME]: http://www.jneurosci.org/content/jneuro/30/28/9477.full.pdf "Lynall, M.E., Bassett, D.S., Kerwin, R., McKenna, P.J., Kitzbichler, M., Muller, U. and Bullmore, E., 2010. Functional connectivity and brain networks in schizophrenia. Journal of Neuroscience, 30(28), pp.9477-9487."
[2010DaffertshoferA_vanWijkBC]: .
[2011HaraN_KonishiK]: https://journals.aps.org/pre/abstract/10.1103/PhysRevE.83.036204 "Konishi, K. and Hara, N., 2011. Topology-free stability of a steady state in network systems with dynamic connections. Physical Review E, 83(3), p.036204."
[2011LaurientiPJ_TelesfordQK]: https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3604768/ "Telesford, Q.K., Joyce, K.E., Hayasaka, S., Burdette, J.H. and Laurienti, P.J., 2011. The ubiquity of small-world networks. Brain connectivity, 1(5), pp.367-375."
[2011SpornsO]: https://mitpress.mit.edu/books/networks-brain "Sporns, O., 2010. Networks of the Brain. MIT press."
[2011SpornsO_RubinovM]: .
[2012AstolfiL_ToppiJ]: https://www.hindawi.com/journals/cmmm/2012/130985/abs/ "Toppi, J., de Vico Fallani, F., Vecchiato, G., Maglione, A.G., Cincotti, F., Mattia, D., Salinari, S., Babiloni, F. and Astolfi, L., 2012. How the statistical validation of functional connectivity patterns can prevent erroneous definition of small-world properties of a brain connectivity network. Computational and mathematical methods in medicine, 2012."
[2013KennedyH_MarkovNT]: https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3905047/ "Markov, N.T., Ercsey-Ravasz, M., Van Essen, D.C., Knoblauch, K., Toroczkai, Z. and Kennedy, H., 2013. Cortical high-density counterstream architectures. Science, 342(6158), p.1238406."
[2013SiebenhuhnerF_BassettDS]: https://onlinelibrary.wiley.com/doi/abs/10.1002/9783527671632.ch07 "Bassett, D.S. and Siebenhühner, F., 2013. Multiscale network organization in the human brain. Multiscale Analysis and Nonlinear Dynamics, pp.179-204."
[2014VanDenHeuvelMP_SendenM]: https://repositori.upf.edu/bitstream/handle/10230/23126/Senden_Neuroimage.pdf?sequence=1&isAllowed=y "Senden, M., Deco, G., de Reus, M.A., Goebel, R. and van den Heuvel, M.P., 2014. Rich club organization supports a diverse set of functional network configurations. Neuroimage, 96, pp.174-182."
[2015BassettDS_MattarMG]: https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1004533 "Mattar, M.G., Cole, M.W., Thompson-Schill, S.L. and Bassett, D.S., 2015. A functional cartography of cognitive systems. PLoS computational biology, 11(12), p.e1004533."
[2015KrioulovD_GulyásA]: https://www.nature.com/articles/ncomms8651?origin=ppub "Gulyás, A., Bíró, J.J., Kőrösi, A., Rétvári, G. and Krioukov, D., 2015. Navigable networks as Nash equilibria of navigation games. Nature communications, 6, p.7651."
[2016BassettDS_MuldoonSF]: https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1005076 "Muldoon, S.F., Pasqualetti, F., Gu, S., Cieslak, M., Grafton, S.T., Vettel, J.M. and Bassett, D.S., 2016. Stimulation-based control of dynamic brain networks. PLoS computational biology, 12(9), p.e1005076."
[2016BetzelRF_SpornsO]: https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4782188/ "Sporns, O. and Betzel, R.F., 2016. Modular brain networks. Annual review of psychology, 67, pp.613-640."
[2016FornitoA]: https://books.google.co.jp/books?hl=en&lr=&id=Hc-cBAAAQBAJ&oi=fnd&pg=PP1&dq=Fornito+2016&ots=AMBCDkYY6b&sig=6alKVgYUMXmOd7cRxkTn-8KCLQ8#v=onepage&q&f=false "Fornito, A., Zalesky, A. and Bullmore, E., 2016. Fundamentals of brain network analysis. Academic Press."
[2016SpornsO_BetzelRF]: https://www.sciencedirect.com/science/article/pii/S1053811915008563 "Betzel, R.F., Avena-Koenigsberger, A., Goñi, J., He, Y., De Reus, M.A., Griffa, A., Vértes, P.E., Mišic, B., Thiran, J.P., Hagmann, P. and Van Den Heuvel, M., 2016. Generative models of the human connectome. Neuroimage, 124, pp.1054-1064."