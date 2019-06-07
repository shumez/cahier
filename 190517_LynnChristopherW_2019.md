<!--
Filename: 	190517_LynnChristopherW_2019.md
Project: 	/Users/shume/Documents/Cahier
Author: 	shumez <https://github.com/shumez>
Created: 	2019-05-17 20:31:0
Modified: 	2019-06-07 17:33:15
-----
Copyright (c) 2019 shumez
-->

# 19-05-17 The physics of brain network structure, function and control

Lynn, C. W., & Bassett, D. S. (2019). The physics of brain network structure, function and control. Nature Reviews Physics, 1.

```tex
@article{lynn2019physics,
  title={The physics of brain network structure, function and control},
  author={Lynn, Christopher W and Bassett, Danielle S},
  journal={Nature Reviews Physics},
  pages={1},
  year={2019},
  publisher={Nature Publishing Group}
}
```

[Original] | [Arxiv] | [Mendeley]

## ToC

* [00. Abstract][00]
* [01. Introduction][01]
* [02. The physics of brain network structure][02]
	* [Box 1][box1]
	* [02.01. Measureing brain netrork structure][0201]
	* [02.02. Modeling brain network structure][0202]
		* [02.02.01. Random structure][020201]
		* [02.02.02. Community structure][020202]
		* [02.02.03. Small-world structure][020203]
		* [02.02.04. Hub structure][020204]
		* [02.02.05. Spatial structure][020205]
		* [02.02.06. Competition between structural properties][020206]
	* [02.03. The future of brain network structure][0203]
	* [Box 2][box2]
* [03. The physics of brain network function][03]
	* [03.01. Measuring brain network function][0301]
	* [03.02. Modeling brain network function][0302]
		* [03.02.01. Artificial models][030201]
		* [03.02.02. Biophysical models][030202]
	* [03.03. The future of brain network function][0303]
	* [Box 3][box3]
* [04. Perteration experiments and the physics of brain network control][04]
	* [04.01. Trageted perturbations and clinical interventions][0401]
	* [04.02. Network control in the brain][0402]
	* [Box 4][box4]
	* [04.03. The future of brain network control][0403]
* [05. Conclusions and future directions in the neurophysics of brain networks][05]


## Summary

## Further

## Terminology


## Original

### 00. Abstract

> The brain is characterized by heterogeneous patterns of structural connections supporting unparalleled [feat]s of cognition and a wide range of behaviours. New non-invasive imaging techniques now allow comprehensive mapping of these patterns. However, a fundamental challenge remains to understand how the brain’s structural wiring supports cognitive processes, with major implications for personalized mental health treatments. Here, we review recent efforts to meet this challenge, drawing on physics intuitions, models and theories, spanning the domains of statistical mechanics, information theory, dynamical systems and control. We first describe the organizing principles of brain network architecture [instantiate]d in structural wiring under constraints of spatial embedding and energy minimization. We then survey models of brain network function that [stipulate] how neural activity propagates along structural connections. Finally, we discuss [perturbative] experiments and models for brain network control; these use the physics of signal transmission along structural connections to infer intrinsic control processes that support goal-directed behaviour and to inform stimulation-based therapies for neurological and psychiatric disease. Throughout, we highlight open questions that invite the creative efforts of pioneering physicists.

#### 00.01. Key points

* From the first measurement of the nerve impulse by Hermann von Helmholtz in 1849 to the cutting-edge superconducting devices used in magnetoencephalography, physics and neuroscience have always been inextricably linked.
* Today, network neuroscience — the study of the brain as a complex web of interacting components — draws intuitions and techniques from nearly every branch of physics.
* The architecture of structural connections between neurons or brain regions is constrained by requirements of energy minimization and efficient information transfer.
* The materialization of long-range correlations and synchronization from the collective firing of individual neurons conjures notions of emergence and criticality from statistical mechanics.
* Together, these investigations of brain network structure and function guide targeted treatments for cognitive disorders using theories of network control.
* Now more than ever, understanding the complexities of the mind lies at the feet of curious and pioneering physicists.

### 01. Introduction

> It is our good fortune as physicists to seek to understand the nature of the observable world around us. In this inquiry, we need not reach to contemporary science to appreciate the fact that our perception of the world around us is inextricably linked to the world within us: the mind. Indeed, even Aristotle c. 350 B.C. noted that it is by mapping the structure of the world that the human comes to understand their own mind ^[1]^. “Mind thinks itself because it shares the nature of the object of thought; for it becomes an object of thought in coming into contact with and thinking its objects, so that mind and object of thought are the same” ^[2]^. Over the ensuing 2000-plus years, it has not completely escaped notice that the mappers of the world have unique contributions to offer the mapping of the mind (from Thales of Miletus, c. 624–546 B.C., to Leonardo Da Vinci, 1452–1519). More recently, it is notable that nearly all famous physicists of the early 20th century – Albert Einstein, Niels Bohr, Erwin Schroedinger, Werner Heisenberg, Max Born – considered the philosophical implications of their observations and theories ^[3]^. In the post-war era, philosophical musings turned to particularly conspicuous empirical contributions at the intersection of neuroscience and artificial intelligence, spanning polymath John von Neumann’s work enhancing our understanding of computational architectures ^[4]^ and physicist John Hopfield’s invention of the associative neural network, which revolutionized our understanding of collective computation ^[5]^.

