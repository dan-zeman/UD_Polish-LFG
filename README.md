# Summary

The LFG Enhanced UD treebank of Polish is based on a corpus of LFG (Lexical Functional Grammar) syntactic structures generated by an LFG grammar of Polish, POLFIE, and manually disambiguated by human annotators.

# Introduction

The treebank consists of around 17,200 sentences (see the Data Split section for precise numbers).  Thanks to richness of the original LFG representations, it makes heavy use of enhanced dependencies.  Secondary edges are used not only in representations of coordination (for shared dependents and shared governors), but also for various control-like constructions.

The annotation differs from the SZ UD treebank of Polish also in other respects, including the following:
* __Direct objects__ are understood here not as just any bare nominal required dependents of verbs, but as those dependents which passivise, i.e., which become subjects in the passive voice.  In the case of nominal direct objects, the standard `obj` relation is used, and in the case of clausal direct objects, the subtyped `ccomp:obj` is applied.
* Only dative required nominal dependents are understood as __indirect objects__.  
* The three __masculine genders__ in Polish are represented via the language-specific `SubGender` feature (rather than `Animacy`).
* __Abbreviations__ are assigned parts of speech of their full forms.
* __Predicative complements__ of non-copular verbs are consistently marked as `xcomp`.
* Preposition + short pronoun contractions are __tokenised__ properly.
* A distinction is made between __interrogative and relative pronouns__.
* __Impersonal__ _-no/-to_ forms are correctly marked as verbs (rather than as adjectival passive participles).
* Impersonal uses of the so-called __reflexive marker__ _się_ are distinguished (as `expl:impers`).

# Data Split

19,597 sentences with their LFG syntactic structures form an input to the conversion.  Many of these are sentences with multiple possible LFG analyses, as well as accidental duplicates.  After conversion only unique UD structures are retained, i.e., a sentence may appear in the corpus a couple of times only with different dependency annotations.  As a result, the LFG Enhanced UD treebank contains 17,246 dependency trees (with 130,967 segments) for 17,190 different sentences.  (This should be contrasted with the SZ UD treebank of Polish, which contains repeated sentences with identical annotations.)

These 17,246 were split into training, development and test subcorpora in two stages.  First, for each sentence, it was checked whether this sentence occurs in the SZ UD treebank of Polish.  If it occurred in the training corpus there, it was also assigned – with all its dependency structures, if there were more than one – to the training subcorpus of the LFG Enhanced UD treebank.  Otherwise, if it was found in the SZ development corpus, it was assigned to the current development corpus.  Otherwise, if it occurred in the SZ test corpus, it was assigned to the current test corpus.  Altogether, 3502 (2594 + 439 + 469, respectively) dependency trees were pre-classified to the tree subcorpora this way.  

Second, the remaining sentences were randomly added to the development and test subcorpora until each of these subcorpora contained more than 20\% of the whole corpus, in terms of both the number of dependency trees and the number of tokens.  The rest of the sentences were added to the training corpus.  This procedure results in the following split:
* training: 13,744 trees (104,750 tokens),
* development: 1745 trees (13,105 tokens),
* test: 1727 trees (13,112 tokens).


# Acknowledgments

The original LFG corpus has been developed under the supervision of Agnieszka Patejuk (many thanks to the annotators!) and has been converted to UD by Adam Przepiórkowski, in collaboration with Agnieszka Patejuk.  Both the creation of the original LFG corpus and the conversion into UD have been partially supported by the Polish Ministry of Science and Higher Education within the CLARIN ERIC programme 2015–2018 (http://clarin.eu/).  The data, lemmata and original morphosyntactic tags come from the manually annotated subcorpus of the National Corpus of Polish (led by Adam Przepiórkowski; http://nkjp.pl/), whose development was financed by the Polish Ministry of Science and Higher Education in 2007–2011.  Many thanks to Joakim Nivre and Dan Zeman for their infinite patience in answering a myriad of diverse UD-related questions during the development of this treebank.


## References

A citable description of this treebank is in progress.  Below are references to tools and resources that were used in the creation of the LFG Enhanced UD treebank of Polish.  For the time being, you may want to cite the 2015 publication “Parallel development of linguistic resources: Towards a structure bank of Polish”.

* Agnieszka Patejuk and Adam Przepiórkowski. “POLFIE: współczesna gramatyka formalna języka polskiego”. _Język Polski_, __XCVII__(1):48–64, 2017.
* Agnieszka Patejuk and Adam Przepiórkowski. “Parallel development of linguistic resources: Towards a structure bank of Polish”. _Prace Filologiczne_, __LXV__:255–270, 2015. 
* Adam Przepiórkowski, Mirosław Bańko, Rafał L. Górski, Barbara Lewandowska-Tomaszczyk, Marek Łaziński, and Piotr Pęzik. “National Corpus of Polish”. In Zygmunt Vetulani, editor, *Proceedings of the 5th Language & Technology Conference: Human Language Technologies as a Challenge for Computer Science and Linguistics*, pages 259–263, Poznań, Poland, 2011.


<pre>
=== Machine-readable metadata (DO NOT REMOVE!) ================================
Data available since: UD v2.2
License: GNU GPL 3.0
Includes text: yes
Genre: fiction nonfiction news legal academic spoken blog social
Lemmas: converted from manual
UPOS: converted from manual
XPOS: manual native
Features: converted from manual
Relations: converted from manual
Contributors: Patejuk, Agnieszka; Przepiórkowski, Adam
Contributing: elsewhere
Contact: aep@ipipan.waw.pl, adamp@ipipan.waw.pl
===============================================================================
</pre>
