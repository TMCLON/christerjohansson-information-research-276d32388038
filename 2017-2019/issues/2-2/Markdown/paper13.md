---
title: "Stemming and N-gram matching for term conflation in Turkish texts"
---
#### Information Research, Vol. 2 No. 2, October 1996

* * *

<a name="paper13"></a>

# **Stemming and _N_-gram matching for term conflation in Turkish texts**

#### F. Çuna Ekmekçioglu, Michael F. Lynch, and [Peter Willett](mailto:p.willett@shef.ac.uk)  
Department of Information Studies  
University of Sheffield, Sheffield, UK

* * *

## Introduction

One of the main problems involved in the use of free text for indexing and retrieval is the variation in word forms that is likely to be encountered ([Lennon, et al., 1981](#lenn81)) The most common type of variations are spelling errors, alternative spellings, multi-word concepts, transliteration, affixes and abbreviations. One way to alleviate this problem is to use a conflation algorithm, a computational procedure that is designed to bring together words that are semantically related, and to reduce them to a single form for retrieval purposes. In this paper, we discuss the use of conflation techniques for Turkish text databases.

Turkish is a member of the south-western or Oghuz group of the Turkic languages, which also includes Turkmen, Azerbaijani or Azeri, Ghasghai and Gagauz ([Crystal, 1987](#crys87); [Lewis, 1991](#lewi91)). The Turkish language uses a Latin alphabet consisting of twenty-nine letters, of which eight are vowels and twenty-one are consonants. Unlike the main Indo-European languages (such as French and German), Turkish is an example of an _agglutinative language_, where words are a combination of several morphemes and suffixes. Here, words contain a root and suffixes are combined with this root in order to extend its meaning or to create other classes of words. In Turkish the process of adding one suffix to another can result in relatively long words, which often contain an amount of semantic information equivalent to a whole English phrase, clause or sentence. Due to this complex morphological structure, a single Turkish word can give rise to a very large number of variants, with a consequent need for effective conflation procedures if high recall is to be achieved in searches of Turkish text databases. Here, we summarise the principal results thus far of a project to develop and to evaluate such procedures; full details of the work are presented by [Ekmekçioglu _et al._ (1995](#ekme95), [1996](#ekme96)).

## Conflation techniques

Conflation algorithms can be broadly divided into two main classes: _stemming algorithms_, which are language dependent and which are designed to handle morphological variants, and _string-similarity algorithms_, which are (usually) language independent and which are designed to handle all types of variant.

### Stemming algorithms

[Lovins (1968)](#lovi68) defines a stemming algorithm as "a procedure to reduce all words with the same stem to a common form, usually by stripping each word of its derivational and inflectional suffixes". Stemming is generally effected by means of suffix dictionaries that contain lists of possible word endings, and this approach has been applied successfully to many different languages. It is, however, less applicable to an agglutinative language such as Turkish, which require a more detailed level of morphological analysis, where purely morphological techniques are required that remove suffixes from words according to their internal structure. They proceed from the left to the right of a word and first look in a lexicon for a root matching an initial substring of the word; they then use grammatical information stored in the lexical entry to determine what possible suffixes may follow. When a suffix matching a further substring is found subsequent grammatical information in the lexical entry for that suffix again determines what class of suffixes may follow. The stemming is successful if the end of the word can be reached by iteration of this process, and if the last suffix is one which may end a word. Examples of agglutinative languages for which morphological analysers have been developed include Finnish ([Koskenniemi, 1983](#kosk83), [J�ppinnen, _et al._, 1985](#japp85)) and Turkish ([Hankamer, 1984;](#hank84) [Solak. & Oflazer, 1993](#sola93); [Oflazer, 1994](#ofla94)).

### _N_-Grams

String-similarity approaches to conflation involve the system calculating a measure of similarity between an input query term and each of the distinct terms in the database. Those database terms that have a high similarity to a query term are then displayed to the user for possible inclusion in the query. _N-gram matching_ techniques are one of the most common of these approaches ([Freund & Willett, 1982](#freu82)). An _n_-gram is a set of _n_ consecutive characters extracted from a word. The main idea behind this approach is that, similar words will have a high proportion of _n_-grams in common. Typical values for _n_ are 2 or 3, these corresponding to the use of digrams or trigrams, respectively. For example, the word BILGISAYAR(computer) results in the generation of the digrams

*B, BI, IL, LG, GI, IS, SA, AY, YA, AR, R*

and the trigrams

**B, *BI, BIL, ILG, LGI, GIS, ISA, SAY, AYA, YAR, AR*, R**

where '*' denotes a padding space. There are _n_+1 such digrams and _n_+2 such trigrams in a word containing _n_ characters.

## Experimental details and results

### Stopword list and compression experiments

The two main objectives to be achieved in the first stage of the research were the development of a stopword list for Turkish and the evaluation of a stemming algorithm that takes account of the language's morphological structure. The frequencies of occurrence of the word types in the Turkish corpora were found to follow a typical Zipfian distribution, with a few word types providing a very high percentage of the observed tokens. The most frequently occurring words were mainly function words such as conjunctions, postpositions, pronouns, _etc_., and, these words were selected for inclusion in the stopword list. Furthermore, some of the large numbers of low-frequency Turkish words were morphological variants of very commonly occurring function words; these former words were also included in the stopword list.

The experiments used a a political news database that contained 376,187 Turkish word tokens; experiments with additional corpora are reported by [Ekmekçioglu _et al_. (1995)](#ekme95). A dictionary was created from this database, and the stopwords eliminated. The two-level morphological parser, PC-KIMMO ([Anthworth, 1990](#anth90)) and the PC-KIMMO description of the Turkish

* * *

<pre width="132">Corpus      Word       Word       Distinct  Distinct  Compression   
            Tokens     Types      Terms     Stems     (%)           

Turkish     376,187    49,479     41,370      6,363         84.6    

English     567,574    19,044     18,348    11,671          36.4    
</pre>

* * *

**Table 1**. Level of compression in the six Turkish text corpora and in the English text.

language developed at Bilkent University [11] were employed to parse the words in the Turkish dictionaries to obtain the stems. The results of this procedure were evaluated in terms of percentage of compression, _i.e._, in terms of the number of reduced words in the dictionary after stemming. For comparison, the results were compared with those obtained when [Porter's (1980)](#port80) stemming algorithm for English was applied to a newswire database containing 567,574 English word tokens.

An inspection of Table 1 shows that the English database yields a much smaller number of word types than does the Turkish database, despite the fact that the former contains many more word tokens. This indicates the much greater richness of the variations that occur in the Turkish language, a conclusion that is reinforced by consideration of the compression results. Employment of the Turkish stemming algorithm reduces the number of the words by no less than 84.6%, which indicates that stemming can bring about very substantial reductions in the numbers of word variants that must be processed in a Turkish free-text retrieval system. The compression figure for the English database is far smaller, at 36.4%, illustrating clearly the lower degree of morphological variation in English.

### Searching experiments

A dictionary was created containing all of the word types, and each word was then represented by its lists of constituent digrams or trigrams. A query term was represented by an analogous list and then matched against each of the _n_-gram lists in turn to find the similarity between the query word and the corresponding dictionary word, using the overlap similarity measure. The dictionary words were ranked in decreasing order of similarity and some fixed number, 10 in the experiments reported here, of the top-ranked words displayed as the possible variants of the search term.

The query words here were a random selection of 50 words from the dictionary, and the effectiveness of a search was measured by the mean number of relevant words retrieved when averaged over the entire set of query words, where a relevant word is taken to be one that appears to be a correct variant of the chosen query word. Conventionally, _n_-gram matching has been applied to unstemmed document and query words. However, we have also carried out experiments that involve both stemming and _n_-gram matching. Specifically, each of the query words was stemmed prior to the implementation of the _n_-gram procedures. The experiments thus involve unstemmed documents and queries (the simple _n_-gram runs), and unstemmed documents and stemmed queries (the combined experiments).

The results of the _n_-gram searches are shown in Table 2, which suggests that the trigrams perform better, irrespective of whether or not the query words are stemmed prior to the

* * *

<pre width="132">_n_-grams         Unstemmed         Stemmed      
                Query Words    Query Words     

Digrams              4.76            5.80      

Trigrams             5.42            6.08      
</pre>

* * *

**Table 2**. Mean number of relevant words (averaged over the entire set of query words) retrieved in the _n_-gram searching experiments with a cutoff of the top-10 words.

* * *

<pre width="132">                  Type-A    Type-B     
Stem search       8.56        7.33     
Combined search   8.48        6.08     
</pre>

* * *

**Table3**. Mean number of relevant words (averaged over the entire set of query words) using the stem search and the combined search (trigrams and stemming of query words).

generation of the _n-_gram lists. The Sign test was used to determine the significance of the difference in performance between pairs of different sets of different searches. The trigram searches are significantly better(_p_=0.00) than the digram searches when no stemming is applied but there is no significant difference when stemming is applied to the query words prior to the generation of the _n_-gram lists. However, these combined searches are significantly better (_p_=0.00 for both digrams and trigrams) than the searches that use unstemmed query words. We thus conclude that the best results are obtained by using trigrams derived from the stemmed query terms.

Further tests were carried out in which the best _n_-gram searches, _i.e._, those involving both trigrams and stemming, were compared with searches in which both the query words and the dictionary words were stemmed, which is the most common way of implementing stem-based retrieval. Such a comparison requires a way of equalising the outputs of the two types of search, and two approaches were taken to achieve this [5]. In both cases, a stem search is carried out for a query word and the number, _s_, of matching stems noted. In the first approach, referred to as Type-A searches, the corresponding _n_-gram search was evaluated using the top ranked _s_ words. In the second, Type-B, approach, if _s_<10 then 10-_s_ non-relevant words were added to the _s_ words that were retrieved; otherwise the number of relevant words was multiplied by 10/_s_. The Type-A searches are thus biased towards the stem searches while the Type-B searches are biased towards the _n_-gram searches.

The results of this comparison is shown in Table 3, where it will be seen that stemming is superior (but not significantly so; _p_=0.26 and _p_=0.07, respectively) to the combined search in both the Type-A and Type-B searches

## Conclusions

Our experiments show that the use of a stopword list and a stemming algorithm can bring about substantial reductions in the numbers of word variants encountered in searches of Turkish text databases; moreover, stemming appears to be superior, but not significantly so, to _n_-gram matching for conflating such variants. However, the experiments thus far have been limited in that have involved only single-word searches of a dictionary. The procedures are thus now being implemented in a version of the OKAPI ([Walker, 1988](#walk88)) retrieval system to carry out both conflated and non-conflated searches of Turkish databases. This work will be reported shortly.

## Acknowledgements

We thank Dr. Sandy Robertson and Dr. Kemal Oflazer for assistance and helpful discussions, and Dr. Hilmi Çelik, ulector of the Library of the Turkish Parliament, for the provision of the political news database used in this study.

## References

*   <a name="anth90">Anthworth, E.L</a>. (1990) _PC-KIMMO: A Two-level Processor for Morphological Analysis_. Dallas, Texas: Summer Institute of Linguistics.
*   <a name="crys87">Crystal, D</a>. (1987)_The Cambridge Encyclopaedia of Language_. Cambridge: Cambridge University Press.
*   <a name="ekme95">Ekmekçioglu, F</a>.Ç., Lynch, M. F. & Willett, P. (1995) Development and evaluation of conflation techniques for the implementation of a document retrieval system for Turkish text databases. _The New Review of Document and Text Management_, **1**, 131-146.
*   <a name="ekme96">Ekmekçioglu, F.</a>Ç., Lynch, M.F., Robertson, A.M., Sembok, T.M.T. & Willett, P. (1996) Comparison of _n_-gram matching and stemming for term conflation in English, Malay, and Turkish texts. _Text Technology_, **6**, 1-14.
*   <a name="freu82">Freund, G.E.</a> & Willett, P. (1982) Online identification of word variants and arbitrary truncation searching using a string similarity measure. _Information Technology: Research and Development_, **1**, 177-187.
*   <a name="hank84">Hankamer, J.</a> (1984) Turkish generative morphology and morphological parsing. Presented at the _Second International Conference on Turkish Linguistics_, Istanbul.
*   <a name="japp85">Jäppinnen, H.,</a> Niemisto, J. & Ylilammi, M. (1985) FINNTEXT - text retrieval system for an agglutinative language. _RIAO 85 Recherche d'Informations_, Grenoble: IMAG, 1985, 217-226
*   <a name="kosk83">Koskenniemi, K.</a> (1983) _Two-level Morphology: A General Computational Model for Word-Form Recognition and Production_. Publications of the Department of General Linguistics, 11\. Helsinki: University of Helsinki.
*   <a name="lenn81">Lennon, M.,</a> Peirce, D.S., Tarry, B.D. & Willett, P. (1981) An evaluation of some conflation algorithms for information retrieval. _Journal of Information Science_, **3**, 177-183.
*   <a name="lewi91">Lewis, G.L.</a> (1991) _Turkish Grammar._ Oxford: Oxford University Press, 1991.
*   <a name="lovi68">Lovins, J.B.</a> (1968) Development of a stemming algorithm. _Mechanical Translation and Computational Linguistics_, **11**, 1968, 22-31.
*   <a name="ofla94">Oflazer, K.</a> (1994) Two-level description of Turkish morphology. _Literary and Linguistic Computing_,**9**, 175-198.
*   <a name="port80">Porter, M.F.</a> (1980) An algorithm for suffix stripping. _Program_, **14**, 130-137.
*   <a name="sola93">Solak, A.</a> & Oflazer, K. (1993) Design and implementation of a spelling checker for Turkish. _Linguistic and Literary Computing,_ **8**, 1993.
*   <a name="walk88">Walker, S.</a> (1988) Improving subject access painlessly: recent work on the Okapi online catalogue projects. _Program_, **22**, 21-31.

* * *