# Summary

The LFG Enhanced UD treebank of Polish is based on a corpus of LFG (Lexical Functional Grammar) syntactic structures generated by an LFG grammar of Polish, POLFIE, and manually disambiguated by human annotators.

# Introduction

The treebank consists of around 17,200 sentences (see the Data Split section for precise numbers).  Thanks to the richness of the original LFG representations, it makes heavy use of enhanced dependencies.  Secondary edges are used not only in representations of coordination (for shared dependents and shared governors), but also for various control-like constructions.

The annotation differs from (the release 2.1 of) the SZ UD treebank of Polish also in other respects, including the following:
* __Direct objects__ are understood here not as just any bare nominal required dependents of verbs, but as those dependents which passivise, i.e., which become subjects in the passive voice.  In the case of nominal direct objects, the standard `obj` relation is used, and in the case of clausal direct objects, the subtyped `ccomp:obj` is applied.
* Only dative required nominal dependents are understood as __indirect objects__.
* The three __masculine genders__ in Polish are represented via the language-specific `SubGender` feature (rather than `Animacy`).
* __Abbreviations__ are assigned parts of speech of their full forms.
* __Predicative complements__ of non-copular verbs are consistently marked as `xcomp`.
* Preposition + short pronoun contractions are __tokenised__ properly.
* A distinction is made between __interrogative and relative pronouns__.
* __Impersonal__ _-no/-to_ forms are correctly marked as verbs (rather than as adjectival passive participles).
* Impersonal uses of the so-called __reflexive marker__ _się_ are distinguished (as `expl:impers`).

# Data Split and Genres

19,597 sentences with their LFG syntactic structures form an input to the conversion.  Many of these are sentences with multiple possible LFG analyses, as well as accidental duplicates.  After conversion only unique UD structures are retained, i.e., a sentence may appear in the corpus a couple of times only with different dependency annotations.  As a result, the LFG Enhanced UD treebank contains 17,246 dependency trees (with 130,967 segments) for 17,190 different sentences.  (This should be contrasted with the SZ UD treebank of Polish, which contains repeated sentences with identical annotations.)

These 17,246 were split into training, development and test subcorpora in two stages.  First, for each sentence, it was checked whether this sentence occurs in the SZ UD treebank of Polish.  If it occurred in the training corpus there, it was also assigned – with all its dependency structures, if there were more than one – to the training subcorpus of the LFG Enhanced UD treebank.  Otherwise, if it was found in the SZ development corpus, it was assigned to the current development corpus.  Otherwise, if it occurred in the SZ test corpus, it was assigned to the current test corpus.  Altogether, 3502 (2594 + 439 + 469, respectively) dependency trees were pre-classified to the tree subcorpora this way.

Second, the remaining sentences were randomly added to the development and test subcorpora until each of these subcorpora contained more than 20\% of the whole corpus, in terms of both the number of dependency trees and the number of tokens.  The rest of the sentences were added to the training corpus.  This procedure results in the following split:
* training: 13,744 trees (104,750 tokens),
* development: 1745 trees (13,105 tokens),
* test: 1727 trees (13,112 tokens).

About 42.1% of sentences represent the fiction genre, 39.1% – news, 7.4\% – nonfiction, 7.3% – spoken, 3% – interactive Internet texts (forums, chatrooms, etc.), and there are also traces of static Internet pages (0.8%), academic style (0.3%) and legal texts (0.1%).  For each sentence, genre is explicitly given in a comment to this sentence.


# Acknowledgments

The original LFG corpus has been developed under the supervision of Agnieszka Patejuk (many thanks to the annotators!) and has been converted to UD by Adam Przepiórkowski, in collaboration with Agnieszka Patejuk.  Both the creation of the original LFG corpus and the conversion into UD have been partially supported by the Polish Ministry of Science and Higher Education within the CLARIN ERIC programme 2015–2018 (http://clarin.eu/).  The data, lemmata and original morphosyntactic tags come from the manually annotated subcorpus of the National Corpus of Polish (led by Adam Przepiórkowski; http://nkjp.pl/), whose development was financed by the Polish Ministry of Science and Higher Education in 2007–2011, and – to a lesser extent – from the corpus Polish language of the 1960s (http://clip.ipipan.waw.pl/PL196x).  Many thanks to Joakim Nivre and Dan Zeman for their infinite patience in answering a myriad of diverse UD-related questions during the development of this treebank.

## References

If you use this treebank, you are encouraged to cite this book:

Agnieszka Patejuk and Adam Przepiórkowski. “From Lexical Functional Grammar to Enhanced Universal Dependencies: Linguistically informed treebanks of Polish.” Institute of Computer Science, Polish Academy of Sciences, Warsaw, 2018.  Downloadable from http://nlp.ipipan.waw.pl/Bib/pat:prz:18:book.pdf.

    @Book{pat:prz:18:book,
      author =       {Agnieszka Patejuk and Adam Przepiórkowski},
      title =        {From {L}exical {F}unctional {G}rammar to Enhanced {U}niversal {D}ependencies: Linguistically informed treebanks of {P}olish},
      publisher =    {Institute of Computer Science, Polish Academy of Sciences},
      year =         2018,
      address =      {Warsaw},
      url =          {http://nlp.ipipan.waw.pl/Bib/pat:prz:18:book.pdf}}


# Changelog

* 2019-04-26 v2.4
  * When UPOS=INTJ (XPOS=interj), DEPREL/DEPS=discourse (instead of advmod)
* 2018-11-01 v2.3
  * Removed double EUD dependency in sentence train-8762
* 2018-07-01 v2.2
  * First official release
* 2018-02-20
  * First treebank data commit (to be released in v2.2)


# Metadata

<pre>
=== Machine-readable metadata (DO NOT REMOVE!) ================================
Data available since: UD v2.2
License: GNU GPL 3.0
Includes text: yes
Genre: fiction nonfiction news spoken social
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
