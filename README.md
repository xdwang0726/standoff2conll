# BRAT STANDOFF2CONLL 2004

An extended version of the original Sampo Pyysalo's and aoldoni's conversion script that also supports conversion from brat-flavored standoff to the D. Roth and W. Yih CoNLL 2004 Relation Extractor training format.

This custom CONLL 2004 format is used to train the Stanford Relation Extractor model. An usage example can be seen in the https://github.com/aoldoni/tetre repository.


### USAGE
1. run the command targetting the folder with the annotated text (with the *.txt and *.ann files):  
  `./standoff2conll.py data/annotated/ --process ROTHANDYIH --tagset IOBES > conll04.tsv`

(Note: your annotated text should be clean without any extra spaces between sentences. 
if you have use regular expression to remove extra spaces
 	`a. [\n]{3,}`
	`b. [\d]+\t[\d]+[\t].*[\n]{3,}`)
 
### THE CONLL 2004 FORMAT

The format is described [here](http://cogcomp.cs.illinois.edu/page/resource_view/43) with an example [here](http://cogcomp.cs.illinois.edu/Data/ER/conll04.corp). 


### CUSTOM ENTITIES IN STANFORD RE TRAINING

By default Relation Extractor only accepts a few core entities, such as PEOPLE, ORGANISATION and LOCATION. If you attempt different entities you will see the following error:
```
Caused by: java.lang.RuntimeException: Cannot normalize ner tag Concept
	at edu.stanford.nlp.ie.machinereading.domains.roth.RothCONLL04Reader.getNormalizedNERTag(RothCONLL04Reader.java:85)
	at edu.stanford.nlp.ie.machinereading.domains.roth.RothCONLL04Reader.readSentence(RothCONLL04Reader.java:148)
	at edu.stanford.nlp.ie.machinereading.domains.roth.RothCONLL04Reader.read(RothCONLL04Reader.java:56)
	at edu.stanford.nlp.ie.machinereading.GenericDataSetReader.parse(GenericDataSetReader.java:132)
	... 3 more
```

To use your custom entities you have a few options:

1) Hard-code the new list of entities in the already hard-coded list inside the machine reading code, as per [this commit](https://github.com/aoldoni/stanford-corenlp/commit/ae6782266cb40629aefcecbab397da47f808abc3).

2) Use [this](https://github.com/aoldoni/stanford-corenlp/) fork I prepared of the Stanford CoreNLP. In this fork a new `possibleEntities` paremeter acceptes a comma separated list of entities for normalization.

3) Or wait until [support is added](https://github.com/stanfordnlp/CoreNLP/issues/359).

# LICENSE

Copyright (c) 2016, 2017 Alisson Oldoni, Sampo Pyysalo [MIT License](LICENSE)
