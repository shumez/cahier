<!--
Filename: 	190920_SizemoreAnnE_2019.md
Project: 	/Users/shume/Documents/Cahier
Author: 	shumez <https://github.com/shumez>
Created: 	2019-09-20 15:14:4
Modified: 	2019-09-23 11:27:35
-----
Copyright (c) 2019 shumez
-->

# 19-09-20 Sizemore, Ann E., 2019

> Sizemore, Ann E., Jennifer E. Phillips-Cremins, Robert Ghrist, and Danielle S. Bassett. "The importance of the whole: topological data analysis for the network neuroscientist." Network Neuroscience 3, no. 3 (2019): 656-673.


[Original] | [Mendeley]


## ToC

- [00. Abstract][00]
- [01. Intro][01]
	- [Figure 1][figure1]
- [02. When should we use topological data analysis?][02]
- [03. Pieces and parts of the simplicical complex][03]
	- [03.01. Chain groups and boudaries][0301]
	- [03.02. Homological algebra][0302]
- [04. Homology from complex to complex: persistebt homology][04]
	- [04.01. Filtrations][0401]
	- [04.02. Persistent homology][0402]
	- [04.03. Extracting topological feautres][0403]
- [05. Conclusion][05]


## 00. Abstract


## 01. Intro

###### 01 ¶01

**algebraic topology**

###### 01 ¶02

**neteork topology**


###### Figure 1

[![fig01][fig01]][fig01]

###### 01 ¶03

**persistent homology**

###### 01 ¶04

###### 01 ¶05


## 02. When should we use topological data analysis?

###### 02 ¶01

###### 02 ¶02


## 03. Pieces and parts of the simplicical complex

###### 03 ¶01

**simplicial complex**

unit of \(k + 1\) nodes is \(k\)-simplex

\(k\)-simplex  
nodes \(\{v_0, \cdots, v_k\}\)

rule:  
if \(s\) is simplex in \(K\) and \(s' \subseteq s\), then \(s' \in K\)

\(k\)-skeleton (\(X^k\)): collection of all cimplices w dim at most \(k\)

\(k\)-cycle: looped patterns of \(k\)-simplices

###### 03 ¶02

simplex dist

###### 03 ¶03

**face**: subset of a simplex  
e.g., if \(\{v_1, v_2, v_3\}\) is 2-simplex, it contains 1-simplex \(\{v_1, v_2\}\),  
where \(\{v_i, v_j\}\) is face of \(\{v_i, v_j, v_k\}\) 

###### Figure 2
[![fig02][fig02]][fig02]

### 03.01. Chain groups and boudaries

###### 03.01 ¶01

cavities w/i simplicial complexes as akin to bubbles under water

#### Box 1. From data to simplicial complex

###### box1 ¶01
<!-- There are multiple -->

**clique complex**

###### box1 ¶02
<!-- A second interesting -->

###### box1 ¶03
<!-- If the data -->


###### 03.01 ¶02
<!-- Let’s begin with -->

\(\text{#nodes} \times \text{#edges}\) binary mat (\(\partial_1\))

first / zeroth **chain group**s (\(C_1\), \(C_0\)), 1- / 0-chains

###### 03.01 ¶03
<!-- This matrix houses -->

\(\partial_1(C_1) \subseteq C_0 \)

###### 03.01 ¶04
<!-- Now we again -->


\[  \cdots \overset{\partial_{k+3}}{\longrightarrow} C_{k+2} \overset{\partial_{k+2}}{\longrightarrow} C_{k+1} \overset{\partial_{k+1}}{\longrightarrow} C_{k} \overset{\partial_{k}}{\longrightarrow} C_{k-1} \overset{\partial_{k-1}}{\longrightarrow} C_{k-2} \overset{\partial_{k-2}}{\longrightarrow} \cdots \]


###### Figure 3
[![fig03][fig03]][fig03]
###### Figure 4
[![fig04][fig04]][fig04]
### 03.02. Homological algebra
## 04. Homology from complex to complex: persistebt homology
### 04.01. Filtrations
###### Figure 5
[![fig05][fig05]][fig05]
### 04.02. Persistent homology
### 04.03. Extracting topological feautres
###### Figure 6
[![fig06][fig06]][fig06]
## 05. Conclusion

##
<!-- -------------------------------------------- -->

<!-- toc -->
[00]: #00_abstract
[01]: #01_intro
[figure1]: #figure1
[02]: #02_when_should_we_use_topological_data_analysis

<!-- ref -->
[Original]: 
[Mendenley]:
[ref01]: .

[simplicial homology]: https://en.wikipedia.org/wiki/Simplicial_homology

<!-- fig -->
[fig01]: https://www.mitpressjournals.org/na101/home/literatum/publisher/mit/journals/content/netn/2019/netn.2019.3.issue-3/netn_a_00073/20190710/images/large/00073f01c.jpeg
[fig02]: https://www.mitpressjournals.org/na101/home/literatum/publisher/mit/journals/content/netn/2019/netn.2019.3.issue-3/netn_a_00073/20190710/images/large/00073f02c.jpeg
[fig03]: https://www.mitpressjournals.org/na101/home/literatum/publisher/mit/journals/content/netn/2019/netn.2019.3.issue-3/netn_a_00073/20190710/images/large/00073f03c.jpeg
[fig04]: https://www.mitpressjournals.org/na101/home/literatum/publisher/mit/journals/content/netn/2019/netn.2019.3.issue-3/netn_a_00073/20190710/images/large/00073f04c.jpeg
[fig05]: https://www.mitpressjournals.org/na101/home/literatum/publisher/mit/journals/content/netn/2019/netn.2019.3.issue-3/netn_a_00073/20190710/images/large/00073f05c.jpeg
[fig06]: https://www.mitpressjournals.org/na101/home/literatum/publisher/mit/journals/content/netn/2019/netn.2019.3.issue-3/netn_a_00073/20190710/images/large/00073f06c.jpeg

<style type="text/css">
	img{width: 50%; float: right;}
</style>