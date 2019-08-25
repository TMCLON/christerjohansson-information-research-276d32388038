#### vol. 13 no. 3, September, 2008



# Extracting variant forms of chemical names for information retrieval



#### [Ari Pirkola](mailto:pirkola@cc.jyu.fi)  
Department of Information Studies, University of Tampere, 33014 Tampere, Finland

#### Abstract

> **Introduction.** Chemical substance names are long, complex and prone to variation. This study investigates the retrieval effects of the variation.  
> **Method.** A large set of acronyms and associated text parts was extracted from a subset of the Medline collection and used to construct a full name - acronym index. A longest common subsequence and statistics based technique (named FNV-Finder) was devised to identify MeSH term variants from the full name - acronym index for use as query terms in searching. The average number of variants for each MeSH term, the performance of the FNV-Finder technique and retrieval performance were evaluated.  
> **Results.** The average number of unique variants for each MeSH term denoting a chemical substance is 2.82\. The FNV-Finder technique achieved 95.0% recall and 97.1% precision. The retrieval experiments showed that the collection contains a substantial number of documents that contain only variant forms of the MeSH terms (and do not contain the MeSH terms or CAS registry numbers).  
> **Conclusions.** The selection of variant forms for queries from a collection would be very useful or even necessary in chemical name searching. Variant forms can be selected readily from the full name - acronym index either manually or automatically using the FNV-Finder technique.


## Introduction

We investigate the variation of _chemical substance names_ and the retrieval effects of the variation. Chemical names pose a special challenge in information retrieval since they typically are long and complex expressions, being thus prone to variation, which in turn may cause a decrease in retrieval performance due to a mismatch between query terms and index terms.

