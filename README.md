Content Models with Attitude
===============================================================

Christina Sauper      |  Aria Haghighi     | Regina Barzilay  
:--------------------:|:------------------:|:---------------------:
csauper@csail.mit.edu |  aria42@gmail.com  | regina@csail.mit.edu  

Abstract
--------

We present a probabilistic topic model for jointly identifying properties and
attributes of social media review snippets. Our model simultaneously learns a
set of properties of a product and captures aggregate user sentiments towards
these properties. This approach directly enables discovery of highly rated or
inconsistent properties of a product. Our model admits an efficient variational
mean-field inference algorithm which can be parallelized and run on large
snippet collections. We evaluate our model on a large corpus of snippets from
Yelp reviews to assess property and attribute prediction. We demonstrate that
it outperforms applicable baselines by a considerable margin.

Full Text: http://groups.csail.mit.edu/rbg/code/content_attitude/sauper-acl-11.pdf


Code
====

This code is available for research use only.

Running
-------

All main code is in `variational.rb`.  To run, you need a configuration file
(sample provided in `params`).  Then, simply run with:

`ruby variational.rb params`

Data
====

Each line of each data file should contain one snippet, optionally with parts
of speech (can be automatically tagged).  For example:

`Their_PRP$ bread_NN basket_NN was_VBD very_RB good_JJ`

Annotation
----------

Sample annotated files for testing are provided in `annotation/`.

`aspect.json`  
Labels for aspect identification, represented as a clustering over
snippets.

`words.json`  
Per-word labels for type of word:  

* 0 -- aspect  
* 1 -- sentiment  
* 2 -- background  

Collected via Amazon Mechanical Turk.

`sentiment_{train,test}`  
Annotation of snippet sentiments, positive or negative.  All neutral or
ambiguous snippets have been removed from this set.
