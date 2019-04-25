<!--
Filename: 	190410_DeAngelisD_DiazS_2019.md
Project: 	/Users/shume/Documents/Cahier
Author: 	shumez <https://github.com/shumez>
Created: 	2019-04-10 20:57:8
Modified: 	2019-04-25 16:28:7
-----
Copyright (c) 2019 shumez
-->

# 19-04-10 Decision-Making in Agent-Based Modeling: A Current Review and Future Prospectus

[Original][orig] | [Mendeley][mend]

## ToC

* [00. Abstract](#00_abstract)
* [01. Introduction](#01_introduction)
* [02. Decisions in Classical Population Models](#02_decisions_in_classical_population_models)
* [03. Agent-based Modeling in Ecology](#03_agent-based_modeling_in_ecology)
* [04. Movement Decisions and Their Consequences](#04_movement_decisions_and_their_consequences)
	* [04.01. When to Move?](#0401_when_to_move)
	* [04.02. Where to Move?](#0402_where_to_move)
	* [04.03. Collective Movement Behavior](#0403_collective_movement_behavior)
* [05. Foraging Decisions and Population Interactions](#05_foraging_decisions_and_population_interactions)
* [06. Social Interactions in Populations](#06_social_interactions_in_populations)
* [07. Developments in the Modeling of Decisions in Population Models](#07_developments_in_the_modeling_of_decisions_in_population_models)
* [08. Prospectus](#08_prospectus)


## 00. Abstract

###### 00.P01
> All basic processes of ecological populations involve decisions; when and where to move, when and what to eat, and whether to fight or flee. Yet decisions and the underlying principles of decision-making have been difficult to integrate into the classical population-level models of ecology. Certainly, there is a long history of modeling individuals' searching behavior, diet selection, or conflict dynamics within social interactions. When all the individuals are given certain simple rules to govern their decision-making processes, the [resultant]("結果的に生じる") population–level models have yielded important generalizations and theory. But it is also recognized that such models do not represent the way real individuals decide on actions. Factors that influence a decision include **the organism's environment with its dynamic rewards and risks**, **the complex internal state of the organism**, and its **imperfect knowledge of the environment**. In the case of animals, it may also involve **complex social factors, and experience and learning**, which vary among individuals. The way that all factors are weighed and processed to lead to decisions is a major area of behavioral theory.

###### 00.P02

**Individual- / Agent-based model** (IBM / ABM)

> While classic population-level modeling is limited in its ability to integrate decision-making in its actual complexity, the development of **individual- or agent-based models (IBM/ABMs)** (we use ABM throughout to designate both “agent-based modeling” and an “agent-based model”) has opened the possibility of describing the way that decisions are made, and their effects, in minute detail. Over the years, these models have increased in size and complexity. Current ABMs can simulate thousands of individuals in realistic environments, and with highly detailed internal physiology, **perception** and ability to process the perceptions and make **decisions based on those and their internal states**. The implementation of decision-making in ABMs ranges from fairly simple to highly complex; the process of an individual deciding on an action can occur through the use of logical and simple (if-then) rules to more sophisticated **neural networks** and **genetic algorithms**. The purpose of this paper is to give an overview of the ways in which decisions are integrated into a variety of ABMs and to give a prospectus on the future of modeling of decisions in ABMs.

## 01. Introduction

###### 01.P01

classical models:

* randomly moving 
* w/ growth, reproducitin, mortality, interaction w/ env & other organisms
* e.g.,
	* **logistric population model**
	* **Lotka-Volterra predator-prey and competition model**
	* **reaction-diffusion partial differential equation (PDE) model**

decision-making by individuals is unimportant?

decision continually made

e.g., 

* single-celled animals (paramecia) ([2009_Wagner])
* social ants ([2006_Deneubourg_Detrain])

> The role of decision-making by individual organisms is largely ignored in the classical mathematical models of ecology, such as the **logistic population models**, **Lotka-Volterra predator-prey and competition models**, and their many variations. These models, as well as their extensions to space, as **reaction-diffusion partial differential equation (PDE) models**, treat organisms as randomly moving atoms, with added features of growth, reproduction, mortality, and interactions with their environment and other organisms. Because the classical models of ecological populations have been successful in revealing much about ecological systems, one might ask if decision-making by individuals is unimportant enough that it can be ignored at the population level, at least for simple organisms. But something like decisions are continually made, even by organisms perceived as simple. [Bray (2009)][2009_Bray] notes that single-celled animals, like swimming paramecia, “continually encounter different situations… and have to evaluate their options and assign priorities.” [Wagner (2009)][2009_Wagner] asks “Does the bacterium choose to change direction?” and concludes that this may be a matter of perspective. In more complex organisms, such as social ants, “each individual is a sensitive unit which can process a lot of information” ([Detrain and Deneubourg, 2006][2006_Deneubourg_Detrain]). These actions are programmed into the organism's DNA, and are unconscious, but clearly decisions are being made, and we will follow [Ydenberg (2010)][2010_Ydenberg] (cited in [Rypstra et al., 2015][2015_Rypstra]) in calling a decision **“wherever one or two (or more) options is/are selected**.”

###### 01.P02

> How important these decisions are at the population level and above is therefore an important question, even for organisms of low cognitive ability. Our perspective in this review is from that of population and community ecology and how modeling helps link individual behaviors to phenomena at the level of collections of individuals. We begin with a brief overview of how decisions have been incorporated in some classical analytic models of ecology. Then we introduce agent-based modeling (ABM) and describe how it has been used to simulate decision-making in individual movement, [foraging](. "(食べ物を)探し求める") behavior, population interactions, and social interactions within populations. This is not intended to be comprehensive, but to touch on a variety of ways ABM is used. Finally, we discuss more recent developments in modeling decisions within population models and present a prospectus for future directions.

## 02. Decisions in Classical Population Models

###### 02.P01

individual decision &rArr; population  
< individual fitness &lArr; ecological context


> The use of modeling to address **the question of the effect of individual decisions on population level dynamics** developed more slowly than modeling of the converse question of how ecological context influences the effects of decisions on individual fitness. The latter has been explored by behavioral ecologists using classical population models for several decades, focusing especially on decisions regarding foraging movement and its effects on the fitness of individuals. Additionally, some models have been able to incorporate decision-making when modeling collections of individuals, whole populations, and even multiple populations.

###### 02.P02

models 

* kinesis model  
	(decisions on when to speed up/slow down/turn in response to detected local cond)
* restricted are search
	* patch
	* DSVM (Dynamic State Variable Modeling)

> Movement of animals toward favorable conditions could be decomposed into simple decisions on directed movement, or taxis, in relation to light, temperature, or resource gradients. Because it may be difficult for organisms to detect gradients, but possible to assess conditions at a current location, many models focused on kinesis, which involves decisions on when to speed up, slow down, or turn in response to detected local conditions (e.g., [Gunn and Fraenkel, 1961][1961_Fraenkel_Gunn]; [Schöne, 1984][1984_Schöne]; [Bell, 1991][1991_Bell]; [Grünbaum, 1999][1999_Grünbaum]; [Gautestad, 2016][2016_Gautestad]). Other models used “restricted area search” in which organisms evaluate conditions within a limited area before making a movement choice (e.g., [Humston et al., 2004][2004_Humston]). Movement decisions can be combined with decisions on settling at a place or leaving it, for which a variety of modeling approaches are used ([Lima and Zollner, 1996][1996_Zollner_Lima]). At one extreme, animals may simply move in one direction until they find a spot to settle, or they may use spatial memory and learning to gain knowledge of the landscape such that they can choose the nearest detectable habitat patch ([Fahrig, 1988][1988_Fahrig]). Decisions on leaving a patch may increase as the level of resources is depleted. Mathematical theory has been applied to predict the optimal time to leave a patch, depending on its resource level relative to other patches and travel costs ([Charnov, 1976][1976_Charnov]), or to predict what succession of patches, with varying risks and rewards, to choose in order to maximize fitness over longer times ([Mangel and Clark, 1988][1988_Clark_Mangel]; [Houston and McNamara, 1999][1999_McNamara_Houston]; [Clark and Mangel, 2000][2000_Mangel_Clark]), an approach referred to as **Dynamic State Variable Modeling (DSVM)**.

###### 02.P03

* **advective-dffusion model** ([Skalski and Gilliam (2000)][2000_Gilliam_Skalski]) 
	* e.g., fish formation
* **purposeful kinesis**
	* population density gradients ([Flierl (1999)][1999_OlsonDonald_GrünbaumD_FlierlG])

> The step from modeling individuals to modeling collections of individuals could in some cases be done using mathematical models, in which all individuals follow the same basic rules that could be incorporated into PDEs. For example, [Skalski and Gilliam (2000)][2000_Gilliam_Skalski] used an **[advective](. "移流")-diffusion model** to simulate patterns of fish formation in which the only decisions involved swimming fast or slow and having an upstream directional bias rather than pure random movement. However, many observed movement patterns of collectives, such as of flocks of birds, schools of fish, swarms of insects, and patterns formed by herding mammals, are more complex. Modeling these patterns requires more than movement decisions based on abiotic conditions, but they can be approximated when the PDEs also incorporate terms that represent **decisions to move up or down population density gradients**. Such individual movement behavior differs from random walk and can result in various patterns of collections of organisms ([Patterson et al., 2008][2008_MatthiopoulosJ_ThomasL_PattersonTA]). “**Purposeful kinesis**” can alter diffusive patterns ([Gorban and Çabukoglu, 2018][2018_Çabukoglu_Gorban]), leading to positive density-dependent diffusion, or “**super-diffusion**,” and other variations on diffusion through dependence on population density ([Topaz and Bertozzi, 2004][2004_Bertozzi_Topaz]; [Lutscher, 2008][2008_Lutscher]; [Almeida et al., 2015][2015_Almeida]; [Tilles and Petrovskii, 2016][2016_Petrovskii_Tilles]). For example, the phenomenon of clustering, in insect swarms and fish shoals, can occur when individuals accelerate in the direction of a positive density gradient ([Tyutyunov et al., 2004][2004_Tyutyunov]). [Flierl et al. (1999)][1999_OlsonDonald_GrünbaumD_FlierlG] provide a general review of mathematical modeling of collective behavior.

###### 02.P04

**IFD** (Ideal free distribution)

* e.g., **predator-induced defenses**
	* **Holling type 2 functional responses**

> The influence of individual decisions on the level of whole populations and multi-population systems can also be studied when decision-making is incorporated into models of classical ecology, if the decisions are limited to simple rules, such as optimization of fitness in foraging ([MacArthur and Pianka, 1966][1966_Pianka_MacArthur]; [Charnov, 1976][1976_Charnov]), or in diet selection ([Pulliam, 1974][1974_Pulliam]) and life history ([Roff, 1992][1992_Roff]). For example, if all individuals foraging on a spatial environment of habitat patches with different resource levels are assumed to move among them until no further movement would increase their fitness, the population would reach what is called an **Ideal Free Distribution (IFD)** ([Fretwell and Lucas, 1969][1969_Lucas_Fretwell]). The IFD concept applies to a wider range of decisions, such as the choice that organisms in a population have in allocating resources in different proportions to foraging, defense, reproduction, etc. A particular example is that of **predator-induced defenses**, which are known to exist in many ecological systems and may involve changes in both morphology and behavior. The defended individuals are still [edible](. "食用になる") but less so than undefended prey and, as a tradeoff, have lower resource intake rates than undefended prey. Recently it has been shown that the existence of inducible defenses in species at the bottom or middle of the food chain can affect the stability of the food chain, as well as the ability of the top predator to exert top-down control on the system ([Vos et al., 2004][2004_Vos]). In [DeAngelis et al. (2007)][2007_DeAngelis], a system containing a predator, a prey with an inducible defense, and a resource of the prey, was studied using a differential equation model, with **Holling type 2 functional responses** describing the trophic interactions. The prey could choose between [allocation](. "割り当て, 配分") to induced defense, with the tradeoff of lower resource uptake. The prey population evolved to switching between defense and non-defense, leading to a balance in which certain proportions of prey were in the undefended state and the rest in the defended state, the proportions depending on predator density. The prey in each state had equal fitness, so this was an IFD. This strategy of the prey influenced the populations of the whole food chain.

###### 02.P05

**game theory**

> Mathematical models have also represented simple decisions on allocation of time and energy to foraging vs. avoiding or defending against predators ([Abrams, 1982][1982_Abrams], [1993][1993_Abrams]; [Lima and Dill, 1990][1990_Dill_Lima]; [Abrams and Matsuda, 1993][1993_Matsuda_Abrams]; [Lima and Zollner, 1996][1996_Zollner_Lima]; [Werner and Peacor, 2003][2003_Peacor_Werner]). Other models, using differential equations, describe a forager in an environment of several prey, in which the forager could choose which prey to feed on, based on a maximization of long-term food intake (e.g., [Feng et al., 2009][2009_Feng]). Another approach of classical mathematical theory in ecology is **game theory**, which can be used to determine the optimal strategy of an individual when the expected pay-off of a decision (e.g., to “fight or flee” when in a confrontation) depends on the decisions made by other individuals ([Riechert and Hammerstein, 1983][1983_Hammerstein_Richert]). In all these cases models showed that optimal decisions taken by members of the populations can have large ecosystem consequences.

## 03. Agent-based Modeling in Ecology

###### 03.P01

<!-- simple decision model &larr;  -->

2 trends:

1. variability w/i populations in behaviors
	* e.g., behavioral tendencies, personality
2. ABM (Agent-based modeling)

> The fact that mathematical or analytic models based on a few simple decision rules can explain even complex patterns is remarkable, and such modeling is still a lively and important area of theory. But **behaviorists recognized that the capacity of these simple models to represent the real decisions of organisms, determined by a multitude of inputs, was limited, and that inclusion of decision-making was important** ([Dill, 1987][1987_Dill]). Two trends in ecology that are relevant to that problem have accelerated over the past two decades. One trend is the increasing recognition of marked variability within populations, not just in age, size, or stage, but also in behaviors of individuals within given classes. In fact, individuals across many [taxa](. "species, family. class") appear to have their own personalities, or temporally consistent “**behavioral tendencies**” ([Biro and Stamps, 2008][2008_Stamps_Biro]; [Beekman and Jordan, 2017][2017_Jordan_Beekman]). The prevalence of behavioral differences, or different personalities, that exists across animal taxa was reviewed in a [pivotal](. "中心の, 重要な") paper ([Bolnick et al., 2003][2003_Bolnick]). Personality differences such as “bold” vs. “conservative” behavior in fish (e.g., [Blake et al., 2018][2018_Blake]) exist and involve various aspects of behavior, such as responses to intra-and inter-specific competition ([Araújo et al., 2011][2011_Araújo]; [Dall et al., 2012][2012_Dall]), and tradeoffs between growth and mortality ([Biro and Stamps, 2008][2008_Stamps_Biro]) and early and late reproduction ([Wolf et al., 2011][2011_Wolf]). [Bolnick et al. (2011)][2011_VasseurDavid_AmarasekarePriyanga_BolnickDanielI] discuss several ways in which this individual-level specialization can affect community dynamics, which is an [impetus](. "刺激、推進力") to including individual differences in models. Variation in individuals, and therefore in their possible decision-making, casts further doubt on the capability of analytic models to adequately represent real populations. The second trend is the rapid spread of individual- or **agent-based modeling (ABM)**, which has become an established approach with numerous modeling platforms and is encompassed by a vast literature. The latter development may provide a solution to the [impasse](. "行き詰まり, 袋小路") of creating models of sophistication comparable to what is known about decision-making.

###### 03.P02

ABM

* simulate autonomous "agents" 
* state var representing internal states (behavioral states)
* unique history of interactions w/ env & other agents


> ABMs are ideally suited to accounting for individual differences in organisms. First applied to tree communities ([Botkin et al., 1972][1972_Botkin]), in the last few decades ABMs have become well established in all areas of ecology. ABMs simulate the interactions of autonomous “agents,” generally representing individual organisms or other real-world entities, with other agents and with the external environment ([DeAngelis and Mooij, 2005][2005_Mooij_DeAngelis]). In ABMs, every individual of a population can, in principle, be simulated to almost any level of detail. Each agent may have state variables representing internal states, including behavioral states, and each can have a unique history of interactions with its environment and other agents ([DeAngelis and Grimm, 2014][2014_GrimmV_DeAngelisDL]). Agent-based modeling attempts to capture the variation among individuals that is relevant to the questions being addressed. In particular, it can incorporate what is known about individual decision-making to explore the consequences in population and community models ([Parunak et al., 1998][1998_Parunak]; [Railsback, 2001][2001_Railsback]; [Vincenot, 2018][2018_Vincenot]).

###### 03.P03

* deterministic
* probabilistic

> An ABM can be used where decisions are complex and/or are in a setting of populations or communities. The simplest and most straightforward way to represent individual decision-making in an ABM is to utilize logical rules following the “if-then” structure. The behavior of an individual can be modeled when the “if” part contains a condition, and the proceeding “then” part presents the individual's response. The rules governing decision-making processes can be set up in various ways. Strictly logical, deterministic rules would assign only one possible behavior to an individual in a particular circumstance ([Grimm and Railsback, 2005][2005_Railsback_Grimm]). Alternatively, a rule may be **probabilistic**, with a different probability for each choice in an array of possible actions in response to some stimulus. Rules may also be a combination of probabilistic and deterministic. For many animals, however, decision-making processes may be more complex, and can be influenced by many variables including the internal state of the individual, that may vary among individuals. As will be discussed later, ABMs are increasingly being used in situations where organisms are assumed to have incomplete knowledge of the surrounding environment, and differences in perception and navigation capacities, but are able to employ cognitive skills to make choices that are good proximate decisions, [albeit](. "although") less than optimal. In this way, ABMs are able to [encapsulate](. "要約する") the basic underlying principles of the decision-making process in a more realistic way than classical models, and may more effectively represent the way individuals actually decide on actions and how the resulting behaviors shape population-level processes ([Figure 1](#figure_1)).

###### Figure 1

* individual complexity
* proximate decision-making, uncerteainty, emergence

![fig.1][fig_01]

> Figure 1. Schematic representation of the models and methodologies utilized to model decision-making in ecology. Along the horizontal axis, these models and methodologies are able to introduce greater **individual complexity** and represent more complex interactions. Along the vertical axis, the models' entities can be characterized by more **proximate decision-making**. There is more uncertainty introduced along this axis, but also a greater level of **emergence**, or higher-level behaviors resulting from lower-level interactions.

## 04. Movement Decisions and Their Consequences

###### 04.P01

compoponents:

* internal state
	* physiological
	* psychological 
* external env
	* spatially-explicit
* navigational capacity
* motion capacity

> ABMs have been used extensively to simulate the movement behavior of both terrestrial and marine organisms, due in large part to their flexibility in incorporating the various components that influence an individual's movement through space. These components include an individual's internal state, external environment, and navigational and motion capabilities ([Tang and Bennett, 2010][2010_Bennett_Tang]; [Figure 2](#figure_02)). ABMs can represent a variety of dynamic physiological and psychological state variables comprising an organism's internal state, including commonly used [bioenergetic](. "transformation of energy in organism, 生体エネルギー論") variables (Tang and Bennett, 2010). When simulating movement through space, the external environment is generally **spatially-explicit**, often represented as grid cells, such that **the location of agents and environmental attributes and the spatial relationship between them is explicitly defined** ([Duning, 1995][1995_Duning]; [Bauer and Klaassen, 2013][2013_Klaassen_Bauer]). 

###### Figure 2

[![Fig.2][fig_02]][fig_02]

> Figure 2. Schematic illustrating the major components influencing animal movement, all of which can be represented within an ABM ([Baguette et al., 2014][2014_Baguette]).

###### 04.P02

2 important decisions:

* when to move
* where to move

> By portraying an individual's dynamic environment and internal state in detail, ABMs can capture the two important decisions that an individual in motion must continually make: **when to move**, and **where to move**. The models can also be used to [derive](. "...から引き出す") the consequences of many organisms moving and interacting with each other at the same time, which gives rise to spatial patterns.

### 04.01. When to Move?

###### 04.01.P01

* internal state
* cond of the current area
* presence of competition & predation

temporal changes prompt agents moement  
e.g., trout, bear 

> ABMs for movement generally incorporate rules that dictate when an individual agent decides to move from its current location. For real-world organisms, the onset of movement at fine scales may depend on the individual's current internal state, including its physiological and psychological conditions, the condition of the current area that the individual is in, and the presence of competition and predation ([Semeniuk et al., 2011][2011_Semeniuk]; [Martin et al., 2013][2013_Martin]; [Doherty and Driscoll, 2017][2017_Driscoll_Doherty]). As such, ABMs simulating the fine-scale movement of individuals often keep track of **temporal changes in the individual agent's internal state and its local surroundings**. These changes generally prompt agent movement if they somehow increase (or at the very least, not decrease) the agent's fitness. For example, brown and rainbow [trout](. "マス") agents decide to move from their position if the previous day's calculated ratio of mortality risk to growth is greater than expected. Thus, at a given time step, fish agents might move to maximize the ratio of growth to risk of mortality ([Van Winkle et al., 1998][1998_VanWinkle]). Bear agents in an ABM simulating human-bear interactions decide to move to a new location if their current location has a low amount of food, or if they are threatened by human activity ([Marley et al., 2017][2017_Marley]).

###### 04.01.P02

changes of many individuals through time influence movement

e.g., green woodhoopoe

> An individual's decision on when to move may be influenced by the individual's life cycle and social factors. ABMs can track important biological changes of many individuals through time and be utilized to explore how these changes influence movement when placed within a social context. For example, [Neuert et al. (1995)][1995_Neuert] developed a model of the territorial group-living green [woodhoopoe](https://en.wikipedia.org/wiki/Wood_hoopoe "モリヤツガシラ") (*Phoeniculus purpureus*) to address the question of when a subdominant (and thus non-breeding) individual should decide to leave the group and [scout](. "reject") for a territory on which it could breed, vs. waiting around to become high enough in status to breed at its natal site. In the model, **the decision was based on its own age and rank, where the rank is correlated with age**. The simple decision trait of higher [propensity](. "性癖, 傾向") to go on scouting [forays](. "進出, 一時的関心") with increasing age provided the best agreement with empirical data.

###### 04.01.P03

* temporal changes in
	* recoucese availability
	* other factors


e.g., timing of pink-footed geese migration are influenced by factors:

1. minimal body stores
2. maximal stores
3. date
4. temperature
5. plant phenology
6. fixed duration of stay

> Large scale movement, such as migration, may be triggered by temporal changes in resource availability ([Van Moorter et al., 2013][2013_VanMoorter]) along with a number of other factors, and ABMs have been utilized to explore the potential decision-rules that may dictate the timing of such behavior for various species. For example, ([Duriez et al., 2009][2009_KlaassenMarcel_BauerSilke_DuriezOlivier]) assumed the following factors to be important for the timing of pink-footed geese migration; (1) having minimal body stores, (2) having maximal stores, (3) date, (4) temperature, (5) plant phenology, and (6) fixed duration of stay. The authors found that decision-rules related to food resources were important for dictating the onset of migration, but later in the season, decision-rules related to the geese agents' internal clocks and date are likely used.

###### 04.01.P04

**range expansion of population**

3 phases

1. **initial probability** of offspring dispersing from natal cell 
	* depending on population density
2. **transfer probability** 
	* dependind on landscape composition of the cell & neghboring animals
3. **settlement probability**
	* depending on habitat suitability, presence of potential mate, density of conspeceifics

> Movement is also involved in the **range expansion of a population**, and [Bocedi et al. (2014)][2014_Bocedi] modeled range expansion by considering three phases. Within the ABM, there is an initial probability of **offspring dispersing** from a natal [cell](. "巣"), which can depend on population density. Then there is “**transfer probability**,” the direction of which is weighted by the costs of moving to each adjacent cell, which depends on landscape composition of the cell and neighboring animals. In the final phase, four alternative strategies were compared to determine which best described **settlement probability**, and each of which was based on a combination of several factors, including habitat suitability, presence of a potential mate, and density of [conspecifics](. "member of the same species").



### 04.02. Where to Move?

###### 04.02.P01

navigation capacity:  
links internal state and ecternal var 


> Many organisms can process information about their environment and make movement decisions to satisfy internal desires. Changes in the internal state of an organism may result in changes in the organism's goals, movement decisions, and subsequent movement behavior ([Tang and Bennett, 2010][2010_Bennett_Tang]). When deciding where to move, mobile animals rely on their navigation capacity, which links the animals' internal states and external variables and manifests itself as either non-oriented, oriented, or memory-driven movement ([Nathan et al., 2008][2008_Nathan]; [Doherty and Driscoll, 2017][2017_DriscollDonA_DohertyTimS]). The ABM framework [lends](. "貸す, 適している") itself to representing dynamic environmental cues, particularly when the spatiotemporal relationships between the agent and the environment is explicitly represented, as in spatially explicit ABMs. The internal states of individuals can be represented as dynamic state variables and integrated with the cognitive capabilities of individuals, which allows model agents to assess various movement decisions within complex landscapes and ultimately decide on their next destination ([Tang and Bennett, 2010][2010_Bennett_Tang]). Additionally, some stochasticity in selecting an area to move to is incorporated within many ABMs by using a combination of probabilistic and logical rules, reflecting imperfect knowledge of the environment and perception capabilities.

###### 04.02.P02

e.g., 

* caribous
	* destination cell influenced by
		* daily energetic state
		* reproductive energy requirement
		* predation risk
* jaguars
	* energy reserves (internal state)
* hippopotamus

> Many ABMs simulating animal movement explicitly represent and track various components of an individual agent's internal state in detail, often resulting in movement characteristics that closely mimic those of real-world organisms. For example, [Semeniuk et al. (2012)][2012_Semeniuk] explored potential habitat-selection strategies employed by woodland [caribou](. "トナカイ") in response to industrial features in the landscape and represented the caribou's internal states by primarily tracking an individual's energy gain and loss. The caribou's decision on selecting a destination cell was influenced by its daily energetic state, reproductive energy requirement, and predation risk. The way that the internal state of the agent influenced movement varied for each alternative habitat-selection strategy. The authors found that the behavioral strategy concerned with balancing daily energy intake, conserving energy for reproduction, and minimizing predation risk agreed with real-world data better than the other strategies ([Semeniuk et al., 2012][2012_Semeniuk]). [Watkins et al. (2015)][2015_Watkins] kept track of energy reserves of jaguar agents within a model landscape representing central [Belize](https://en.wikipedia.org/wiki/Belize "ベリーズ"). The landscape cells were characterized by attributes including food availability, the presence of marks from other jaguars, and the presence of roads. When agents decide to move, their decision-making process concerning cell selection depends on the habitat attributes underlying a specific cell *and* the agent's internal state, namely, **energy reserves**. The individual jaguar's energy reserve levels modulate the preference of different attributes; consequently, agents with high energy reserve levels may decide to move to a cell that does not necessarily have high food availability; see also [Lewison and Carter (2004)][2004_Carter_Lewison] for an ABM simulating hippopotamus foraging behavior.

###### 04.02.P03

resistance 

**cost**


> When information on the dynamics of an individual's internal state is lacking, it may be appropriate to simulate movement by using simple decision rules based on empirical observations of the resistance that different habitat types may [confer](. "参照する") to the movement of real-world individuals. For example, [Aben et al. (2014)][2014_Aben] developed and explored the effectiveness of an ABM in simulating forest bird movement, in which a bird agent's selection of a cell (habitat area) to move to at any given time step was partially determined by the **land-cover class** that characterized a given cell. Land-cover classes conferring more resistance to movement were given higher **“cost” values**. Spatial cells characterized as having a low cost to birds that are moving through the cells had a higher probability of being selected than cells characterized as having a high cost. Similarly, simple decisions rules governing the selection of destination cells may be based on the quality of the surrounding environment, such that agents generally move toward preferred or favorable areas. In an ABM developed to estimate landscape connectivity for bighorn sheep, each cell in the landscape is represented by landscape attributes including its proximity to escape terrain and the presence of roads ([Allen et al., 2016][2016_Allen]). Bighorn sheep agents have a higher probability of moving to cells closer to escape terrain and away from roads as these cells represent more favorable habitats to real-world bighorn sheep. The characteristics of the surrounding environment also played a major role for agents deciding on a destination in ABMs simulating movement for tiger ([Kanagaraj et al., 2013][2013_Kanagaraj]), tortoise ([Anadón et al., 2012][2012_Anadón]), and capercaillie ([Graf et al., 2007][2007_Graf]).

### 04.03. Collective Movement Behavior

###### 04.03.P01

* single-agent
* multi-agent

key to understanding collective behavior:

* principles of the bahavioral algorithms followed by individual
* how info flows between animals 

> Many of the above models of animal movement are single-agent ABMs, as opposed to **multi-agent ABMs** used to simulate collections of interacting individuals. One of the [enigmas](. "謎") of natural history is the striking coordinated collective movements of various taxa (birds, insects, fish, mammals, etc.). Investigation of these phenomena is based on the recognition that the movement characteristics of individuals are often influenced by the spatial position and movement of conspecifics, which results in collective movement ([Krause et al., 2010][2010_Krause]). Individuals must make decisions on the initialization and direction of movement, and these decisions somehow incorporate the states of their neighbors. As [Sumpter (2006)][2006_SumpterDavidJT] notes, the key to understanding collective behavior lies in identifying **the principles of the behavioral algorithms followed by individual animals** and **how information flows between the animals**. The decision-making process of individuals involved in collective movement has been represented by a spectrum of simple to complex rules within ABMs.

###### 04.03.P02

* fish school ([Huth and Wissel (1992)][1992_Wissel_Huth])
	* rupulsion ()
	* attraction ()

[Couzin 2002][2002_Couzin]:

* repulsion (move away from nearby neighbors)
* alignment (adopt the same direction)
* attractin (avoid becoming isolated)

> Both [Sumpter (2006)][2006_SumpterDavidJT] and [Couzin and Krause (2003)][2003_Krause_Couzin] provide reviews of the use of ABM in describing collective behaviors of organisms based on relatively small sets of decision rules. In an early use of a spatially explicit ABM, [Huth and Wissel (1992)][1992_Wissel_Huth] showed that the complex movement of fish schools could be described by a few rules; the fish tend to keep a certain distance between themselves and a number of its close neighbors and move parallel to other fish when they are within a certain range. The fish agents decide to move away from neighbors if they are too close (repulsion) or align themselves with their neighbors if they are too far (attraction). Size sorting also occurs in fish schools, which may be represented by simple rules, where individuals tend to actively stay with individuals of similar size and avoid those of a different size ([Hemelrijk and Kunz, 2005][2005_Kunz_Hemelrijk]). [Couzin et al. (2002)][2002_Couzin] proposed a similarly simple model in which individual animals followed three rules of thumb; (1) move away from very nearby neighbors, (2) adopt the same direction as those that are close by, and (3) avoid becoming isolated; thus, the authors utilized the simple rules of repulsion, alignment, and attraction. In taking into account the location of an individual's neighbors at all times, the authors' model was able to reproduce collective behavior often seen in nature, including [swarm](. "昆虫などが群れる")ing and [torus](. "円環面") behavior.

###### 04.03.P03

[Gueron 1996][1996_Gueron]:

* stress zone
* attraction zone
* neutral zone
* rear zone

[Hoare 2004][2004_Hoare]:

* "zones of interactions" influence the size of groups 

> Dynamics of a small [herd](. "(牛などの)群れ") of mammal browsers were described by a more complex decision tree than those used by [Huth and Wissel (1992)][1992_Wissel_Huth], and [Couzin et al. (2002)][2002_Couzin]. [Gueron et al. (1996)][1996_Gueron] integrated a combination of “stress zones,” “attraction zones,” “neutral zones,” and “[rear](. "care for") zones” in the decision-making process of individuals moving within a herd. The various zones corresponded to specific distances extending from each individual, and each individual could invade the zones of other individuals. Probabilities and directions of movement depended on the type of zone an individual invaded. For example, if an individual sensed another individual within its “stress zone,” the individual slowed down to avoid collision. If neighbors were all on one side of the individual, the individual moved toward neighbors. Even though this sort of collective behavior is a much looser kind of group cohesion than fish schooling, the ABM showed that by simply integrating information about an individual's neighbors into the decision rules, many patterns of collective movement could emerge. [Hoare et al. (2004)][2004_Hoare] used a similar model to explain the group size distributions of fish, where dynamic “zones of interactions” strongly influence the size of groups in simulations.

## 05. Foraging Decisions and Population Interactions

###### 05.P01

* temporal / spatial patterns 

> The use of ABM in modeling foraging behavior changes the emphasis from predicting the fitness of the individual based on its decisions to **predicting temporal and spatial patterns formed by large collections of individuals foraging and competing for resources** (though sometimes interacting positively). 

###### 05.P02

observations of real population in real locations

> A common, though not universal, characteristic of ABMs is that they are based on observations of real populations in real locations. Thus, the assumptions built into the models constitute hypotheses that can be tested against observational data. A few models will be mentioned here: Barnacle geese (Branta leucopsis) in Helgeland, Norway, white-fronted geese (Anser albifrons) in Lake Miyajimanuma, Japan, oystercatchers (Haematopus ostralegus) in the Exe estuary, England, salmonids in Little Jones Creek, California, USA, and dusky dolphins (Lagenorrhyncus obscurus) and killer whales (Orcinus orca) near Kaikoura, New Zealand. 

###### 05.P03

geese

**Bioenergetics model**

> [Kanarek et al. (2008)][2008_Kanarek] modeled [barnacle geese](. "黒雁") that return to the same group of islands each year as a migration stop. The geese are assumed to vary in age, energy reserves, genetic disposition, and spatial memory of previously visited locations. A goose chooses a specific island based on a combination of factors; constraint due to rank in the dominance hierarchy, memories of previously visited sites and past reproductive success, inherited genetic influences toward site faithfulness, and knowledge of the available biomass density. Within the island the goose chooses to forage on a particular patch until its intake rate drops below a certain amount. Once a goose decides to leave a patch, it uses its knowledge to choose where to go next, assigning a score to a patch based on several factors. A **bioenergetics model** keeps track of the body mass of the goose, and the goose leaves the staging area either when a threshold of the amount of energy stored or when the end of the stopover period is reached. Each year that a goose returns to the same patch, its familiarity and ability to locate food increases as well as its hierarchical rank. 

###### 05.P04

**dominance hierarchy**

> A dominance hierarchy is also incorporated into the ABM of a migratory bird, the [oystercatcher](. "ミヤコドリ"), feeding on [mussels](. "ムール貝") in a tidal [estuary](. "河口, 入江") in England during the winter ([Stillman et al., 1997][1997_Stillman]). A population of individual oystercatchers was modeled on a two-dimensional patch, and the individuals were assigned to places in a dominance hierarchy. When two individuals come within a certain distance, and one is handling prey, the other might attack to attempt to steal the prey, prompting the other to fight back, with the dominant individual always winning. The alternative behavior is avoidance, an action taken with higher probability by less dominant individuals. Avoidance subtracts less time from foraging than fighting. The authors assumed that individuals could calculate the costs vs. benefits of a given action and decide accordingly. The results of the model show, in accord with observations, much less incidence of interference than equivalent analytic models, because, given the differences in rank that are incorporated in the ABM, dominants wasted less time avoiding subdominants, and subdominants avoided fighting. 

###### 05.P05

> In the case of white-fronted geese, an ABM explored possible positive interactions among the geese (Amano et al., 2006). The model tested the hypothesis that geese foraging in patches usually have no prior information on patch quality before making a choice but can benefit from choosing patches already occupied by conspecifics; i.e., the presence of conspecifics in the patch has the potential positive effect of decreasing the need for vigilance, although it also causes prey to be depleted faster. The authors tested the hypothesis and found that it was better than alternatives foraging models at describing empirical data, indicating that the assumptions are realistic bases of foraging decisions. 

###### 05.P06

> In the classical DSVM theory mentioned earlier, tradeoffs are assumed between risks of starvation and predation. Many ABM foraging models also incorporate these risks. Railsback and Harvey (2002) used ABM to predict empirical patterns of habitat selection in drift-feeding juvenile trout foraging in a stream, based on assumptions concerning their decisions to choose habitat to forage in, given a range of empirical factors; e.g., water depth, velocity, available food, in the stream environment. The risks involved in deciding to move to a given location were starvation, predation by terrestrial animals, predation by fish, high water velocity (which requires energy to stay in place), stranding, and competition. A bioenergetics model was used to follow daily growth, and daily predation mortality depended on the size of the fish and water depth at its location, which gave the current “state” of the individual. Three foraging strategies were compared, based on the agent's state and prediction of conditions over the near term (thus the authors label their approach “state and prediction theory”). The strategy that compared well with all observed patterns involved daily decisions that maximized, over a longer term, the “expected maturity” (EM), or the product of predicted survival from starvation and other mortality risks and the fraction of reproductive size reached over the period of the 75-day simulation. The EM strategy, in which the fish agent maximizes both growth and survival, gives better results than other maximization criteria, such as maximizing only growth or only survival probability, used in many classical models. 

###### 05.P07

> These studies all illustrate the ability of ABMs not only to incorporate high amounts of the complexity of real ecological systems and their ability to compare output with empirically observed patterns, but also to derive more realistic pictures of the decision-making process. 

###### 05.P08

> Lima (2002) noted the importance of the behavioral decisions of the predator when studying predator-prey interactions, rather than treating predators as “unresponsive black boxes.” Accordingly, ABMs have also been used to extend the focus of predation risk beyond merely the prey strategy to include feedbacks from the predator or from competitors. A detailed investigation of tradeoffs of dusky dolphins choosing between feeding and avoiding predation by killer whales is given in a spatially explicit ABM of Srinivasan et al. (2010). The authors explored the fitness costs and benefits of various escape strategies potentially used by dusky dolphins, including the time spent hiding in a refuge from predation and degree of vigilance when feeding. The model included counter strategies of the amount of time a killer whale would wait for a dolphin to emerge from a refuge, so the model contains a version of game theory. Another example of feedback effects, in this case coming from competition, is illustrated by a model of Peacor et al. (2007). Individual foragers and a common resource for which they compete were simulated, both with and without the presence of a predator. The density of competing foragers affected the tradeoff in foraging. Under low density of competitors, the forager spent 40% of its time eating, but the time eating decreased to 7% when the forager density was high. This outcome resulted from the decreased benefits of foraging, as the resource was reduced by competitors. Such an outcome could not easily be anticipated or incorporated in simple models. A species' response to predation risk can affect whole food chains. An illustration of how behaviors of herbivores can modify top-down effects of predators on plants is the ABM of Schmitz and Booth (1997) for a tri-trophic chain (spiders, grasshoppers, and a food base of two plant types, grass and a herbaceous plant) of individual organisms on a spatial lattice. The spiders could affect the grasshoppers directly, by predation, and indirectly, by causing grasshoppers within a certain radius to move from grass to the safer herb sites. The model allowed the relative effects of direct predation and the predator avoidance by grasshoppers to be examined individually. The model predicted long-term field observations of the predator's top-down effect and showed the importance of including the behavioral response of the herbivore. 



## 06. Social Interactions in Populations

###### 06.P01

> Social behavior requires decisions involving, among other things, reproduction, parental care, and territorial or home range defense. These, plus a wider range of activities, have been represented in ABMs. 

###### 06.P02

> Several studies have addressed the question of when to reproduce, incorporating external factors such as population density and the availability and quality of resources in an area (Stewart et al., 2005; Brouwer et al., 2015). When deciding to reproduce, individual agents within an ABM often consider information of the surrounding environment. An individual agent's decision to reproduce is frequently represented in a logistical or probabilistic manner, in which agents may decide to reproduce if they meet some requirement or threshold. For example, Ye et al. (2014) used a grid-based spatially explicit ABM to gain insight on how the population dynamics of a virtual species is influenced by landscape structure and various life history traits. In the ABM, the resource share of an individual reflects the number of individuals in a spatial cell and the cell's underlying habitat quality. Only individual agents with a resource fraction over a given threshold may reproduce in a given time step with a given probability, reflecting the importance of competition and the quality of the surrounding habitat in driving reproductive success. 

###### 06.P03

> The agent's internal state also influences its decision to reproduce. Hancock et al. (2005) developed an ABM to predict the population dynamics of Bornean bearded pigs, tracking the “fatness index” of each pig agent in the model. The reproduction status of each agent varied according to their respective fatness index, which in turn depended on the available food supply and the density of the pig population. A pig agent decides to reproduce if its fatness index is above a specific threshold, such that agents in a large population with low food supply are unlikely to reproduce due to low fatness indices (Hancock et al., 2005). Fish agents within another ABM also took their internal state into consideration in deciding when to spawn. The ratio of actual weight to expected weight of a fish of a given length (a “condition index”) is tracked for each fish agent, and only agents with ratios over 0.75 were able to spawn (Rashleigh and Grossman, 2005). 

###### 06.P04

> After reproduction, decisions must be made on parental care. Different strategies of parental investment reflect variation in the decision-making process of individuals, and ultimately have consequences for the dynamics of the population. Decisions involved in provisioning of offspring by bluebirds were studied by Davis et al. (1999), from the point of view of survival of the offspring under different conditions of food availability in the environment. The authors performed model simulations for different levels of food availability by assuming four different strategies on feeding decisions: (1) Feed the smallest first, (2) feed the largest first, or (3) feed the hungriest first, in each case going to the next larger, smaller, or less hungry, respectively, if the offspring representing the first choice was full. These choices were compared to random feeding (strategy 4). Environmental conditions determined which strategy maximizes the nest success, in terms of total biomass of surviving fledglings, with strategies (1), (2), and (3) performing best, successively, with increasing food availability. The random strategy was never the best. 

###### 06.P05

> The formation and maintenance of territories and home ranges occurs in many taxa. ABMs can simulate the spatiotemporal changes in resource availability throughout the environment and interactions between various agents through time, potentially elucidating the mechanisms underlying territory and home range dynamics. In order to aid conservation planning for the tiger (Panthera tigris) by providing an estimate of population number, location and size of territories, Carter et al. (2015), modeled territory formation of both females and males using a spatially explicit ABM. Females at 3 years of age were assumed to move to a site within 33 km of their natal site, and at least 2 km away from any other female, and to establish the center of her territory where prey density was highest. If the female failed to find such a site, she lowered the limit on neighboring females from 2 to 1 km. A female was assumed to be able to sense the total prey in her territory and in neighboring spatial cells. She could try to add habitat cells to their territories based on a few decision rules, including prey availability and the status of the neighboring female tiger's hierarchical status (avoiding cells near a female of higher status, which is correlated with age). When possible, she adds habitat cells to her territory until the total amount of prey reaches a certain threshold. Another spatially explicit model of home range dynamics is that of Wang and Grimm (2007) for the common shrew (Sorex araneus). Shrews were assumed to continually adjust their territories by sensing the amount of food in a cell of the habitat and the presence of other individuals. Individuals tried to optimize their home range by preferentially selecting cells with high food sources and avoiding cells occupied by other individuals. Acquisition and release of cells followed an optimization procedure, in which the shrew is assumed capable of ranking all the cells in its territory and releasing the worst ones in favor of adding new ones. These simple model rules predicted realistic territories for both tigers and shrews. 



## 07. Developments in the Modeling of Decisions in Population Models

###### 07.P01

> The papers reviewed above show that ABM is an important departure from earlier mathematical approaches, which, collectively, have been critical theoretical frameworks over the past few decades. In many earlier approaches, the individual was assumed to make a sequence of decisions through time that would result in optimal fitness at some end time. These approaches often assume knowledge of future conditions and ignore the feedbacks on the individuals through changes in the environment created by the individual's own decisions. To incorporate the feedbacks and uncertainty that are present in real ecological systems, a trend in ABMs has been to simulate how proximate decisions are made based on the individual's current state and short-term predictions. This is modeled differently by different modeling groups. As noted earlier, Railsback and Harvey (2002) (see also Railsback et al., 1999) use a “state and prediction theory” strategy for individuals, which estimate an “expected survival” over a specified time horizon over which little appreciable change in the environment is expected, considering the risks of predation, starvation, etc., and choosing the behavior that achieves the best fitness over that time. Giske and his group (e.g., Eliassen et al., 2016) find the adaptive behaviors for situations encountered through selection in genetic algorithms (GA) and artificial neural networks (ANNs). Other ABM modeling approaches include the computational system Digital Organisms in a Virtual Ecosystem (DOVE), in which a GA is used to allow phenotypic plasticity to evolve and interact with a dynamic environment (Peacor et al., 2007). 


###### 07.P02

> Borrowing concepts from machine learning and artificial life studies, modelers such as those noted above have utilized ANN and GA (together referred to as individual-based neural-network-genetic algorithm, or ING techniques) to represent the decision-making processes and consequent behaviors of organisms. Instead of fixed rules governing the way an organism makes decisions, ING techniques are flexible approaches that use principles of neurobiology and natural selection to solve optimization problems, resulting in individuals making adaptive decisions (Huse et al., 1999; Hamblin, 2013). ABMs that use genetic algorithms to govern decisions initialize a population of individuals with different solutions to a given optimization problem. Optimization problems may include finding the decision that will maximize fitness during foraging, or the probability of survival when selecting a patch (Hamblin, 2013). The individuals with the best solutions to the problem are allowed to reproduce through various commonly recognized selection operators, and reproduction continues for many generations. Trebitz (1991) was an early user of a GA-type approach to estimate the optimal spawning time for largemouth bass. In the model a female that spawned too early in spring risked the loss of eggs or larvae due to random cold snaps, while if it spawned too late it risked zooplankton being depleted by the offspring of earlier spawning females. 

###### 07.P03

> ANNs “train” the weights of input data by continuously modifying these weights until the resulting decisions and subsequent behaviors of individuals reach a specific fitness measure. In this way, ANNs and the way they capture the decision-making process of individuals mirror brain functions by “learning” from the outputs of the various input data weight modifications. Once an ANN is trained, it can be used on new input data to determine the decisions and behaviors that satisfy the specific fitness measure (Huse et al., 1999; Lek and Guégan, 1999). In GAs and ANNs, as in the more fixed logical and probabilistic decision-making rules within ABMs discussed earlier, the decision-making processes of individuals are generally geared to optimize some sort of fitness measure, but the decision-making strategy evolves through selection. 


###### 07.P04

> ANNs have been increasingly used to represent the decision-making processes of organisms, particularly with respect to movement through space. As the decisions of real-world individuals are driven by neuronal responses to internal and external stimuli, neural networks are well-suited to represent decision-making in an individual agent (Eliassen et al., 2016). Once a fitness criterion is identified for a given ABM, the ANN can be trained to find the input weights that correspond to outputs best fitting the fitness criterion (Huse et al., 1999). ANN training can occur in several ways, but here we focus on training with GAs, an approach common within ABMs utilizing ANNs. GAs are optimization tools that utilize the principles of crossing over and mutation to essentially “evolve” the decision-making processes of individuals, without the need for probabilistic or logistical rules. 

###### 07.P05

> For example, Okunishi et al. (2009) developed an ABM to simulate the growth and large-scale movements of Japanese sardines with the goal of exploring the effects of climate change on the population dynamics of the species, primarily its distribution and production in the North Pacific. The authors utilized an ANN to represent the way fish decide on movement directions when migrating to spawn. The inputs to the ANN were environmental factors known to influence the migration of sardines and included ocean current speed, the distance from land, and the experienced temperature change during subsequent days. Back propagation (a training method where weights are assigned to the various inputs based on a training data set) was one method used to train the ANN on spawning migration trajectories from actual sardines. The authors also used a GA to find the sardine offspring's input weights that would produce optimal outputs through crossing over and mutation of the parent sardine's weights. In training the ANN with a GA, the sardines' decisions representing swimming directions were allowed to evolve through many simulations; subsequently, the authors were able to find optimal combinations of weights that produce realistic migration trajectories. They found that combining back propagation with a GA to determine input weights produced the most realistic migration trajectories, indicating that utilizing the principles underlying the GA (in tandem with observed movement data) adequately captures the decision-making process of migrating sardines (Okunishi et al., 2009). 

###### 07.P06

> Morales et al. (2005) utilized several ANNs, each in combination with a GA, to determine efficient movement decisions for elk within a spatially explicit ABM. Movement decisions to be made by the elk included when to switch behaviors from foraging to exploring, where to move if foraging or exploring, and which type of plant to consume at a given time if foraging. The fitness measures that characterized the efficiency of elk agent decisions were energy gain for fat reserves and survival probability associated with predation risks. Percent body fat, forage biomass, and local predation risks were a few of the ANN inputs representing both internal and external movement stimuli. Rather than setting specific rules to guide the decision-making processes, the authors allowed the process to evolve over many generations. 

###### 07.P07

> ANNs were also used to model movement in Mueller and Fagan (2008), who noted three basic types of pattern resulting from movement (or lack thereof): sedentary, migratory, and nomadism. The authors assumed that landscape structure drove individual-level movement types and that there were four gradients in hierarchical order; resource abundance, spatial configuration of resources, temporal variability of resource locations, and temporal predictability of resources. Mueller et al. (2011) followed up by using ANNs to evolutionarily train model organisms to use and combine different types of information representing the different movement behaviors (memory, oriented, and non-oriented movements). 240 individual animals were simulated moving across landscape and making choices of patches and, in doing so, depleting exhaustible resources. Different movement strategies involving combinations of these movement types worked better on different landscape types. After 5,000 generations with inheritance, survivors using unique movement strategies had optimized fitness on particular landscapes. 


###### 07.P08

> In incorporating optimization of fitness, classic analytic models omit consideration of the immediate, or proximate, complexities that organisms encounter. This allows the integration of individual strategies with ultimate fitness, but the proximate mechanisms through which organisms solve problems are largely ignored (Sih et al., 2004; Fawcett et al., 2013; Eliassen et al., 2016). Animals need to be able to respond quickly and adequately in situations they have never experienced before; that is, the world is too complex for evolution to produce rules for every possible circumstance. It is likely that animals will evolve rules that perform well on average in their natural environment (McNamara and Houston, 2009). One of the basic advantages of ABMs is their ability to incorporate such heuristic, or rule of thumb, decision-making to perform well in complex environments. The GA approach allows one to simulate how such rules evolve. 


###### 07.P09

> Toward this end Giske et al. (2013) formulated a model based on recent insights from a range of empirical disciplines that sheds light on the processes involved with decision making. In vertebrates, multipurpose rules are arbitrated through an “emotion system,” which describes the integration of information, motivation, and physiological state in determining physiological and behavioral outcomes. These outcomes affect the survival, growth, development, space use, and life history of the organism. Giske et al. (2013) modeled fish, where the fish had the choice of moving among different depths. Fish at deeper depths were generally safer from predation, but food was more limited, though uncertainty was entered into the model by letting both food levels and predation risk vary stochastically from fish generation to generation. The authors employed the survival-circuit concept (LeDoux, 2012), in which emotions form the basis for decisions, and they contribute to the survival or fitness of the organism. The first half of the survival-circuit is “emotional appraisal.” It starts with sensory input, considers motivational impact related to developmental stage, and may potentially activate the organism into a “global organismic state,” such that the whole organism is focusing on the situation. The second half of the survival circuit; the “emotional response,” consists of physiological responses and behavior. Physiological activation enables the organism to focus its sensory attention, brain activity, and potentially also bodily functions, such as heartbeat and muscle tension, toward the present situation. Fear and hunger are the emotions, and the ABM includes sensory inputs. The options for a fish are to stay at its current depth or move a short distance upward or downward, as determined by equations incorporating hunger and fear. On the basis of its global organismic state, the motivated fish behaves in a way that maximizes its net neuronal response. 

###### 07.P10

> The model of Giske et al. (2013) predicted the same general type of spatial distribution patterns that classic optimization and game models produce, such as diel vertical migration with some extension around the average. But the model of Giske et al. (2013) differed from the classic models by allowing the fish to respond on immediate timescales to food and perceived risk, as opposed to optimization criteria involving only long-term goals. For example, danger is avoided because of an evolved proximate preference to stay with others or in darker waters when afraid, while danger is largely ignored when hungry. This is important in a fluctuating environment, where simple rules of thumb couple proximate constraints in determining behavior, with long-term adaptive value. 



## 08. Prospectus

###### 08.P01

> In his book “Sociobiology,” Wilson (1975) foresaw the gradual merger of population biology and behavioral ecology and the growing importance of neurophysiology to the latter (Wilson's Figure 1.2). These developments have been accelerated through ABM and ANN, particularly through using ABM as a means through which population and community dynamics emerge from the adaptive traits of individuals, including “how individuals make decisions in response to other individuals, the environment, or changes in themselves” (Grimm and Railsback, 2005). 


###### 08.P02

> Future development of ABM in modeling decision-making in ecology will be influenced by the continued refinement of modeling methodology and increases in needed data for parameterizing ABMs. Two of the modeling methodologies, the “state and predict” (Railsback and Harvey, 2002) and ING (Eliassen et al., 2016) continue to be developed. In particular, a cognitive architecture based on the survival-circuit concept (LeDoux 2012) forms a general modeling framework for linking decision-making to neurobiological mechanisms (Bach and Dayan, 2017; Landsrød, 2017; Budaev et al., 2018). Other approaches to providing rules of thumb for individuals, such as Fuzzy Cognitive Maps (FCM), based on Fuzzy Set Theory (Berkes and Berkes, 2009), are also being used in evolving predator-prey systems. In addition, off the shelf ABM modeling programs such as NetLogo and Ecobeaker are making development and use of ABM easier (e.g., Railsback and Grimm, 2011). Concerning relevant data, ABMs generally require a large amount of data at the individual level and site level. Such data are generally only available for ecological systems that have been intensively studied. But technology is rapidly increasing data collection capabilities, and the availability of remote sensing data and the ease with which these data are integrated within the ABM framework facilitates the development of decision rules based on a plethora of environmental attributes that potentially drive animal decisions. This may facilitate wider use of ABM, though this will require more coordinated efforts in making data broadly available to the modeling community (Hampton et al., 2013). 


###### 08.P03

> Recent advancements in technological tools should facilitate the parameterization of future ABMs developed for simulating dispersal, migration, and local-scale movements of animal groups. In particular, developments in GPS telemetry (and satellite telemetry in general) and biotelemetry devices have allowed for remote tracking of an individual's movement, physiological state, and behavior over long periods of time at relatively fine temporal resolutions (Cooke et al., 2004). This is especially useful considering the challenges ecologists face when attempting to directly observe and study free-ranging animals in a non-invasive manner. Basic movement parameters, including step length and turning angle distributions, can be derived from a time series of relocation data obtained from GPS and satellite telemetry and together shed light onto the limits of an individual's motion capacity. Subsequently, parameters driving agent movement within an ABM can be made more accurate. Bioenergetic models used to track agents' growth and reproduction within ABMs can be further parametrized with information gained from biotelemetry monitoring of undisturbed animals in their natural environments. The wealth of data generated for many species thus far should allow ecologists to more accurately model how individuals decide on an action in response to dynamic internal and external variables. What will most define the future success of ABM will be its ability to address complex questions that are difficult for traditional approaches. These questions include, among many others, the origin of collective actions, the interactions of tradeoffs at the individual level and the whole ecological system, the dynamics of complex social systems, and applications to conservation and management issues. 


###### 08.P04

> How collective actions such as migration are initiated, usually by a small fraction of leaders, has been discussed as resulting from differences in experience within populations (Ferno et al., 1998; Krause et al., 2000). Collective actions that benefit the whole group, but which may have negative fitness consequences for individuals, have long attracted attention, but are still not well-understood and may profit from use of ABM. An example is “mobbing action” by birds against nest threats. Unrelated birds and even birds of different species may be involved in these aggressive actions against a threat to nests, such as hawks or owls. While there is clear benefit to each individual in protecting its nest, there are also costs, such as becoming a victim of the threat or revealing the location of one's nest. Wheatcroft and Price (2018), in an empirical/theoretical study, proposed that collective action in this case can build up among birds whose nest locations are distributed across various distances from the threat. Birds nearest the nest respond first, and others that have nests farther and farther away decide to join as the risk to any individual declines with the growing size of the mob. The authors used a mathematical model with two individuals to analyze the amount of investment in each in aggressiveness to the threat. While the mathematical model provides insight, this is the type of problem where an ABM, which can simulate the actions of many birds with individual variation, could provide output directly comparable with observations of mobbing behavior. 


###### 08.P05

> Social interactions of at least moderate complexity already occur in several of the models noted above, in which social hierarchies constrain actions, but extension to much more complex interactions is possible using ABM. For example, in many primate troops the type and level of interaction between individuals, whether positive (cooperation) or negative (e.g., fighting) depends on genetic relatedness. Because there is kin-recognition, any interaction, such as a fight between two unrelated individuals, can give rise to a larger complex of interactions involving their relatives (Cheney and Seyfarth, 1992). Modeling the behavior of such societies may require ABM to represent a network of relevant interactions. 


###### 08.P06

> Behavioral ecologists and modelers like to think that their work can have some useful applications in conservation and wildlife management. A review by Caro (2007) of application of ecological theory found little evidence that many of the applications proposed so far by behavioral ecology, based on hypothetical conditions, would be effective in practice. However, ABM may be able to bridge the gap between theory and real conservation issues (Wood et al., 2015). For example, to elucidate whether specific predation strategies influenced the nesting success of waterfowl, Ringelman (2014) simulated the movements of different predators in a landscape with clumped and dispersed nests. The results of the ABM suggested that managers concerned with nesting success of waterfowl should consider the various behavioral strategies used by nest predators when creating and managing potential nesting habitat. The results highlight the practical applications of ABMs, particularly when utilized as tools for wildlife ecology investigations (some examples of which are detailed in McLane et al., 2011). 


###### 08.P07

> The above are all areas in which ABM incorporating decision-making has room to expand. ABM is still a young field, and its potential for contributing to the understanding of how decisions are made by animals and how they affect whole ecosystems has yet to be fully exploited. 




## 

<style type="text/css">
	img{width: 51%; float: right;}
</style>

<!-- -------------------------------------------- -->
[orig]: https://www.frontiersin.org/articles/10.3389/fevo.2018.00237/full
[mend]: https://www.mendeley.com/viewer/?fileId=3d78bb79-89c8-e37f-6254-22f7f29d68ef&documentId=2f302485-626d-340d-abc7-86c0d24bfe06
[figs]: .
[fig_01]: https://www.frontiersin.org/files/Articles/428465/fevo-06-00237-HTML/image_m/fevo-06-00237-g001.jpg
[fig_02]: https://www.frontiersin.org/files/Articles/428465/fevo-06-00237-HTML/image_m/fevo-06-00237-g002.jpg

<!-- ref -->

<!-- 01p01 -->
[2009_Bray]: . ""
[2009_Wagner]: . ""
[2006_Deneubourg_Detrain]: . ""
[2010_Ydenberg]: . ""
[2015_Rypstra]: . ""

<!-- 01p02 -->

<!-- 02p01 -->

<!-- 02p02 -->
[1961_Fraenkel_Gunn]: . ""
[1984_Schöne]: . ""
[1991_Bell]: . ""
[1999_Grünbaum]: . ""
[2016_Gautestad]: . ""
[2004_Humston]: . ""
[1996_Zollner_Lima]: . ""
[1988_Fahrig]: . ""
[1976_Charnov]: . ""
[1988_Clark_Mangel]: . ""
[1999_McNamara_Houston]: . ""
[2000_Mangel_Clark]: . ""

<!-- 02p03 -->
[2000_Gilliam_Skalski]: https://pdfs.semanticscholar.org/3b3b/39b3456e3854ade5b74f5a763304e8710565.pdf "Skalski, G.T. and Gilliam, J.F., 2000. Modeling diffusive spread in a heterogeneous population: a movement study with stream fish. Ecology, 81(6), pp.1685-1700."
[2008_MatthiopoulosJ_ThomasL_PattersonTA]: http://fics.hiit.fi/files/Patterson%20et%20al%202008%20TREE.pdf "Patterson, T.A., Thomas, L., Wilcox, C., Ovaskainen, O. and Matthiopoulos, J., 2008. State–space models of individual animal movement. Trends in ecology & evolution, 23(2), pp.87-94."
[2018_Çabukoglu_Gorban]: https://arxiv.org/pdf/1804.01342.pdf "Gorban, A.N. and Çabukoǧlu, N., 2018. Mobility cost and degenerated diffusion in kinesis models. Ecological complexity, 36, pp.16-21."
[2004_Bertozzi_Topaz]: . ""
[2008_Lutscher]: . ""
[2015_Almeida]: . ""
[2016_Petrovskii_Tilles]: . ""
[2004_Tyutyunov]: . ""
[1999_OlsonDonald_GrünbaumD_FlierlG]: https://www.sciencedirect.com/science/article/pii/S0022519398908426 "Flierl, G., Grünbaum, D., Levins, S. and Olson, D., 1999. From individuals to aggregations: the interplay between behavior and physics. Journal of Theoretical biology, 196(4), pp.397-454."

<!-- 02p04 -->
[1966_Pianka_MacArthur]: . ""
[1974_Pulliam]: . ""
[1992_Roff]: . ""
[1969_Lucas_Fretwell]: . ""
[2004_Vos]: . ""
[2007_DeAngelis]: . ""

<!-- 02p05 -->
[1982_Abrams]: . ""
[1993_Abrams]: . ""
[1990_Dill_Lima]: . ""
[1993_Matsuda_Abrams]: . ""
[2003_Peacor_Werner]: . ""
[2009_Feng]: . ""
[1983_Hammerstein_Richert]: https://www.annualreviews.org/doi/pdf/10.1146/annurev.es.14.110183.002113 "Riechert, S.E. and Hammerstein, P., 1983. Game theory in the ecological context. Annual Review of Ecology and Systematics, 14(1), pp.377-409."

<!-- 03p01 -->
[1987_Dill]: . ""
[2008_Stamps_Biro]: . ""
[2017_Jordan_Beekman]: . ""
[2003_Bolnick]: . ""
[2018_Blake]: . ""
[2011_Araújo]: . ""
[2012_Dall]: . ""
[2011_Wolf]: . ""
[2011_VasseurDavid_AmarasekarePriyanga_BolnickDanielI]: https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3088364/ "Bolnick, D.I., Amarasekare, P., Araújo, M.S., Bürger, R., Levine, J.M., Novak, M., Rudolf, V.H., Schreiber, S.J., Urban, M.C. and Vasseur, D.A., 2011. Why intraspecific trait variation matters in community ecology. Trends in ecology & evolution, 26(4), pp.183-192."

<!-- 03p02 -->
[1972_Botkin]: . ""
[2005_Mooij_DeAngelis]: . ""
[2014_GrimmV_DeAngelisDL]: https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4047944/  "DeAngelis, D.L. and Grimm, V., 2014. Individual-based models in ecology after four decades. F1000prime reports, 6."
[1998_Parunak]: . ""
[2001_Railsback]: . ""
[2018_Vincenot]: . ""

<!-- 03p03 -->
[2005_Railsback_Grimm]: . ""

<!-- 04p01 -->
[2010_Bennett_Tang]: . ""
[1995_Duning]: . ""
[2013_Klaassen_Bauer]: . ""

<!-- figure 2 -->
[2014_Baguette]: . ""

<!-- 0401p01 -->
[2011_Semeniuk]: . ""
[2013_Martin]: . ""
[2017_Driscoll_Doherty]: . ""
[1998_VanWinkle]: . ""
[2017_Marley]: . ""

<!-- 0401p02 -->
[1995_Neuert]: . ""

<!-- 0401p03 -->
[2013_VanMoorter]: . ""
[2009_KlaassenMarcel_BauerSilke_DuriezOlivier]: https://academic.oup.com/beheco/article/20/3/560/185692 "Duriez, O., Bauer, S., Destin, A., Madsen, J., Nolet, B.A., Stillman, R.A. and Klaassen, M., 2009. What decision rules might pink-footed geese use to depart on migration? An individual-based model. Behavioral Ecology, 20(3), pp.560-569."

<!-- 0401p04 -->
[2014_Bocedi]: . ""

<!-- 0402p01 -->
[2010_Bennett_Tang]: . ""
[2008_Nathan]: . ""
[2017_DriscollDonA_DohertyTimS]: https://royalsocietypublishing.org/doi/pdf/10.1098/rspb.2017.2272 "Doherty TS, Driscoll DA. 2017 Coupling movement and landscape ecology for animal conservation in production landscapes. Proc. R. Soc. B 285: 20172272. http://dx.doi.org/10.1098/rspb.2017.2272"

<!-- 0402p02 -->
[2012_Semeniuk]: . ""
[2015_Watkins]: . ""
[2004_Carter_Lewison]: . ""

<!-- 0402p03 -->
[2014_Aben]: . ""
[2016_Allen]: . ""
[2013_Kanagaraj]: . ""
[2012_Anadón]: . ""
[2007_Graf]: . ""

<!-- 0403p01 -->
[2010_Krause]: . ""
[2006_SumpterDavidJT]: https://www.ncbi.nlm.nih.gov/pmc/articles/PMC1626537/ "Sumpter, D.J., 2005. The principles of collective animal behaviour. Philosophical transactions of the royal society B: Biological Sciences, 361(1465), pp.5-22."

<!-- 0403p02 -->
[2003_Krause_Couzin]: . ""
[1992_Wissel_Huth]: . ""
[2005_Kunz_Hemelrijk]: . ""
[2002_Couzin]: . ""

<!-- 0403p03 -->
[1996_Gueron]: . ""
[2004_Hoare]: . ""

<!-- 05p03 -->
[2008_Kanarek]: . ""

<!-- 05p04 -->
[1997_Stillman]: . ""