> In the contemporary study of the mind and its fundamental organ – the brain – nearly all of the domains of physics, perhaps with the exception of relativity, are not only relevant but truly essential, motivating the early [coinage] of the term neurophysics some four decades ago ^[6]^. The fundamentals of electricity and magnetism prove critical for building theoretical models of neurons and the transmission of action potentials ^[7]^. These theories are being increasingly informed by mechanics to understand how force-generating and load-bearing proteins bend, curl, kink, buckle, constrict, and stretch to mediate neuronal signaling and plasticity ^[8]^. Principles from thermodynamics come into play when predicting how the brain samples the environment (action) or shifts the distribution of information that it encodes (perception) ^[9]^. Collectively, theories of brain function are either [buttress]ed or [dismantle]d by imaging, with common tools including magnetic resonance imaging ^[10]^ and magnetoencephalography ^[11]^, the latter being built on superconducting quantum interference devices and next-generation quantum sensors that can be embedded into a system that can be worn like a helmet, revolutionizing our ability to measure brain function while allowing free and natural movement ^[12]^. Moreover, recent developments in nanoscale analysis tools and in the design and synthesis of nanomaterials have generated optical, electrical, and chemical methods to explore brain function by enabling simultaneous measurement and manipulation of the activity of thousands or even millions of neurons ^[13]^. Beyond its relevance for continued imaging advance- ments ^[14]^, optics has come to the fore of neuroscience over the last decade with the development of optogenetics, an approach that uses light to alter neural processing at the level of single spikes and synaptic events, offering reliable, millisecond-timescale control of excitatory and inhibitory synaptic transmission ^[15]^.

> Such astounding advances, enabled by the intersection of physics and neuroscience, have motivated the construction of a National Brain Observatory at the Argonne National Laboratory (Director: Peter Littlewood, previously of Cavendish Laboratories) funded by the National Sci- ence Foundation, as well as frequent media coverage including titles in the APS News such as “Physicists, the Brain is Calling You.”16 And as physicists answer the call, our understanding of the brain deepens and our ability to mark and measure its component parts expands. Yet alongside this growing systematization and archivation, we have begun to face an increasing realization that it is the interactions between hundreds or thousands of neurons that generate the mind’s functional states 13. Indeed, from interactions among neural components emerge computation 17, commu- nication 18, and information propagation 19. We can confidently state of neuroscience what Henri Poincare, the French mathematician, theoretical physicist, and philosopher of science, states of sci- ence generally: “The aim of science is not things themselves, as the dogmatists in their simplicity imagine, but the relations among things; outside these relations there is no reality knowable.”20 The overarching goal of mapping these interactions in neural systems has motivated multibillion-dollar investments across the United States (the Brain Initiative generally, and the Human Connectome Project specifically 21), the European Union (the Blue Brain Project 22), China (the China Brain Project 23), and Japan (Japan’s Brain/MINDS project 24).

> While it is clear that interactions are paramount, exactly how the functions of the mind arise from these interactions remains one of the fundamental open questions of brain science 25. To the physicist, such a question appears to exist naturally within the purview of statistical mechanics 26, with one major caveat: the interaction patterns observed in the brain are far from regular, such as those observed in crystalline structures, and are also far from random, such as those observed in fully disordered systems 27. Indeed, the observed heterogeneity of interaction patterns in neural systems – across a range of spatial and temporal scales – generally limits the utility of basic contin- uum models or mean-field theories, which would otherwise comprise our natural first approaches. Fortunately, similar observations of interaction heterogeneity have been made in other technologi- cal, social, and biological systems, leading to concerted efforts to develop a statistical mechanics of complex networks 28. The resultant area of inquiry includes criteria for building a network model of a complex system 29, statistics to quantify the architecture of that network 30, models to stipulate the dynamics that can occur both in and on a network 31–33, and theories of network function and control 34,35.

> Here, we provide a brief review for the curious physicist, spanning the network-based ap- proaches, statistics, models, and theories that have recently been used to understand the brain. Importantly, the interpretations that can be rationally drawn from all such efforts depend upon the nature of the network representation 29, including its descriptive, explanatory, and predictive valid- ity – topics that are treated with some philosophical rigor elsewhere 36. Following a simple primer on the nature of network models, we discuss the physics of brain network structure, beginning with an exposition regarding measurement before turning to an exposition regarding modeling. In a parallel line of discourse, we then discuss the physics of brain network function, followed by a description of perturbation experiments and brain network control. In each section we separate our remarks into the known and the unknown, the past and the future, the fact and the speculation. Our goal is to provide an accessible introduction to the field, and to inspire the younger generation of physicists to courageously tackle some of the most pressing open questions surrounding the inner workings of the mind.