A new technique named _FNV-Finder_ (where FNV stands for Full Name Variant) was developed to automatically identify the variant forms. Articles discussing a given chemical substance often use a canonical pattern where a full name is followed by an acronym in parentheses, e.g., _N-methyl pyrrolidone (NMP)_. The FNV-Finder technique is based on the fact that different variant forms of the same full name share the same acronym. The acronym is used as a pivot to find the variants of the same name. We extracted all the canonical patterns from a subset of the Medline collection, i.e., TREC 2003 Genomics Track collection containing some 525, 000 documents ([Hersh and Bhupatiraju 2004](#hersh)). We constructed a full name-acronym index which contains the extracted acronyms and associated text parts and where the acronyms are arranged in an alphabetical order. The index allows an efficient means of identifying the full names of acronyms both manually and automatically. The FNV-Finder technique uses a similarity measure (longest common subsequence, LCS) between an acronym and string sequences associated with it in the full name-acronym index and statistical data contained in the full name-acronym index to identify the full names of acronyms and the variant forms of the same full name.

As test data we used a set of chemical acronyms and their MeSH (Medical Subject Headings) terms, for which variant forms were identified from the full name-acronym index manually and automatically using the FNV-Finder technique. Using these data we investigate the following research problems:

1.  What is the average number of variants for a MeSH term denoting a chemical substance?
2.  How to effectively identify automatically different variant forms of a MeSH term? For this research problem we devised the LCS and statistics based FNV-Finder technique, which identifies the variants from the full name-acronym index for use as query terms in chemical name searching.
3.  What are the recall and precision of the proposed FNV-Finder technique?
4.  Does chemical name searching benefit from using variant forms in queries?

The main contributions of this paper are: to present a novel technique (FNV-Finder) to identify chemical name variants from a collection, and to present evaluation results for the approach; to demonstrate how to effectively organize the full name-acronym patterns contained in the collection (the construction of the full name-acronym index); and to report the effects of chemical name variation in information retrieval.

## Methods and data

### Test collection and test words

The test collection used in the study was the TREC 2003 Genomics Track collection, which is a subset of the Medline collection. The test collection contains some 525,000 article abstracts, which were indexed between January 2002 and January 2003\. Medline's documents are indexed with the National Library of Medicine's [Medical Subject Headings (MeSH)](http://www.nlm.nih.gov/mesh/). Chemical names are also indexed with [Chemical Abstract Service registry numbers](http://www.cas.org/expertise/cascontent/registry/regsys.html).

A Medline record consists of several fields of which the fields TI (title), AB (abstract), MH (MeSH terms), and RN (Chemical Abstract Service Registry Number) were indexed for the retrieval experiments conducted in this study.

The full names of chemical acronyms in the [full name-acronym index](#fna) are often terms that are contained in the Medical Subject Headings vocabulary: they are either MeSH terms or so-called substance names, or the full names in the full name-acronym index are their variants. In this study, variation is considered from the viewpoint of the MeSH terms and the substance names. A MeSH term or substance name is regarded as a standard full name of an acronym while the full names that denote the same chemical substance as the MeSH term or substance name and that are similar to it but written differently are regarded as variant forms. For example, _hydroxyethyl methacrylate_ is a substance name and _hydroxyethylmethacrylate_ and _2-hydroxyethyl methacrylate_ are its variant forms. As can be seen, the latter two names are similar, but not identical, to _hydroxyethyl methacrylate_. Below are more examples of variant forms. (For simplicity, in this paper _MeSH term_ refers both to the actual MeSH terms and the substance names contained in the MeSH.)

From the viewpoint of the research problems examined in this study we differentiate between three types of names that denote a chemical substance: a MeSH term, its variant forms, and an acronym that refers to the MeSH term and the variant forms. We do not study orthographic variation (see below) but _lexical variation_. Here lexical variation means that the MeSH term and a variant form denote the same chemical substance and are similar, but there are differences in components, letters, or numbers. We can distinguish several types of variant cases: the MeSH term and its variant form have one or more common components but differ from each other in the number or the order of the components (e.g., MeSH term _inosine monophosphate_ and a variant form _inosine 5 monophosphate_); the components are written together (i.e., as a compound word) vs. the components are written separately (i.e., as a phrase) (e.g., MeSH term _carboxymethylcellulose_ and a variant form _carboxymethyl cellulose_); the corresponding components in the MeSH term and a variant form differ (typically) in one or two characters (e.g., MeSH term _1 methyl 2 pyrrolidinone_ and a variant form _1 methyl 2 pyrrolidone_); a component that appears in a variant may be an abbreviation of a component that appears in the MeSH term, or the other way around (e.g., MeSH term _methyl tert butyl ether_ and a variant form _methyl t butyl ether_). All these cases affect information retrieval. For example, it is obvious that query terms _carboxymethylcellulose_ (compound) and _carboxymethyl cellulose_ (phrase) give different retrieval results.

Since we examine lexical variation rather than orthographic variation we performed orthographic normalisation in documents, queries, and in the full name-acronym index: other characters than letters and numbers were replaced with spaces; case was normalised into lower case. As an example of orthographic normalisation, the substance name _N-Formylmethionine Leucyl-Phenylalanine_ was converted into a normalised form of _n formylmethionine leucyl phenylalanine_. In a retrieval phase, phrasal names were searched for using the ordered window proximity operator of the InQuery retrieval system ([Allan _et al_. 2000](#allan)) which was used as a test system in the retrieval experiments. The benefits of orthographic normalisation in information retrieval are obvious and it is commonly used in retrieval systems even though it may create ambiguity. However, in this study orthographic normalisation did not affect performance (the issue of wrong identifications by FNV-Finder is discussed in the Findings section).

We used a training set of fifty acronyms (see [Appendix 1](#app)) to devise the FNV-Finder technique and to set the thresholds to get the best possible results. The test acronyms were taken randomly from the full name-acronym index; every Nth acronym was selected iteratively until fifty substance name acronyms for which there were both MeSH terms and Registry Numbers were obtained. From the original set of 55 acronyms five were removed since there were no MeSH terms or Registry Numbers for them. In the case of ambiguous chemical acronyms having more than one MeSH term, the first term was selected for the tests.

The number of the test acronyms is relatively small because of the time-consuming manual identification of variants and [document relevance assessments](#relevance) , which are necessary for reliable results. It should be noted, however, that using this test data we are able to report statistically significant results in retrieval experiments.

As an aid in manual name identification we used printed reference books in chemistry and the National Library of Medicine's [ChemIDplus Lite](http://chem2.sis.nlm.nih.gov/chemidplus/chemidlite.jsp) Web service. In some (rare) cases it was not possible determine which string sequence in the full name-acronym index was acronym's full name. In these cases we looked at the document from where the text part was extracted and used document's text to determine the correct full name.

### Identification of full name variants


#### Constructing the full name-acronym index

The full name-acronym index was constructed by extracting from the Medline test collection all strings that consisted of letters, numbers or both letters and numbers and that were located in parentheses. For each such string a text part of the length of up to nine strings prior to it was also extracted. Strings inside parentheses containing other characters than letters or numbers were not included in the full name-acronym index. The first version of the index was cleaned: strings within parentheses that only contained numbers and associated text parts were removed.

To take an example of the extraction phase, consider a Medline record containing the following phrases: _end-stage renal disease (ESRD) were glomerulonephritis (26%)_, and, _with antithymocyte globulin (ATG) or orthoclone thymocyte 3 (OKT3)_. The strings _ESRD_, _ATG_, and _OKT3_ were included in the full name-acronym index while the string "26%", which does not contain letters and which contains a percentage sign was not included.

The index was arranged in an alphabetical order. The final index contains 479,882 lines. Most of the strings inside parentheses are not acronyms but noise in the context of this study. However, such strings do not play any role in variant identification and thus do not have any effects on the FNV-Finder effectiveness or retrieval results.

An _index entry_ contains all the extracted instances of an acronym _Ai_ (with _Ai_ denoting any acronym in the index) and the associated text parts. Let us take an example of an index entry. For the acronym MTBE part of the entry is as follows (here we only present seven lines, the full entry includes fifty-one lines):

> **entry: mtbe  
> **etbe t butyl alcohol tba methyl t butyl ether mtbe  
> mtbe from soil samples ab methyl tert butyl ether mtbe  
> 9 isopropyl alcohol ipa in methyl tert butyl ether mtbe  
> a procedure for determination of methyl tert butyl ether mtbe  
> an increase in levels of methyl tertiary butyl ether mtbe  
> and in bus exposures to methyl tertiary butyl ether mtbe  
> butyl ether in water ab methyl tert butyl ether mtbe

The string positions in a line _l_ are numbered from _s<sub>1</sub>(A<sub>i</sub>(l))_ (the first position) to _s<sub>n</sub>(A<sub>i</sub>(l))_ (the last position immediately left to the acronym).

For the fifty test acronyms, the number of lines in entries ranged from 1 to 214\. Overall, the fifty entries contained 1,595 lines. Manual identification of variants was done using all 1,595 lines (the first step of FNV-Finder also used all 1,595 lines).

#### FNV-Finder algorithm

FNV-Finder-based identification of acronyms' full name variants has six steps. Next we describe the FNV-Finder algorithm which is presented in [Appendix 2](#appendix). It is important to note that in steps one to five no difference is made between MeSH terms and variant forms. Only in the last step variant forms are separated from the MeSH terms.

In the _first step_, all lines in an entry that do not contain any of the components of a phrasal MeSH term, either as a separate string or as a string embedded in a compound word, are filtered out. Single word and compound word MeSH terms (e.g., _resiniferatoxin_) are divided into non-overlapping 6-grams (with the exception of the last n-gram which may contain more than 6 characters), which are used as a filter as in the case of phrasal MeSH terms. The experiments showed that this step removed most of the lines that did not contain a MeSH term or a variant form.

The _second step_ is based on the observation that chemical substance names only very rarely contain function words and other so-called stop words. Therefore, the rightmost stop word in each line and all strings to the left of the rightmost stop word are removed from an index entry. Also the acronyms are removed at this stage. The stop word list used was that of the retrieval system. As single letters are found in chemical names, they were removed from the list. The list was supplemented with the collection specific abbreviations _ti_ and _ab_ (_ti_ refers to title and _ab_ to abstract).

In the _third step_, the _longest common subsequence (LCS)_ technique (see for example [Pirkola _et al_. 2002](#pirkola)) is used to identify probable full names which we call _full name candidates_. The algorithm scans strings from right to left in each line to find a string that starts with the same letter as the acronym. If such string is found, it is marked as a _temporary first component (TFC)_ of a full name. Next LCS is computed for the acronym and the string sequence starting with the TFC and ending with _s<sub>n</sub>(A<sub>i</sub>(l))_. If LCS = |the number of characters in the acronym| the string sequence is marked as a full name candidate and is passed to the fifth step. The lines where full name candidates are not found are passed to the fourth step.

Numbers 0-100 as well as the strings _alpha, beta, gamma, tert, nalpha, d, l, n, p, r, s_, are often found as left components in chemical substance names (e.g., _1 6 diphenyl 1 3 5 hexatriene_), and if such string or a combination of such strings appears immediately left to the TFC it is included in the full name candidate.

In the experiments, the third step correctly identified most of the full names (note, at this stage they are still candidates). Below is an example of the second and third steps. The sample entry shown above is presented. The hyphen shows the location from which the left part of the entry was removed in the second step. The remaining part (called as a post-second-step entry in the following text) was processed in the third step. The asterisk indicates the TFC. As the example shows the LCS method identifies the full names _methyl tert butyl ether_ (MeSH term), _methyl t butyl ether_ and _methyl tertiary butyl ether_ (variant forms).

> **entry: mtbe  
> **etbe t butyl alcohol tba *methyl t butyl ether [LCS=4]  
> mtbe from soil samples ab- *methyl tert butyl ether [LCS=4]  
> 9 isopropyl alcohol ipa in- *methyl tert butyl ether [LCS=4]  
> a procedure for determination of- *methyl tert butyl ether [LCS=4]  
> an increase in levels of- *methyl tertiary butyl ether [LCS=4]  
> and in bus exposures to- *methyl tertiary butyl ether [LCS=4]  
> butyl ether in water ab- *methyl tert butyl ether [LCS=4]

The _fourth step_ handles the lines which the third step could not solve. A frequency-based _FNV indicator_ value is computed for each string in a post-second-step entry using a _FNV-Finder computation scheme_. The idea is that the string that appears frequently in an entry and that is the leftmost string among the frequent strings in a line is likely to be a start component of a full name.

The FNV-Finder computation scheme computes a FNV indicator value for the string _s<sub>k</sub>(A<sub>i</sub>_) as follows:

<div align="center">Fr(s<sub>k</sub>(A<sub>i</sub>)) / ln(N(A<sub>i</sub>))</div>

Fr(s<sub>k</sub>(A<sub>i</sub>)) = frequency of the string s<sub>k</sub> in the entry of an acronym A<sub>i</sub>.  
N(A<sub>i</sub>) = total number of strings in the entry of an acronym A<sub>i</sub>.

The frequency of _s<sub>k</sub>_ is divided by the total number of strings N in an entry to get figures that are in proper proportion between different entries. Similarly the natural logarithm (ln) in a denominator equalizes figures between different entries.

FNV indicator values are computed for each string in a post-second-step entry. The leftmost string whose value is above a set threshold (the value of 0.50 was used based on the training tests) is marked as a TFC. As in the third step, the whole string sequence from the TFC to the _s<sub>n</sub>(A<sub>i</sub>(l))_ is marked as a full name candidate. Similarly to the third step, numbers 0-100 and the strings _alpha, beta, gamma, tert, nalpha, d, l, n, p, r, s_, and combinations of them are included in the full name candidates (also in cases where the indicator value of such string is =< 0.50). The lines which the fourth step does not solve are rejected.

To take an example of full name identification based on the FNV-Finder computation scheme, consider the post-second-step entry of the acronym NMP:

> **entry: nmp  
> **n methyl 2 pyrrolidone [LCS=3]  
> 1 methyl 2 pyrrolidinone  
> n methyl pyrrolidone [LCS=3]  
> 1 methyl 2 pyrrolidone

The LCS method of the third step found the names _n methyl 2 pyrrolidone_ and _n methyl pyrrolidone_ (which are variant forms) in lines 1 and 3\. But it did not find the names _1 methyl 2 pyrrolidinone_ (MeSH term) in the second line nor _1 methyl 2 pyrrolidone_ (a variant form) in the fourth line, whereas the FNV-Finder computation scheme did so based on the indicator value of 0.74 (> 0.50) of the string _1_.

The _fifth step_ checks if there is a contradiction between the endings of the full name candidate and the MeSH term. In other words, this step checks whether they designate different types of chemical substances. The substance types are identified by means of a suffix list built in the study on the basis of a set of substance names extracted from the full name-acronym index. The list contains core word endings (n=21) typical of different types of substance names. The end parts of the MeSH term and the candidate are matched against the suffix list. If the end parts match different suffixes in the list (e.g., one is _amide_ and matches _-ide_, and the other is _amine_ and matches _-ine_), the candidate is rejected. Otherwise, the candidate is passed to the sixth step.

In the _sixth step_, the candidates are mapped to the MeSH terms to see if they are MeSH terms or variants. A full match indicates a MeSH term while a mismatch indicates a variant form.

## Evaluation

FNV-Finder effectiveness (research problem three) was evaluated using the measures of _recall_ and _precision_. In both cases we consider _unique_ variants (as opposed to variant occurrences). Recall is defined as the proportion of variants FNV-Finder identified correctly from the full name-acronym index to intellectually identified variants from the full name-acronym index. Recall:

> |Correct variants identified by FNV-Finder| / |Intellectually identified (correct) variants|

The intellectually identified variants thus constitute a recall base for variants identified by FNV-Finder. A full match between a FNV-Finder variant and an intellectually identified variant is considered a correct identification. A partial match and a mismatch are considered wrong identifications.

Precision is defined as the proportion of correctly identified variants by FNV-Finder among all entities FNV-Finder identified as variants. Precision:

> |Correct variants identified by FNV-Finder| / |All entities identified by FNV-Finder|

In this study, a _relevant document_ is defined as a document that contains at least one of the following items that denote the chemical substance in question: the MeSH term, the Chemical Abstracts Service registry number, a variant form. In retrieval experiments (research problem four) we ran the following three queries:

> _MeSH+Registry Number (hereafter, RN)_. Baseline. These queries (n=50) contained the MeSH terms and registry numbers, and they serve as baseline for the following test queries. For each acronym, they retrieved documents that contained the MeSH term or the registry number (or both of these). By definition, all the documents retrieved by MeSH+RN queries are relevant documents.  
>   
> _MeSH+RN+manual-variant_. These queries (n=50) contained the MeSH terms, registry numbers, and the manually identified variants. For each acronym, they retrieved documents that contained at least one of the following items: the MeSH term, the registry number, at least one of the manually identified variants of the MeSH term. The substance names selected manually from the full name-acronym index were all correct names and these queries were expected to retrieve only relevant documents (see below for relevance assessments).  
>   
> _MeSH+RN+automatic-variant_. These queries (n=50) contained the MeSH terms, registry numbers, and the variant forms identified by the FNV-Finder technique. For each acronym, they retrieved documents that contained at least one of the following items: the MeSH term, the registry number, at least one of the automatically identified variants of the MeSH term. Due to the automatically identified variant forms these queries retrieved also irrelevant documents.

We computed recall for MeSH+RN, MeSH+RN+manual-variant and MeSH+RN+automatic-variant queries, and precision for MeSH+RN+automatic-variant queries. These measures provide an answer to the research question whether, and to what extent, substance name searching benefits from using variant forms.

<a name="relevance">The relevance</a> of the documents containing only variant forms was assessed, firstly, to ensure that the manually identified variants retrieved only relevant documents, so that reliable recall values are obtained for MeSH+RN+manual-variant queries, and secondly, to compute recall and precision for MeSH+RN+automatic-variant queries.

The documents retrieved by the MeSH+RN+manual-variant queries constitute a recall base for the 50 queries. We are aware that the recall base is not complete, in particular due to the synonyms of MeSH terms. Therefore, we measure _relative recall_, in other words, recall relative to the set of known relevant documents, i.e., documents retrieved by MeSH+RN+manual-variant queries. (By the term _synonym_ we mean a term that designates the same chemical substance as the MeSH term but is dissimilar to it.)

A chemical name may be embedded in another, longer name. Therefore prior to the runs we checked the MeSH and ChemIDplus Lite databases to see which MeSH terms and variants in our data appeared in longer names. For such terms and variants we constructed a Boolean negation-based (InQuery's #bandnot-operator) query which excluded wrong names from the results. It should be noted that this type of query modification is not a feature of FNV-Finder based retrieval, but to obtain good results, modification is necessary in many cases. A drawback of this approach that some relevant documents may be lost. However, we analysed a sample set of such documents, and the analysis results suggest that only a fraction of relevant documents are lost.

## Findings

Table 1 presents the results of the first research problem, i.e., the frequency of variant forms. It can be seen that the average number of unique variants per a MeSH term is 2.82.

Table 2 shows the distribution of the variants between the 50 MeSH terms. The MeSH terms were divided into groups on the basis of the number of variants for each term. The left column shows the cardinality of a MeSH term group, and the right column the number of variants in a group. Table 2 shows that out of the 50 MeSH terms 39 have variants. 32 terms have 1-4 variants. One term has 10, one has 13, and one (_n formylmethionine leucyl phenylalanine_) has even 18 variants. These three terms with many variants were long terms. Of the 11 terms that did not have variants 10 were single words, compound words, or phrases with only two components. Thus, the results suggest a general trend: the longer a MeSH term is the more variant forms it has.

Table 3 reports the results of the FNV-Finder effectiveness experiments. It can be seen that FNV-Finder performed very well - it achieved 95.0% recall and 97.1% precision. These figures indicate that there were only a few variant forms that FNV-Finder could not identify, and only a few wrong identifications.

Table 4 reports the results of the retrieval experiments. As shown, MeSH+RN queries retrieved 4,110 documents. MeSH+RN+manual-variant queries retrieved 4,468 documents, and MeSH+RN+automatic-variant queries retrieved 4,456 _relevant_ documents. For MeSH+RN+manual-variant queries the difference (third column) is 358 documents. This means that - for the 50 queries - the collection contains 358 documents that contain only variant forms (and do not contain the MeSH terms or RNs). For MeSH+RN+automatic-variant queries the difference is 346 documents. For MeSH+RN+manual-variant queries we selected only correct variants, and all the retrieved documents were relevant.

Both for MeSH+RN+manual-variant and MeSH+RN+automatic-variant queries recall was improved (with respect to MeSH+RN queries) for 29 queries out of the 50 queries. The statistical significance was analysed by one-tailed non-parametric Wilcoxon signed rank test. For both query types the results were statistically significant at the level of p < 0.0001.

MeSH+RN+automatic-variant queries yield a high precision, i.e., 99.8%. They retrieved 4,467 documents, of which 11 were irrelevant documents. In the case of an ambiguous acronym GDP (_guanosine diphosphate_ in our data) FNV-Finder gave a wrong name _geranyl diphosphate_, and all the irrelevant documents dealt with this substance. Other wrong identifications by FNV-Finder were too short and too long sequences, but they did not affect retrieval results. In particular short sequences may be useful query terms though sometimes their use may decrease precision.

<table style="border: medium solid rgb(153, 245, 251); font-size: smaller; font-style: normal; font-family: verdana,geneva,arial,helvetica,sans-serif; background-color: rgb(253, 255, 221);" align="center" border="1" cellpadding="5" cellspacing="0" width="60%"><caption align="bottom">  
**Table 1\. The frequency of variants.**</caption>

<tbody>

<tr>

<th>Condition</th>

<th>Number/Average Number</th>

</tr>

<tr>

<td align="left">Number of MeSH terms</td>

<td align="center">50</td>

</tr>

<tr>

<td align="left">Number of unique variants</td>

<td align="center">141</td>

</tr>

<tr>

<td align="left">Number of unique variants per a MeSH term</td>

<td align="center">2.82</td>

</tr>

</tbody>

</table>

<table style="border: medium solid rgb(153, 245, 251); font-size: smaller; font-style: normal; font-family: verdana,geneva,arial,helvetica,sans-serif; background-color: rgb(253, 255, 221);" align="center" border="1" cellpadding="5" cellspacing="0" width="60%"><caption align="bottom">  
**Table 2\. Distribution of variants between MeSH terms.**</caption>

<tbody>

<tr>

<th>Number of MeSH terms in a group</th>

<th>Number of variants</th>

</tr>

<tr>

<td align="center">11</td>

<td align="center">0</td>

</tr>

<tr>

<td align="center">11</td>

<td align="center">1</td>

</tr>

<tr>

<td align="center">8</td>

<td align="center">2</td>

</tr>

<tr>

<td align="center">6</td>

<td align="center">3</td>

</tr>

<tr>

<td align="center">7</td>

<td align="center">4</td>

</tr>

<tr>

<td align="center">2</td>

<td align="center">5</td>

</tr>

<tr>

<td align="center">1</td>

<td align="center">8</td>

</tr>

<tr>

<td align="center">1</td>

<td align="center">9</td>

</tr>

<tr>

<td align="center">1</td>

<td align="center">10</td>

</tr>

<tr>

<td align="center">1</td>

<td align="center">13</td>

</tr>

<tr>

<td align="center">1</td>

<td align="center">18</td>

</tr>

</tbody>

</table>

<table style="border: medium solid rgb(153, 245, 251); font-size: smaller; font-style: normal; font-family: verdana,geneva,arial,helvetica,sans-serif; background-color: rgb(253, 255, 221);" align="center" border="1" cellpadding="10" cellspacing="0" width="60%"><caption align="bottom">  
**Table 3\. FNV-Finder effectiveness.**</caption>

<tbody>

<tr>

<th>Recall/Number of instances</th>

<th>Recall%</th>

</tr>

<tr>

<td align="center">134/141</td>

<td align="center">95.0</td>

</tr>

<tr>

<th>Precision/Number of instances</th>

<th>Precision%</th>

</tr>

<tr>

<td align="center">134/138</td>

<td align="center">97.1</td>

</tr>

</tbody>

</table>

<table style="border: medium solid rgb(153, 245, 251); font-size: smaller; font-style: normal; font-family: verdana,geneva,arial,helvetica,sans-serif; background-color: rgb(253, 255, 221);" align="center" border="1" cellpadding="10" cellspacing="0" width="80%"><caption align="bottom">  
**Table 4\. Retrieval performance of test queries.**</caption>

<tbody>

<tr>

<th>Query type n=50</th>

<th>Relevant Retrieved</th>

<th>2-1 / 3-1</th>

<th>Recall%</th>

<th>All Docs. Retrieved</th>

<th>Precision%</th>

</tr>

<tr>

<td align="left">1.MeSH+RN, baseline</td>

<td align="center">4110</td>

<td align="center">-</td>

<td align="center">92.0</td>

<td align="center">4110</td>

<td align="center">(100)</td>

</tr>

<tr>

<td align="left">2.MeSH+RN+manual-variant</td>

<td align="center">4468</td>

<td align="center">358</td>

<td align="center">100.0</td>

<td align="center">4468</td>

<td align="center">(100)</td>

</tr>

<tr>

<td align="left">3.MeSH+RN+automatic-variant</td>

<td align="center">4456</td>

<td align="center">346</td>

<td align="center">99.7</td>

<td align="center">4467</td>

<td align="center">99.8</td>

</tr>

</tbody>

</table>

## Related work

Larkey _et al_. ([2000](#larkey)) extracted from the Web a large collection of acronyms and their expansions (full names, definitions). They developed and evaluated several methods to extract acronyms' expansions. The corpus of the acronyms and expansions built on the basis of the best method was comparable to a high-quality hand-crafted Web site providing acronyms and expansions. Other pattern matching methods for extracting the full names of acronyms are presented in ([Schwartz and Hearst 2003](#schwartz); [Terada _et al_. 2004](#terada); and [Yu _et al_. 2002](#yu)).

Liu and Friedman ([2003](#liu)) developed a statistics-based method that associates abbreviations with their expansions. For example, the acronym ER is linked to the expansion _estrogen receptor_ in a text containing a parenthetical expression _estrogen receptor (ER)_. Text parts containing parenthetical expressions were first extracted from documents. Potential collocations were then generated and their frequencies were computed. The method uses the number of elements in a potential collocation and the ratios of the frequencies of potential collocations to eliminate words co-occurring by chance. For example, for _include pneumonia_ versus _pneumonia_ the frequency ratio is low, and _include pneumonia_ is eliminated. The method achieved 96.3% precision and 88.5% recall.

The FNV-Finder technique proposed in this paper differs from the above studies in that it identifies variant forms of the same name. The above studies focused on the question of the demarcation of the full name (expansion) boundaries in text.

It seems that chemical structure and substructure searching (e.g., [Willett 2000](#willett)) has been studied more than chemical name searching which seems to be a relatively unexplored area. Research on chemical name processing started several decades ago (see for example, [Vander Stouw _et al._ 1976)](#vander). However, there are few studies that have looked at how different techniques and factors affect retrieval performance. [Wren (2006)](#wren) used a first-order Markov Model to evaluate its ability to recognize chemical terms and reject non-chemical terms. The method achieved 93% recall and 99% precision. Based on the results of a small scale information retrieval experiment the researcher concluded that chemical name variation affects information retrieval. This is in agreement with the results of this study.

Luque Ruiz _et al_. ([1996](#luque) )developed an approximate string matching algorithm for repairing lexical errors in inorganic chemical names. The National Library of Medicine has several powerful tools to process biological texts ([Aronson 1994](#aronson); [Wilbur _et al._ 1999](#wilbur)). Lexical Variant Generator and MetaMap generate lexical variants for words appearing in texts. Wilbur _et al_. ([1999](#wilbur)) explored the problem of recognizing chemical terms and tested three methods: a lexical method where chemical terms were analysed into their constituent chemical morphemes, and two statistical methods based on the Bayesian classifier. The evaluation results showed that one of the statistical methods achieved the best results, an overall classification accuracy of 97%.

## Discussion and conclusions

We found in this study that the average number of unique variants for a chemical MeSH term is 2.82\. The retrieval experiments showed that the collection contains a substantial number of documents that contain only MeSH term variants (and do not contain the MeSH terms or RNs). The FNV-Finder technique effectively identified variant forms, and it achieved a high recall and precision. The findings of the retrieval experiments are in agreement with the FNV-Finder effectiveness experiments. The use of the variant forms identified by the FNV-Finder technique improved the recall of queries with respect to the recall of queries that only contained MeSH terms and RNs, and only slightly decreased precision.

MeSH and the Chemical Abstracts Service registry number system are the main terminological resources in chemical name searching. However, in exhaustive retrieval where the aim is to retrieve a large set of documents discussing a given chemical substance, as well as some other retrieval situations, the selection of additional names (variant forms) for queries either manually from a full name-acronym index constructed from a collection or automatically using the FNV-Finder technique would be very useful or even necessary.

It seems that the proposed FNV-Finder technique could be used effectively for name variant identification in any domain where names are expressed using the full name - acronym pattern. Naturally, the domain-specific components of the technique (e.g., suffix lists) need to be constructed according to the selected domain. The proposed technique could also be used in other areas than information retrieval (e.g., in information extraction), and for other languages than English. The next step in the FNV-Finder research will be the application of the technique in the Web environment. We have crawled large amount of data from the Web which will be used to construct Web based full name-acronym indexes. In addition to English, we plan to construct Web based full name-acronym indexes for French, German, and Spanish. These will be used to identify the full names of chemical acronyms in Web pages, and also other domains will be investigated. We would also like to investigate whether the technique could be applied in the area of converting chemical names into structures.

## Acknowledgements

This research was funded by the Academy of Finland (project names _NLP-based information retrieval systems for the biological literature_ and _Focused retrieval of Web documents_ ).

The InQuery search engine was provided by the Center for Intelligent Information Retrieval at the University of Massachusetts.

## References

*   <a id="allan" name="allan"></a>Allan, J., Connell, M.E., Croft, W.B., Feng, F.-F, Fisher, D. & Li, X. (2000). [InQuery and TREC-9](http://www.webcitation.org/5a2pwybjy). In _Proceedings of the Ninth Text REtrieval Conference (TREC-9)_. (pp. 551-600). Gaithersburg, MD: National Institute of Standards and Technology. (NIST Special Publication 500-249) Retrieved 13 August, 2008 from http://trec.nist.gov/pubs/trec9/papers/umass-trec9.pdf (Archived by WebCite® at http://www.webcitation.org/5a2pwybjy)
*   <a id="aronson" name="aronson"></a>Aronson, A.R. (1994). [_Comparison of LVG and MetaMap functionality_](http://www.webcitation.org/5a2qR12a7). Bethesda, MD: Lister Hill National Center for Biomedical Communications. Retrieved 13 August, 2008 from http://skr.nlm.nih.gov/papers/references/LVG-MetaMap.comparison.pdf (Archived by WebCite® at http://www.webcitation.org/5a2qR12a7)
*   <a id="hersh" name="hersh"></a>Hersh, W. & Bhupatiraju, R.T. (2004). [TREC genomics track overview](http://www.webcitation.org/5a2qzVCvD). In _Proceedings of the Twelfth Text Retrieval Conference (TREC-2003)_, (pp. 14-23). Gaithersburg, MD: National Institute of Standards and Technology. (NIST Special Publication 500-255) Retrieved 13 August, 2008 from http://trec.nist.gov/pubs/trec12/papers/GENOMICS.OVERVIEW3.pdf (Archived by WebCite® at http://www.webcitation.org/5a2qzVCvD)
*   <a id="larkey" name="larkey"></a>Larkey, L., Ogilvie, P., Price, A. & Tamilio, B. (2000). Acrophile: an automated acronym extractor and server. In _Proceedings of the ACM Fifth International Conference on Digital Libraries, DL '00, Dallas TX._ (pp. 205-214). New York, NY: ACM Press.
*   <a id="liu" name="liu"></a>Liu, H. & Friedman, C. (2003). Mining terminological knowledge in large biomedical corpora. In Russ B Altman, A Keith Dunker, Lawrence Hunter, Tiffany A Jung & Teri E Klein (Eds.). _Proceedings of the 8th Pacific Symposium on Biocomputing (PSB 2003), Lihue, Hawaii._ (pp. 415-426). Singapore: World Scientific Publishing Co.
*   <a id="luque" name="luque"></a>Luque Ruiz, I., Cruz Soto, J. L. & Gómez-Nieto, M. A. (1996). Error detection, recovery, and repair in the translation of inorganic nomenclatures. 2: a proposed strategy. _Journal of Chemical Information and Computer Sciences_, **36**(1), 16-24.
*   <a id="pirkola" name="pirkola"></a>Pirkola, A., Keskustalo, H., Leppänen, E. , Känsälä, A.-P. & Järvelin, K. (2002). [Targeted s-gram matching: a novel n-gram matching technique for cross- and monolingual word form variants](http://informationr.net/ir/7-2/paper126.html). _Information Research_, **7**(2), paper 126\. Retrieved 13 August, 2008 from http://informationr.net/ir/7-2/paper126.html (Archived by WebCite® at http://www.webcitation.org/5a2sJHoaw)
*   <a id="schwartz" name="schwartz"></a>Schwartz, A. & Hearst, M. (2003). [A simple algorithm for identifying abbrevation definitions in biomedical texts](http://www.webcitation.org/5a2slmvxP). In Russ B Altman, A Keith Dunker, Lawrence Hunter, Tiffany A Jung & Teri E Klein (Eds.). _Proceedings of the 8th Pacific Symposium on Biocomputing (PSB 2003), Lihue, Hawaii._ Singapore: World Scientific Publishing Co. Retrieved 13 August, 2008 from http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.13.2481&rep=rep1&type=pdf (Archived by WebCite® at http://www.webcitation.org/5a2slmvxP)
*   <a id="terada" name="terada"></a>Terada, A., Tokunaga, T. & Tanaka, H. (2004). Automatic expansion of abbrevations by using context and character information. _Information Processing and Management_, **40**(1), 31-45.
*   <a id="vander" name="vander"></a>Vander Stouw, G.G., Gustafson, C., Rule, J.D. & Watson, C.E. (1976). The Chemical Abstracts Service chemical registry system. IV: use of the registry system to support the preparation of index nomenclature. _Journal of Chemical Information and Computer Sciences_, **16**(4), 213-218.
*   <a id="wilbur" name="wilbur"></a>Wilbur, W.J., Hazard, G.F., Divita, G., Mork, J.G., Aronson, A.R. & Browne, A.C. (1999). [Analysis of biomedical text for chemical names: a comparison of three methods](http://www.webcitation.org/5a2t0w0BE). _Proceedings of the AMIA Annual Symposium_, (pp. 176-180). Bethesda, MD: American Medical Informatics Association. Retrieved 13 August, 2008 from http://skr.nlm.nih.gov/papers/references/chemicals.pdf (Archived by WebCite® at http://www.webcitation.org/5a2t0w0BE)
*   <a id="willett" name="willett"></a>Willett, P. (2000). [Textual and chemical information processing: different domains but similar algorithms](http://informationr.net/ir/5-2/paper69.html). _Information Research_, **5**(2), paper 69\. Retrieved 25 July, 2007 from http://informationr.net/ir/5-2/paper69.html (Archived by WebCite® at http://www.webcitation.org/5a2tL872j)
*   <a id="wren" name="wren"></a>Wren, J.D. (2006). A scalable machine-learning approach to recognize chemical names within large text databases. _BMC Bioinformatics_, **7**(Suppl 2): S3.
*   <a id="yu" name="yu"></a>Yu, H., Hatzivassiloglou, V., Rzhetsky, A. & Wilbur, W.J. (2002). Automatically identifying gene/protein terms in MEDLINE abstracts. _Journal of Biomedical Informatics_, **35**, 322-330\.



## Appendix 1 - Training data for FNV-Finder

<table width="90%" border="1" cellspacing="0" cellpadding="3" align="center" style="border-right: #99f5fb solid; border-top: #99f5fb solid; font-size: smaller; border-left: #99f5fb solid; border-bottom: #99f5fb solid; font-style: normal; font-family: verdana, geneva, arial, helvetica, sans-serif; background-color: #fdffdd">

<tbody>

<tr>

<th>Acronym</th>

<th>MeSH term/  
Substance name</th>

<th>Variant forms  
in the FN-A index</th>

</tr>

<tr>

<td valign="top">adomet</td>

<td valign="top">s adenosylmethionine</td>

<td valign="top">adenosyl methionine;  
s adenosyl l methionine</td>

</tr>

<tr>

<td valign="top">adpr</td>

<td valign="top">adenosine diphosphate ribose</td>

<td valign="top">adenosine 5 diphosphoribose;  
adp ribose</td>

</tr>

<tr>

<td valign="top">aibn</td>

<td valign="top">azobis isobutyronitrile</td>

<td valign="top">2 2 azobis isobutyronitrile;  
2 2 azobisisobutyronitrile</td>

</tr>

<tr>

<td valign="top">alum</td>

<td valign="top">aluminum hydroxide</td>

<td valign="top">aluminium hydroxide</td>

</tr>

<tr>

<td valign="top">ampt</td>

<td valign="top">alpha methyltyrosine</td>

<td valign="top">alpha methyl p tyrosine;  
alpha methyl para tyrosine;  
alpha methylpara tyrosine</td>

</tr>

<tr>

<td valign="top">ap4a</td>

<td valign="top">diadenosine tetraphosphate</td>

<td valign="top">p 1 p 4 di adenosine 5 tetraphosphate</td>

</tr>

<tr>

<td valign="top">azttp</td>

<td valign="top">3 azido 3 deoxythymidine 5 triphosphate</td>

<td valign="top">azt triphosphate</td>

</tr>

<tr>

<td valign="top">bbp</td>

<td valign="top">butylbenzyl phthalate</td>

<td valign="top">benzyl butyl phthalate;  
benzylbutyl phthalate;  
butyl benzyl phthalate;  
butylbenzylphthalate</td>

</tr>

<tr>

<td valign="top">bche</td>

<td valign="top">butyrylcholinesterase</td>

<td valign="top">butyrylcholine esterase</td>

</tr>

<tr>

<td valign="top">cccp</td>

<td valign="top">carbonyl cyanide m chlorophenyl hydrazone</td>

<td valign="top">carbonyl cyanide 3 chlorophenylhydrazone;  
carbonyl cyanide m chlorophenylhydrazone;  
carbonyl cyanide m cholorophenyl hydrazone;  
carbonylcyanide m chlorophenyl hydrazone;  
carbonylcyanide m chlorophenylhydrazone</td>

</tr>

<tr>

<td valign="top">dcc</td>

<td valign="top">dicyclohexylcarbodiimide</td>

<td valign="top">dicyclohexyl carbodiimide;  
n n dicyclohexylcarbodiimide</td>

</tr>

<tr>

<td valign="top">dep</td>

<td valign="top">diethyl phthalate</td>

<td valign="top">diethylphthalate</td>

</tr>

<tr>

<td valign="top">dmn</td>

<td valign="top">dimethylnitrosamine</td>

<td valign="top">n nitrosodimethylamine</td>

</tr>

<tr>

<td valign="top">dmpo</td>

<td valign="top">5 5 dimethyl 1 pyrroline 1 oxide</td>

<td valign="top">5 5 dimethyl 1 pyrroline n oxide;  
5 5 dimethyl pyrroline n oxide;  
5 5 dimethylpryrroline n oxide;  
dimethyl pyrroline n oxide</td>

</tr>

<tr>

<td valign="top">emate</td>

<td valign="top">estrone 3 o sulfamate</td>

<td valign="top">oestrone 3 sulphamate</td>

</tr>

<tr>

<td valign="top">galn</td>

<td valign="top">galactosamine</td>

<td valign="top">d galactosamine</td>

</tr>

<tr>

<td valign="top">gsno</td>

<td valign="top">s nitrosoglutathione</td>

<td valign="top">nitrosoglutathione;  
s nitroso glutathione;  
s nitroso l glutathione</td>

</tr>

<tr>

<td valign="top">hba</td>

<td valign="top">4 hydroxybenzoic acid</td>

<td valign="top">p hydroxybenzoate;  
p hydroxybenzoic acid</td>

</tr>

<tr>

<td valign="top">hdi</td>

<td valign="top">1 6 hexamethylene diisocyanate</td>

<td valign="top">hexamethylene diisocyanate;  
hexane diisocyanate</td>

</tr>

<tr>

<td valign="top">iptg</td>

<td valign="top">isopropyl thiogalactoside</td>

<td valign="top">isopropyl beta d thiogalactopyranoside;  
isopropyl beta d thiogalactoside;  
isopropylthiogalactoside</td>

</tr>

<tr>

<td valign="top">kic</td>

<td valign="top">alpha ketoisocaproic acid</td>

<td valign="top">2 ketoisocaproic acid;  
alpha ketoisocaproate</td>

</tr>

<tr>

<td valign="top">kyna</td>

<td valign="top">kynurenic acid</td>

<td valign="top">kynurenate</td>

</tr>

<tr>

<td valign="top">m6g</td>

<td valign="top">morphine 6 glucuronide</td>

<td valign="top">morphine 6 beta glucuronide</td>

</tr>

<tr>

<td valign="top">mat</td>

<td valign="top">methionine adenosyltransferase</td>

<td valign="top">methionine adenosyl transferase</td>

</tr>

<tr>

<td valign="top">mcpa</td>

<td valign="top">2 methyl 4 chlorophenoxyacetic acid</td>

<td valign="top">4 chloro 2 methyl phenoxyacetic acid;  
4 chloro 2 methylphenoxy acetic acid;  
4 chloro 2 methylphenoxyacetic acid</td>

</tr>

<tr>

<td valign="top">mdp</td>

<td valign="top">acetylmuramyl alanyl isoglutamine</td>

<td valign="top">muramyl dipeptide:  
muramyldipeptide</td>

</tr>

<tr>

<td valign="top">mlsb</td>

<td valign="top">streptogramin b</td>

<td valign="top">streptograminb</td>

</tr>

<tr>

<td valign="top">mstfa</td>

<td valign="top">n methyl n trimethylsilyl trifluoroacetamide</td>

<td valign="top">n methyl n trimethylsilyltrifluoroacetamide</td>

</tr>

<tr>

<td valign="top">naag</td>

<td valign="top">n acetyl 1 aspartylglutamic acid</td>

<td valign="top">n acetylaspartylglutamate</td>

</tr>

<tr>

<td valign="top">nata</td>

<td valign="top">n acetyltryptophanamide</td>

<td valign="top">n acetyl tryptophan amide;  
n acetyl l tryptophanamide</td>

</tr>

<tr>

<td valign="top">neuac</td>

<td valign="top">n acetylneuraminic acid</td>

<td valign="top">n acetyl neuraminic acid</td>

</tr>

<tr>

<td valign="top">nmm</td>

<td valign="top">omega n methylarginine</td>

<td valign="top">n g monomethyl l arginine;  
ng monomethyl l arginine</td>

</tr>

<tr>

<td valign="top">npa</td>

<td valign="top">alpha naphthylphthalamic acid</td>

<td valign="top">1 n naphthylphthalamic acid;  
n 1 naphthylphthalamic acid;  
naphtylphtalamic acid</td>

</tr>

<tr>

<td valign="top">npe6</td>

<td valign="top">monoaspartyl chlorin e 6</td>

<td valign="top">mono l aspartyl chlorin e 6;  
n aspartyl chlorin e 6</td>

</tr>

<tr>

<td valign="top">nppb</td>

<td valign="top">5 nitro 2 3 phenylpropylamino benzoic acid</td>

<td valign="top">5 nitro 2 3 phenylpropyl amino benzoate;  
5 nitro 2 3 phenylpropylamino benzoate</td>

</tr>

<tr>

<td valign="top">oag</td>

<td valign="top">1 oleoyl 2 acetylglycerol</td>

<td valign="top">1 oleoyl 2 acetyl sn glycerol;  
1 oleoyl acetyl sn glycerol;  
oleoyl acetyl glycerol</td>

</tr>

<tr>

<td valign="top">ocdd</td>

<td valign="top">octachlorodibenzo 4 dioxin</td>

<td valign="top">octachlorinated dibenzo p dioxin;  
octachlorinated dibenzodioxin;  
octachlorodibenzo p dioxin;  
octachlorodibenzodioxin</td>

</tr>

<tr>

<td valign="top">otz</td>

<td valign="top">2 oxothiazolidine 4 carboxylic acid</td>

<td valign="top">2 oxothiazolidine 4 carboxylate</td>

</tr>

<tr>

<td valign="top">pam</td>

<td valign="top">peptidylglycine monooxygenase</td>

<td valign="top">peptidyl glycine alpha amidating monooxygenase;  
peptidyl glycine alpha amidating mono oxygenase;  
peptidylglycine alpha amidating monooxygenase</td>

</tr>

<tr>

<td valign="top">pcmb</td>

<td valign="top">p chloromercuribenzoic acid</td>

<td valign="top">para chloromercuribenzoate</td>

</tr>

<tr>

<td valign="top">pcmbs</td>

<td valign="top">4 chloromercuribenzenesulfonate</td>

<td valign="top">4 chloromercuri benzene sulfonic acid;  
p chloromercuribenzene sulfonate;  
p chloromercuribenzenesulphonic acid;  
p chloromercurybenzenesulfonate</td>

</tr>

<tr>

<td valign="top">prpp</td>

<td valign="top">phosphoribosyl pyrophosphate</td>

<td valign="top">phosphoribosylpyrophosphate</td>

</tr>

<tr>

<td valign="top">rubp</td>

<td valign="top">ribulose 1 5 diphosphate</td>

<td valign="top">ribulose 1 5 bisphosphate</td>

</tr>

<tr>

<td valign="top">sdma</td>

<td valign="top">n n dimethylarginine</td>

<td valign="top">symmetric dimethylarginine;  
symmetric n g n g dimethyl l arginine;  
symmetric ng ng dimethyl l arginine</td>

</tr>

<tr>

<td valign="top">so2</td>

<td valign="top">sulfur dioxide</td>

<td valign="top">sulphur dioxide</td>

</tr>

<tr>

<td valign="top">tbh</td>

<td valign="top">tert butylhydroperoxide</td>

<td valign="top">t butylhydroperoxide;  
tert butyl hydroperoxide;  
tertiary butyl hydroperoxide</td>

</tr>

<tr>

<td valign="top">tcne</td>

<td valign="top">tetracyanoethylene</td>

<td valign="top">tetracyano ethylene</td>

</tr>

<tr>

<td valign="top">tpmt</td>

<td valign="top">thiopurine methyltransferase</td>

<td valign="top">thio purine methyl transferase;  
thiopurine methyl transferase;  
thiopurine s methyltransferase</td>

</tr>

<tr>

<td valign="top">utp</td>

<td valign="top">uridine triphosphate</td>

<td valign="top">uridine 5 triphosphate</td>

</tr>

<tr>

<td valign="top">vpa</td>

<td valign="top">valproic acid</td>

<td valign="top">valproate</td>

</tr>

</tbody>

</table>



## Appendix 2</a> - FNV-Finder algorithm

**Step 1**. Input: an index entry; components extracted from a phrasal MeSH term, or 6-grams extracted from a single word or compound word MeSH term.

Remove from an index entry all lines that do not contain a MeSH term component or a 6-gram. #Such lines do not contain acronym's MeSH term or its variant.

**Step 2**. Input: output file from step 1; a stop word list.

For each line in an entry, match strings in a line against a stop word list. If there is a match then print the end of the line located between the rightmost stop word and the acronym. Else print the whole line, excluding the acronym.

**Step 3**. Input: post-second-step-entry; a prefix string list containing strings 0-100, alpha, beta, gamma, tert, nalpha, d, l, n, p, r, s; acronym.

For each line, start from the right to find a string whose first letter is identical to the first letter of the acronym. If such string is found then mark it as a temporary first component (TFC). Else go to step 4.

Compute LCS for the acronym and the string sequence right to and including the TFC. If LCS = |the number of characters in the acronym| mark the string sequence as a full name candidate. Else go to step 4.

Match the line containing the full name candidate against a prefix string list. If there is a prefix string that appears immediately left to the full name candidate, include it and all consecutive prefix strings to the left of it in the full name candidate, and go to step 5\. Else print the full name candidate and go to step 5.

**Step 4**. Input: lines that were not resolved in step 3; post-second-step-entry; a prefix string list containing strings 0-100, alpha, beta, gamma, tert, nalpha, d, l, n, p, r, s.

Compute a FNV indicator value for each string in the post-second-step-entry. If a line contains one string with FNV indicator > 0.50, mark it as a TFC. If a line contains more than one string with FNV indicator > 0.50, mark the leftmost string as a TFC. Mark the string sequence right to and including the TFC as a full name candidate. Else, if a line does not contain a string with FNV indicator > 0.50, reject the line.

Match the line containing the full name candidate against a prefix string list. If there is a prefix string that appears immediately left to the full name candidate, include it and all consecutive prefix strings to the left of it in the full name candidate, and go to step 5\. Else print the full name candidate and go to step 5.

**Step 5**. Input: output files from steps 3 and 4; a suffix list; MeSH term.

Match the end of the full name candidate against a suffix list. Match the end of the MeSH term against a suffix list. If the full name candidate and the MeSH term match different suffixes, reject the candidate. Else go to step 6.

**Step 6**. Input: output file from step 5; MeSH term.

Match the full name candidate against the MeSH term. If there is a match, mark the full name candidate as a MeSH term. Else mark the full name candidate as a variant form. Print the variant form.

