# BRAT STANDOFF2CONLL 2004

An extended version of the original Sampo Pyysalo's conversion script that also supports conversion from brat-flavored standoff to the D. Roth and W. Yih CoNLL 2004 Relation Extractor training format.

This custom CONLL 2004 format is used to train the Stanford Relation Extractor model. An usage example can be seen in the https://github.com/aoldoni/tetre repository.


### USAGE

1. Annotate your text in brat.

2. Run the command targetting the folder with the annotated folder:  
  `./standoff2conll.py data/input/training/annotated/  > data/input/training/transformed/documents.tsv`

3. It can not be used to train the Stanford Relation Extractor. NOTE: if you use custom entities/relations, please see

### THE CONLL 2004 FORMAT

The format is described [here](http://cogcomp.cs.illinois.edu/page/resource_view/43) with an example [here](http://cogcomp.cs.illinois.edu/Data/ER/conll04.corp). See an example below where the relation triplet Work_For(Bruno/Pusterla, Italian/Agricultural/Confederation) is denoted.

```
95	O	0	O	``	`	O	O	O
95	O	1	O	``	`	O	O	O
95	O	2	O	IN	If	O	O	O
95	O	3	O	PRP	it	O	O	O
95	O	4	O	VBZ	does	O	O	O
95	O	5	O	RB	not	O	O	O
95	O	6	O	NN	snow	O	O	O
95	O	7	O	,	COMMA	O	O	O
95	O	8	O	CC	and	O	O	O
95	O	9	O	DT	a	O	O	O
95	O	10	O	NN	lot	O	O	O
95	O	11	O	,	COMMA	O	O	O
95	O	12	O	IN	within	O	O	O
95	O	13	O	DT	this	O	O	O
95	O	14	O	NN	month	O	O	O
95	O	15	O	PRP	we	O	O	O
95	O	16	O	MD	will	O	O	O
95	O	17	O	VB	have	O	O	O
95	O	18	O	DT	no	O	O	O
95	O	19	O	NN	water	O	O	O
95	O	20	O	TO	to	O	O	O
95	O	21	O	VB	submerge	O	O	O
95	Other	22	O	CD/,/CD/NNS	150/COMMA/000/hectares	O	O	O
95	O	23	O	-LRB-	-LRB-	O	O	O
95	Other	24	O	CD/,/CD/NNS	370/COMMA/500/acres	O	O	O
95	O	25	O	-RRB-	-RRB-	O	O	O
95	O	26	O	IN	of	O	O	O
95	Other	27	O	NN	rice	O	O	O
95	O	28	O	,	COMMA	O	O	O
95	O	29	O	''	'	O	O	O
95	O	30	O	''	'	O	O	O
95	O	31	O	VBD	said	O	O	O
95	Peop	32	O	NNP/NNP	Bruno/Pusterla	O	O	O
95	O	33	O	,	COMMA	O	O	O
95	O	34	O	DT	a	O	O	O
95	O	35	O	JJ	top	O	O	O
95	O	36	O	NN	official	O	O	O
95	O	37	O	IN	of	O	O	O
95	O	38	O	DT	the	O	O	O
95	Org	39	O	JJ/NNP/NNP	Italian/Agricultural/Confederation	O	O	O
95	O	40	O	.	.	O	O	O

32	39	Work_For
```

### CUSTOM ENTITIES IN STANFORD RE TRAINING



# LICENSE

Copyright (c) 2016, 2017 Alisson Oldoni, Sampo Pyysalo [MIT License](LICENSE)