### 02. The physics of brain network structure

#### Box 1: A simple primer on networks

#### 02.01. Measureing brain netrork structure

#### 02.02. Modeling brain network structure

##### 02.02.01. Random structure

##### 02.02.02. Community structure

##### 02.02.03. Small-world structure

##### 02.02.04. Hub structure

##### 02.02.05. Spatial structure

##### 02.02.06. Competition between structural properties

#### 02.03. The future of brain network structure

#### Box 2: Bridging spatiotemporal scales

### 03. The physics of brain network function

#### 03.01. Measuring brain network function

#### 03.02. Modeling brain network function

##### 03.02.01. Artificial models

##### 03.02.02. Biophysical models

#### 03.03. The future of brain network function

#### Box 3: Information theory and network neuroscience

### 04. Perteration experiments and the physics of brain network control

#### 04.01. Trageted perturbations and clinical interventions

#### 04.02. Network control in the brain

#### Box 4: Linear control and network controllability

#### 04.03. The future of brain network control

### 05. Conclusions and future directions in the neurophysics of brain networks


<!-- [![fig01][fig01]][fig01] -->

### References

01. [Scott, A. Neurophysics (Wiley, 1977).][1]
02. [Koch, C. & Poggio, T. A theoretical analysis of electrical properties of spines. Proc. R. Soc. Lond. B Biol. Sci. 218, 455–477 (1983).][2]
03. 
04. 
05. 
06. 
07. 
08. 
09. 
10. 
11. 
12. [Fries, P. Rhythms for cognition: communication through coherence. Neuron 88, 220–235 (2015).][12]

## 

<!-- -------------------------------------------- -->
[Original]: https://www.nature.com/articles/s42254-019-0040-8
[Arxiv]: https://arxiv.org/abs/1809.06441
[Mendeley]: https://www.mendeley.com/viewer/?fileId=78370c2e-5094-45f9-7007-f9d192a513ef&documentId=0f2066dc-1282-395d-a1f0-9718a7c5860e

<!-- toc -->
[00]: #00_abstract
[01]: #01_introduction
[02]: #02_the_physics_of_brain_network_structure
[box1]: #box_1_a_simple_primer_on_networks
[0201]: #0201_measureing_brain_netrork_structure
[0202]: #0202_modeling_brain_network_structure
[020201]: #020201_random_structure
[020202]: #020202_community_structure
[020203]: #020203_small-world_structure
[020204]: #020204_hub_structure
[020205]: #020205_spatial_structure
[020206]: #020206_competition_between_structural_properties
[0203]: #0203_the_future_of_brain_network_structure
[box2]: #box_2_bridging_spatiotemporal_scales
[03]: #03_the_physics_of_brain_network_function
[0301]: #0301_measuring_brain_network_function
[0302]: #0302_modeling_brain_network_function
[030201]: #030201_artificial_models
[030202]: #030202_biophysical_models
[0303]: #0303_the_future_of_brain_network_function
[box3]: #box_3_information_theory_and_network_neuroscience
[04]: #04_perteration_experiments_and_the_physics_of_brain_network_control
[0401]: #0401_trageted_perturbations_and_clinical_interventions
[0402]: #0402_network_control_in_the_brain
[box4]: #box_4_linear_control_and_network_controllability
[0403]: #0403_the_future_of_brain_network_control
[05]: #05_conclusions_and_future_directions_in_the_neurophysics_of_brain_networks

<!-- fig -->


<!-- ref -->
[1]: # "Scott, A. Neurophysics (Wiley, 1977)."
[2]: # "Koch, C. & Poggio, T. A theoretical analysis of electrical properties of spines. Proc. R. Soc. Lond. B Biol. Sci. 218, 455–477 (1983)."
[3]: #
[4]: #
[5]: #
[6]: #
[7]: #
[8]: #
[9]: #
[10]: #
[11]: #
[12]: https://www.sciencedirect.com/science/article/pii/S0896627315008235 "Fries, P. Rhythms for cognition: communication through coherence. Neuron 88, 220–235 (2015)."
[13]: #
[14]: #
[15]: #


<!-- terminology -->
[feat]: # "偉業"
[instantiate]: # "例示する"
[stipulate]: # "規定する"
[perturbative]: # "動揺, 混乱"
[coinage]: # "硬貨"
[buttress]: # "控え壁で支える, 支持する, 強化する"
[dismantle]: # "分解する, 取り壊す"

<style type="text/css">
	img{width: 50%; float: right;}
</style>