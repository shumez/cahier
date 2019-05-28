<!--
Filename: 	190517_LynnChristopherW_2019.md
Project: 	/Users/shume/Documents/Cahier
Author: 	shumez <https://github.com/shumez>
Created: 	2019-05-17 20:31:0
Modified: 	2019-05-28 11:30:57
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

[Original] | [Mendeley]

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

> It is our good fortune as physicists to seek to understand the nature of the observable world around us. In this inquiry, we need not reach to contemporary science to appreciate the fact that our perception of the world around us is inextricably linked to the world within us: the mind. Indeed, even Aristotle c. 350 B.C. noted that it is by mapping the structure of the world that the human comes to understand their own mind ^[1][ref01]^. “Mind thinks itself because it shares the nature of the object of thought; for it becomes an object of thought in coming into contact with and thinking its objects, so that mind and object of thought are the same” ^[2][ref02]^. Over the ensuing 2000-plus years, it has not completely escaped notice that the mappers of the world have unique contributions to offer the mapping of the mind (from Thales of Miletus, c. 624–546 B.C., to Leonardo Da Vinci, 1452–1519). More recently, it is notable that nearly all famous physicists of the early 20th century – Albert Einstein, Niels Bohr, Erwin Schroedinger, Werner Heisenberg, Max Born – considered the philosophical implications of their observations and theories ^[3][ref03]^. In the post-war era, philosophical musings turned to particularly conspicuous empirical contributions at the intersection of neuroscience and artificial intelligence, spanning polymath John von Neumann’s work enhancing our understanding of computational architectures ^[4][ref04]^ and physicist John Hopfield’s invention of the associative neural network, which revolutionized our understanding of collective computation ^[5][ref05]^.

> In the contemporary study of the mind and its fundamental organ – the brain – nearly all of the domains of physics, perhaps with the exception of relativity, are not only relevant but truly essential, motivating the early [coinage] of the term neurophysics some four decades ago ^[6][ref06]^. The fundamentals of electricity and magnetism prove critical for building theoretical models of neurons and the transmission of action potentials ^[7][ref07]^. These theories are being increasingly informed by mechanics to understand how force-generating and load-bearing proteins bend, curl, kink, buckle, constrict, and stretch to mediate neuronal signaling and plasticity ^[8][ref08]^. Principles from thermodynamics come into play when predicting how the brain samples the environment (action) or shifts the distribution of information that it encodes (perception) ^[9][ref09]^. Collectively, theories of brain function are either [buttress]ed or [dismantle]d by imaging, with common tools including magnetic resonance imaging ^[10][ref10]^ and magnetoencephalography ^[11][ref11]^, the latter being built on superconducting quantum interference devices and next-generation quantum sensors that can be embedded into a system that can be worn like a helmet, revolutionizing our ability to measure brain function while allowing free and natural movement ^[12][ref12]^. Moreover, recent developments in nanoscale analysis tools and in the design and synthesis of nanomaterials have generated optical, electrical, and chemical methods to explore brain function by enabling simultaneous measurement and manipulation of the activity of thousands or even millions of neurons ^[13][ref13]^. Beyond its relevance for continued imaging advance- ments ^[14][ref14]^, optics has come to the fore of neuroscience over the last decade with the development of optogenetics, an approach that uses light to alter neural processing at the level of single spikes and synaptic events, offering reliable, millisecond-timescale control of excitatory and inhibitory synaptic transmission ^[15][ref15]^.




<!-- [![fig01][fig01]][fig01] -->

### References

01. [Scott, A. Neurophysics (Wiley, 1977).][ref01]
02. [Koch, C. & Poggio, T. A theoretical analysis of electrical properties of spines. Proc. R. Soc. Lond. B Biol. Sci. 218, 455–477 (1983).][ref02]
03. 
04. 
05. 
06. 
07. 
08. 
09. 
10. 
11. 
12. [Fries, P. Rhythms for cognition: communication through coherence. Neuron 88, 220–235 (2015).][ref12]

## 

<style type="text/css">
	img{width: 50%; float: right;}
</style>

<!-- -------------------------------------------- -->
[Original]: https://www.nature.com/articles/s42254-019-0040-8
[Mendeley]: https://www.mendeley.com/viewer/?fileId=78370c2e-5094-45f9-7007-f9d192a513ef&documentId=0f2066dc-1282-395d-a1f0-9718a7c5860e

[00]: #00_abstract
[01]: #01_introduction
[02]: #02_the_physics_of_brain_network_structure
[box1]: #box_1
[0201]: #0201_measureing_brain_netrork_structure
[0202]: #0202_modeling_brain_network_structure
[020201]: #020201_random_structure
[020202]: #020202_community_structure
[020203]: #020203_small-world_structure
[020204]: #020204_hub_structure
[020205]: #020205_spatial_structure
[020206]: #020206_competition_between_structural_properties
[0203]: #0203_the_future_of_brain_network_structure
[box2]: #box_2
[03]: #03_the_physics_of_brain_network_function
[0301]: #0301_measuring_brain_network_function
[0302]: #0302_modeling_brain_network_function
[030201]: #030201_artificial_models
[030202]: #030202_biophysical_models
[0303]: #0303_the_future_of_brain_network_function
[box3]: #box_3
[04]: #04_perteration_experiments_and_the_physics_of_brain_network_control
[0401]: #0401_trageted_perturbations_and_clinical_interventions
[0402]: #0402_network_control_in_the_brain
[box4]: #box_4
[0403]: #0403_the_future_of_brain_network_control
[05]: #05_conclusions_and_future_directions_in_the_neurophysics_of_brain_networks

<!-- fig -->
[fig01]: .


<!-- ref -->
[ref01]: . "Scott, A. Neurophysics (Wiley, 1977)."
[ref02]: . "Koch, C. & Poggio, T. A theoretical analysis of electrical properties of spines. Proc. R. Soc. Lond. B Biol. Sci. 218, 455–477 (1983)."
[ref03]: .
[ref04]: .
[ref05]: .
[ref06]: .
[ref07]: .
[ref08]: .
[ref09]: .
[ref10]: .
[ref11]: .
[ref12]: https://www.sciencedirect.com/science/article/pii/S0896627315008235 "Fries, P. Rhythms for cognition: communication through coherence. Neuron 88, 220–235 (2015)."
[ref13]: .
[ref14]: .
[ref15]: .



<!-- terminology -->
[feat]: . "偉業"
[instantiate]: . "例示する"
[stipulate]: . "規定する"
[perturbative]: . "動揺, 混乱"
[coinage]: . "硬貨"
[buttress]: . "控壁で支える, 支持する, 強化する"
[dismantle]: . "分解する, 取り壊す"