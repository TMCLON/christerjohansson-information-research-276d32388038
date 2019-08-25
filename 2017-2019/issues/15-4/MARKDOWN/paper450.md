#### vol. 15 no. 4, December, 2010

# Analysis of automatic translation of questions for question-answering systems

#### [Lola García-Santiago](#author) and [María-Dolores Olvera-Lobo](#author)  
CSIC, Unidad Asociada Grupo SCImago, Madrid, España. University of Granada, Department of Library and Information Science, Colegio Máximo de Cartuja s/n., 18071 Granada, Spain

#### Abstract

> **Introduction.** Multilingual question-answering systems can provide users with specific data in response to queries by searching for a minimal fragment of text that applies to the query, regardless of the language in which the question is formulated and the answer is found. The aim of this paper is to analyse the automatic translation of questions (intended as queries input to a cross-language, question-answering system) from German and French into the Spanish language.  
> **Method.** The methodology used for evaluation, based on automatic and subjective measures, appraises whether the translation will serve as input to a system. That is, does the question retain its validity and fulfil its function, allowing a proper response to be found?  
> **Analysis.** The main features of multilingual question-answering systems are described and then we analyse the effectiveness of the translations achieved through three popular online translating tools: Google Translator, Promt and Worldlingo.  
> **Results.** Our findings serve to identify which is the most reliable translator for both pairs of languages overall. However, an even more reliable option would be to use two different translators, depending on which of the two source languages is being dealt with.  
> **Conclusions.** The results contribute to the realm of innovative search systems by enhancing our understanding of online translators and their potential in the context of multilingual information retrieval.

## Introduction

Information retrieval is the collection of tasks implemented by the user to locate and access the information sources that are appropriate to resolve a given need for information. In these tasks, indexing languages, abstracting techniques, and the description of the documental object play key roles, largely determining how fast and efficient retrieval is ([Belkin and Croft 1987](#bel87)). Ideally, there is a balance between the precision and the recall of the informational yield. This aspect is increasingly important, as the World Wide Web diffuses vast quantities of new content every day, in a great variety of formats and languages ([Turpin and Hersh 2001](#tur01)).

When a need for information arises, a process called the search strategy is set in motion, which leads to the supply of documents by the system ([Belkin and Croft 1987](#bel87)). This process entails seven basic stages:

1.  definition of the information need;
2.  selection of the information sources to be used;
3.  translation of the user query expressed in natural language into the indexing language of the information source, if necessary;
4.  translation of the expression from the indexing language to the query language of each information system;
5.  implementation of expressions obtained from the query language;
6.  assessment of results by the user and the redefinition of the query expressions if the results are not relevant; and
7.  selecting and obtaining the documents that respond to the user’s needs.

One step in the evolution toward improved retrieval resides in the use of question-answering systems, which pursue the supply of specific data instead of documents and respond to the questions formulated by users in natural language ([Hallet _et al._ 2007](#hal07)). If this answer derives from documents that are found in other languages, the situation involves a translingual or multilingual question-answering system. This type of system is particularly complex, as it incorporates the capacities of a translingual system for cross-language information retrieval, while also working as a question-answering system.

This approach, where access entails gathering accurate data that respond to specific questions, is a specialization within the more generic concept of multilingual access to information ([López-Ostenero _et al._ 2004](#lop04)). In important international forums, principally the [Text REtrieval Conference](http://www.webcitation.org/query?url=http%3A%2F%2Ftrec.nist.gov&date=2010-11-17) ([Voorhees and Harman 2000](#voo00)) and the [Cross-Language Evaluation Forum](http://www.webcitation.org/query?url=http%3A%2F%2Fwww.clef-campaign.org&date=2010-11-17) ([Clough _et al._ 2004](#clo04), [2006](#clo06)), such systems have been evaluated, with discussion of innovative proposals and techniques. Both have set up a track dedicated to studying question-answering systems. In the general scope of cross-lingual information retrieval, there are several proposals intended to overcome the language barrier that appears when queries and the documents obtained are in different languages.

As mentioned above, systems that deal with multiple languages usually rely on a translation module. The architecture of a cross-lingual information-retrieval system would use one of three main approaches: the translation of the query, the translation of documents from the database, or an interlinguistic approach ([Oard and Diekema 1998](#oar98)). However, at present, translation of the answer could be another possibility ([Bos and Nissim 2006](#bos06)). Translating the query is the most frequent option since they are shorter texts than the documents, and therefore their translations have limited computational costs ([Hull and Grefenstette 1996](#hul96)). Nevertheless, many researchers describe the problems that arise in the translation process when the questions are short and offer little context to help eliminate any semantic ambiguity in the terms of the question; in such cases, interaction with the user ([Oard _et al._ 2008](#oar08)) may improve the results. The underlying translation processes apply different linguistic resources, such as bilingual dictionaries, textual corpora, machine-translation software, and thesauri ([López-Ostenero _et al._ 2004](#lop04); [Abusalah _et al._ 2005](#abu05)); and various mechanisms for disambiguation and the selection of the most appropriate translation between the different proposals available ([Kishida 2005](#kis05)).

As depicted in Figure 1, for the systems that incorporate a translation module, the user enters a specific query, generally including some interrogative adverb (e.g. How? When? Where?) in a given natural source language. This question is translated by an automatic translator. The resulting search expression will then be the _input_, or the formulation of the query to be used by the search engine of the system for comparing and matching it with the documents in the database. Once documents relevant to the query are located, the system breaks them up into sections, selects the excerpts that include the candidate responses and selects a final response. This response, along with its location in the corresponding document, is finally delivered to the user.

<div align="center">![Basic elements of a translingual question-answering system](p450fig1.jpg)</div>

<div align="center">  
**Figure 1: Basic elements of a translingual question-answering system**</div>

Given this background, our study focuses on the first module of the translingual question-answering systems, designed to translate the original user query. In the following sections, we present a comparative study of the quality of the different automatic translation tools that may be used online for no charge, applying three that translate from German and French into the Spanish language. Our perspective is a documental one; that is, we analyse the functionality of the translator as a mediating instrument in the search for answers. To this end, we apply well-known assessment measures (both objective and subjective ones) for machine translation, with the help of [EvalTrans](http://www.webcitation.org/query?url=http%3A%2F%2Fwww-i6.informatik.rwth-aachen.de%2Fweb%2FSoftware%2FEvalTrans%2Findex.html&date=2010-11-17) software. Finally, we analyse the results and offer succinct conclusions.

## Evaluation of automatic translations as input in cross-language question-answering systems

One of the objectives of this study is to identify the most adequate online translator for a given question-answering system entailing a collection of documents in Spanish. In this case, the questions would be formulated in French or in German and would have to be translated into Spanish in order to constitute the system input before proceeding.

Our study used a set of questions from the [Cross-Language Evaluation Forum, 2008](#cle08), with 200 queries in German and the same 200 in French. The questions as expressed in Spanish by each of the online translators were both manually and automatically analysed, applying objective and subjective measures for the evaluation of automatic translation with the aid of EvalTrans software.

### Online translators evaluated

_[Google Translator](http://www.google.es/translate_t?hl=es)_, _[Promt](http://www.online-translator.com)_ and _[Worldlingo](http://www.worldlingo.com/en/products_services/worldlingo_translator.html)_ were selected for this study because they allow us to translate and compare results using language pairs of German to Spanish and French to Spanish. Moreover, they are widely used services, they are quick in translating and they show reasonable quality overall. There are limitations regarding the maximum amount of text (from 150 to 300 characters) with which the free online translators can work, except _Google Translator_, which admits much more extensive texts, but these do not interfere with the purposes of our study, as a question-answering system deals with specific questions for which the formulation is not excessively long.

_Google Translator_ is an automatic translator; that is, it works without the intervention of human translators, using state-of-the-art technology instead. Most commercial machine-translation systems in use today have been developed using a rule-based approach and require substantial work to define vocabularies and grammars. However, this system takes a different approach; the computer is fed billions of words of text, both monolingual text in the target language as well as aligned text consisting of examples of human translations between the languages. Afterwards statistical learning techniques are applied to build a translation model which is able to contextualise. _Promt_ uses semantic classes to improve the syntactic and the semantic correspondence in a sentence.

A subdivision of translation systems into transfer-based systems and Interlingua-based systems has been adopted ([Sokolova 2009](#sok09)). This subdivision is based on aspects of architectural solutions relating to linguistic algorithms. Translation algorithms for transfer-based systems are built as a composition of three processes: analysis of the input sentence in terms of source language structures, conversion of this structure into a similar target-language structure (_transfer_) and, finally, synthesis of the output sentence according to the constructed structure. Interlingua-based systems assume _a priori_ that a certain structure metalanguage (_Interlingua_) is available, which, in principle, can be used for describing any structure of both the source and the target languages. _Wordlingo_ uses statistical techniques from cryptography, applying machine-learning algorithms that automatically acquire statistical models from existing parallel collections of human translations. These models are more likely to be up to date, appropriate and idiomatic, because they are learned directly from real translations. The software can also be quickly customized to any subject area or style and do a full translation of previously unseen text. Statistical machine translation was once thought appropriate only for languages with very large amounts of pre-translated data. Additionally, with customization, such systems can also _learn_ to translate highly technical material accurately ([Grundwald 2009](#gru09)).

### Sample and types of questions

In the stage of the query analysis, the question-answering system examines the user’s question and determines what type of information is being requested. The classification of the questions is crucial for the system, as this information will be utilized in the search stage and in the selection and extraction of the potential responses ([García Cumbreras _et al_. 2005](#gar05)). The collection of 200 Cross-Language Evaluation Forum questions were formulated in German and in French in the input stage (before transformation to an indexing language) and were meant to gather precise data on a given subject.

A sample of 200 cases by each pair of the two languages, French and German, to Spanish is analysed. It is a sample that reflects a normal distribution for an infinite population. This sample has a 95% confidence level, a significance level of 2.5% (p = 0.025) and a statistical power of 0.8\. Bloom, according his taxonomy, considers these queries _questions of knowledge_ ([Bloom 1956](#blo56) and [Forehand 2005](#blo56)). As in a survey, factual questions can be answered by either _Yes_ or _No_. In other cases the answer is nominal; for example, a person, a place or institution. In addition, there are other knowledge questions. Closed-list questions imply a closed group of nominal possibilities (names, verbs, adjectives). Finally, there are definitional questions which describe the existence of some person, thing or process.

These questions may be classified as three types ([Cross-Language... 2008](#cle08)):

*   **Factual questions:** which seek tidbits of information such a names of person, organization or place,locations, time, quantities (measurement or recount) or object, among others. The question always starts with any interrogative particle: _Who...?, When...?, Where...?, Where...?,._...
*   **Definitional questions:** where the information solicited may entail synonymy and formulation with respect to a person, object, organization or concept (_What or who is it_?)
*   **Closed list:** questions that call for a response enumerating various items (_What/is…? How…? or Name_…)

Unlike opinion questions that request an interpretation of the information, e.g. What should I do? or Is it better to do X or Y?, factual questions are focused on finding an specific and objective answer. According to Sloman ([2005](#blo56)), these can cover from the most basic issue, which refers to a proposition that is capable of being true or false and requests the information whether the proposition is true or false, to issues which create one or more gaps in the proposition and specify requests for information. Some factual questions ([Chan _et al._ 2003](#slo05)) can require information which is expressed by an interrogative particle, e.g., who (person), where (location), how many (number). However, for most questions using the interrogative word 'which' or what', we need to find the core noun to help us to identify the information required. For example: Which city is home of Superman? or What type of bee drills holes in wood? These kinds of questions are not lengthy and they have a formal and clear structure.

The 200 questions used were mostly (156) of the factual type; and in the Spanish language, they present mainly interrogative particles, as explained above. The remainder (44) are divided fairly equally into definition questions (24) and closed-list questions (20). Some examples are:

*   _Où l'article de Gerda Taro sur cette bataille a-t-il été publié?_
*   _Qu'est-ce que la vexillologie?_
*   _Quels sont les pays membres de l'Observatoire européen austral?_/ Welche Länder sind Mitglied bei der Europäischen Südsternwarte?

Natural language is not an exact science. Interrogative adverbs in each language change their characteristics and require modifications when these subgroups must be identified clearly. For example, the question 'What political party does Tony Blair belong to?' differs from 'What is a screwdriver?' as the former contains a preposition which goes with the interrogative adverb. Therefore, the latter sentence is classified as a definition-type question. On the other hand, all kinds of questions can include a temporal restriction (e.g.. What book did George Orwell write in 1945?). Hermjakob ([2001](#slo05)) classifies questions from a functional perspective during the information search on the Web. Furthermore, he identifies questions which include interrogative adverbs and he emphasizes questions that only ask for a confirmation or disconfirmation. This author sorts out this typology according to the answer rather the question;consequently, he tags them as 'Yes-No questions' and 'True-False questions'.

### Measures for the evaluation of the automatic translation of questions

Evaluation of machine translation is an unresolved research problem that has been addressed by numerous studies in recent years ([Ueffing and Ney 2007](#uef07)). The most extensively used assessment tools are classified into two major groups: automatic objective methods and subjective methods ([Tomás _et al._ 2003](#tom03)). The objective evaluation methods compare a set of correct reference translations against the set of translations produced by the translation software under evaluation. The measurement units most often used work at the lexical level, comparing strings of text.

Our study evaluated the online translators in the light of the following parameters:

*   _Word error rate_ (WER) ([Tillman _et al._ 1997](#til97); [Vidal 1997](#vid97)): This is based on comparison of the Levensthein Distance or edit distance between two strings of characters. It measures the number of insertions, substitutions and eliminations necessary to convert one string into another (Figure 2). Yet, unlike the edit distance, which does this through the characters, _word error rate_ calculates this distance in relation to the words involved. It can be seen as a _pessimistic_ means of measurement for the evaluation of an automatic translation system ([Pérez _et al._ 2004](#per04)), in that, if the output of the system does not coincide exactly with the reference string, it is penalized, even when the expression is considered acceptable by a human translator.

<div align="center">![Fig2](p450fig2.jpg)</div>

<div align="center">  
**Figure 2: Word error rate formula**</div>

*   aWER _All references word error rate_ (aWER) ([Tomás _et al._ 2003](#tom03)): which gathers, for comparison, all the reference phrases that may be taken into fair consideration, i.e., those that a human translator would include in the process of assessing translations. In other words, it corresponds to the rate of words which have to be changed, erased or included to achieve a correct translation. In this case, however, we have all the phrases of reference to compare, not only the first and, consequently, more alternatives.
*   _Sentence error rate_ (SER): which compares phrases (the string of output from the automatic translator and the reference string) overall, as units. It identifies or measures the lack of fit found through this comparison, which does not necessarily mean that the translation is erroneous. If the two strings differ in some way, the system is penalized. This may be considered an excessively tough tool ([Pérez _et al_. 2004](#per04)).
*   _All references sentence error rate_ (aSER) ([Tomás, _et al._ 2003](#tom03)): the _sentence error rate_ compares the phrase to be evaluated with a single reference string, whereas the _all references sentence error rate_, derived from the _all references word error rate_, is used in order to arrive at the percentage of phrases whose translations are _incorrect_.

All the means of measurement described above are applied automatically. Therefore, the translations and the phrases of reference are compared without any specific determination of the type of error or discrepancy occurring between the two strings under consideration (Figure 3). For this purpose, there are other types of metrics requiring human intervention for evaluation. In the context of translingual question-answering systems that include the machine translation architecture, the aim of translation is more practical; so other evaluation measures of a subjective nature, such as _subjective sentence error rate_ (sSER), were applied.

<div align="center">![Fig3: All references sentence error rate formula](p450fig3.jpg)</div>

<div align="center">_**Figure 3: All references sentence error rate formula**_</div>

Other scoring metrics are:

*   _Position independent error rate_ (PER): this measure is similar to the _word error rate_, but it ignores or does not take into account the positions of the words in the reference sentences. It is a more suitable metric to evaluate the system for tasks where the source and target language words are arranged in different ways and the output sentence admits different rearrangements.
*   _BiLingual Evaluation Understudy_ (BLEU): this measures the translation closeness between a candidate translation and a set of reference translations with a numerical metric. It scores the ngram precision (unigrams, bigrams, trigrams and 4-grams) with regard to a sample of reference translations. An N-gram is a subsequence of n-elements from such a sequence ([Lin and Hovy 2003](#lin03)).
*   _National Institute of Standards and Technology_ (NIST): this algorithm is based on the BLEU metric, but with some modifications. Where BLEU simply calculates n-gram precision, adding equal weight to each one, NIST also calculates how informative a particular n-gram is. That is, n-gram precisions are weighted by the n-gram frequencies, to place more emphasis on the less frequent (and more informative) n-grams. Another significant difference with respect to BLEU is that NIST computes the arithmetic mean of the n-gram precision, also with a length penalty ([Goutte 2006](#gou06)).

Up to this point, comparison of sentences has been discussed without evaluating which kind of error or discrepancy occurred between two sentences. However, there are other systems that automatically evaluate translation assessments made by subjective or human methods ([Wikipedia 2008](#wik08)). Amongst these are:

*   _Subjective sentence error rate_ (sSER): in this measure the score ranges from 0 to 1, signifying from a perfect translation to a nonsense sentence. Originally, Nießen ([2000](#nie00)) proposed a score scale from 0 to 10 but has since concluded that scale is too wide and that six or seven quality classes it would function better.
*   _Information item error rate_ (IER): for this measure, the sentence is segmented into information items. A person assesses whether the information from each item is found in the translation. Hence, it can be checked whether, in a wrong translation of the sentence, there are parts that are correctly translated ([Nießen et al. 2000](#nie00)).

Our aim is to customize the system of automatic-translation evaluation _subjective sentence error rate_ with our research from German to Spanish and from French to Spanish. In addition, we propose an evaluation form adapted specifically to the question-answering systems. A _perfect_ translation is not the aim of this study, but, rather, a translation which is able to preserve the characteristics of the questions and consequently enable the system to locate the suitable answers.

### Analysis with EvalTrans

The evaluation process was carried out using EvalTrans software ([Nießen _et al._ 2000](#nie00)) in its graphic version designed for use with Windows ([Tomás _et al._ 2003](#tom03)). This tool can be used freely online, for the evaluation of automatic translation. It provides us with statistics, such as the average Levensthein distance standardized to the length of the target sentence and calculates previous rates by means of automatic metrics ([Dabbadie _et al_. 2002](#dab02)).

One advantage of this program is that it can compare the results of each translator with the other translators studied for the same set of phrases. It works with the follow indicators: WER, mWER, aWER, SER, mSER and sSER (described above). These measures are widely used and they consider important the order of words in the sentence. In addition, it allows for a qualification in the assessment of the translation with a manual and subjective supervision. It is intended to correct the failings of an automatic system without a lexicon when seeking to detect several possible ideal sentences (it supports only a single perfect sentence for comparison). It also includes grading for the assessment (Figure 4).

The selected translators were evaluated independently (e.g., _word error rate_ (WER)) and combined (e.g., _all references word error rate_ (aWER) and _all references word sentence rate_ (aSER)) . EvalTrans highlights the differences in the comparison of the two sentences, which is evaluated with respect to the reference.

<div align="center">![EvalTrans Example](p450fig4.jpg)</div>

<div align="center">  
**Figure 4: Example of EvalTrans**</div>

The metrics used are designed for phrases and questions are short phrases with a predictable structure according to the grammar of the language.

EvalTrans is a tool for evaluating translations using metrics, which are considered as important as the word order. In an effort to mitigate the rigidity of some of these, the _all references word error raqte_ (aWER) and the _all references sentence error rate_ (aSER) are calculated. The latter takes into account more than one alternative when the sentence assessed is compared or checked with the reference or model-phrase collection. This metric evaluation is made fully automatic by calculating the _subjective sentence error rate_ (sSER) with human values (or subjective ratings rather than the match or not match automatic methods), which considers the functionality of the translation in a question-answering system. The increase in the number of reference phrases in human evaluation also changes the rates of aWER and aSER.

## Analysis of results

The results shown are averages, based on the yield of the online translators, given the values obtained on applying the measures described above and the values that resulted from the human assessment of each question translated.

### Effectiveness of the online translators according to indicators used

Tables 1 and 2 show the values based on the set of 200 questions in terms of _word error rate_ (WER) and _sentence error rate_ (SER) for the _Google Translator_, _Promt_ and _Worldlingo_ in automatic evaluations, from German and French into Spanish.

<table width="60%" border="1" cellspacing="0" cellpadding="3" align="center" style="border-right: #444444 solid; border-top: #444444 solid; font-size: smaller; border-left: #444444 solid; border-bottom: #444444 solid; font-style: normal; font-family: verdana, geneva, arial, helvetica, sans-serif; background-color: #ffffff"><caption align="bottom">  
**Table 1: Automatic evaluation of the translations from German to Spanish**</caption>

<tbody>

<tr>

<th>GERMAN</th>

<th>Google</th>

<th>WorldLingo</th>

<th>Promt</th>

</tr>

<tr>

<td>WER</td>

<td align="center">41.9%</td>

<td align="center">57.6%</td>

<td align="center">54.4%</td>

</tr>

<tr>

<td>SER</td>

<td align="center">95.0%</td>

<td align="center">98.5%</td>

<td align="center">99.0%</td>

</tr>

</tbody>

</table>

<table width="60%" border="1" cellspacing="0" cellpadding="3" align="center" style="border-right: #444444 solid; border-top: #444444 solid; font-size: smaller; border-left: #444444 solid; border-bottom: #444444 solid; font-style: normal; font-family: verdana, geneva, arial, helvetica, sans-serif; background-color: #ffffff"><caption align="bottom">  
**Table 2: Automatic evaluation of the translations from French to Spanish**</caption>

<tbody>

<tr>

<th>FRENCH</th>

<th>Google</th>

<th>WorldLingo</th>

<th>Promt</th>

</tr>

<tr>

<td>WER</td>

<td align="center">43.2%</td>

<td align="center">40.8%</td>

<td align="center">39.6%</td>

</tr>

<tr>

<td>SER</td>

<td align="center">95.5%</td>

<td align="center">93.0%</td>

<td align="center">90.0%</td>

</tr>

</tbody>

</table>

The high values found for the _sentence error rate_ (SER) can be attributed to the need for the evaluation software to find a string from the online translator that is identical (with the same words and in the same order) to the reference phrase in order to calculate the edition rate. Any variation, even a minor one, is interpreted as an erroneous phrase (in our case an erroneous question) and is left out. Tables 3 and 4 below reflect that the _subjective sentence error rate_ (sSER) measure aims for greater precision than the SER measure, by taking into account human evaluation and the corresponding acceptance or rejection of the phrase supplied by the online translator, judged as correct or incorrect. Our objective, however, is merely to identify the translating program that generates the most functional input for a translingual question-answering program.

In addition, the coefficients corresponding to the _all references word error rate_, the _sentence error rate_ and _all references sentence error rate_ do indeed vary in conjunction with human intervention (see Tables 3 and 4). For instance, the _subjective sentence error rate_ measure takes the scores for each one of the phrases already translated and evaluated. The _all references word error rate_ measure, meanwhile, gathers all the reference phrases that have been considered subsequently as such by a human translator. These tend to be proposed by the human evaluator as _new reference_ after the reduction of the edit distance; or else, a candidate phrase is scored with a maximum mark. The evaluating program adopts the phrase of reference that is most similar to the group of phrases of reference already existing, not just the first sentence of reference included _a priori_.

The ranking of the online translation programs analysed with regard to their effectiveness means that the best translator of the three would be the one scoring the lowest index (lowest occurrence of errors), especially evident with _subjective sentence error rate_ and _all references word error rate_, which account for human assessment.

Because the applied measures for automatic evaluation do not make a comprehensive syntactic analysis (noting the position of the words in the phrase), the error indexes are greater in German. The fact that the edit distance registers not only the existence of words in the sentence, but also their position, leads to higher error rates when the German language is involved, since alteration in the order of the elements is identified as an error ([Tillman _et al._ 1997](#til97)).

Accordingly, grammatical similarities between the French and Spanish languages result in fewer errors (see Tables 1 and 2). It bears noting that only in the case of _Google Translator_ were the error indexes in conjunction with words (_word error rate_) higher for French than for German. After the subjective assessments of the translations by the application of _all references word error rate_ (aWER), _subjective sentence error rate_ (sSER) and _all references sentence error rate_ (aSER), the results were as follows:

<table width="60%" border="1" cellspacing="0" cellpadding="3" align="center" style="border-right: #444444 solid; border-top: #444444 solid; font-size: smaller; border-left: #444444 solid; border-bottom: #444444 solid; font-style: normal; font-family: verdana, geneva, arial, helvetica, sans-serif; background-color: #ffffff"><caption align="bottom">  
**Table 3: Indicators calculated with human assessment of the translations from German to Spanish**  
</caption>

<tbody>

<tr>

<th>GERMAN</th>

<th>Google</th>

<th>WorldLingo</th>

<th>Promt</th>

</tr>

<tr>

<td>aWER</td>

<td align="center">57.6%</td>

<td align="center">54.6%</td>

<td align="center">50.4%</td>

</tr>

<tr>

<td>sSER</td>

<td align="center">90.2%</td>

<td align="center">91.3%</td>

<td align="center">77%</td>

</tr>

<tr>

<td>aSER</td>

<td align="center">88%</td>

<td align="center">94%</td>

<td align="center">91%</td>

</tr>

</tbody>

</table>

<table width="60%" border="1" cellspacing="0" cellpadding="3" align="center" style="border-right: #444444 solid; border-top: #444444 solid; font-size: smaller; border-left: #444444 solid; border-bottom: #444444 solid; font-style: normal; font-family: verdana, geneva, arial, helvetica, sans-serif; background-color: #ffffff"><caption align="bottom">  
**Table 4: Indicators calculated with human assessment of the translations fromFrench to Spanish**  
</caption>

<tbody>

<tr>

<th>FRENCH</th>

<th>Google</th>

<th>WorldLingo</th>

<th>Promt</th>

</tr>

<tr>

<td>aWER</td>

<td align="center">36.7%</td>

<td align="center">29.7%</td>

<td align="center">27.5%</td>

</tr>

<tr>

<td>sSER</td>

<td align="center">70.4%</td>

<td align="center">53.7%</td>

<td align="center">55.5%</td>

</tr>

<tr>

<td>aSER</td>

<td align="center">87.5%</td>

<td align="center">78.5%</td>

<td align="center">75%</td>

</tr>

</tbody>

</table>

Practically all the values decreased with human assessment, meaning that the error indexes were reduced. The consideration of various alternatives as acceptable leads to a greater yield of questions of reference for calculating _all references word error rate_ and _all references sentence error rate_. The graphic display of the assessment values found with regard to the translations into Spanish from German (Figure 5) and from the French (Figure 6) for the automatic translators evaluated reveal that the error indexes per word (WER and aWER) were lower when the source language was French.

<div align="center">![Figure 5 : Comparison of overall values after human assessment (German-Spanish)](p450fig5.jpg)</div>

<div align="center">  
**_Figure 5 : Comparison of overall values after human assessment (German-Spanish)_**</div>

<div align="center">![Figure 6: Comparison of values after human assessment (French-Spanish)](p450fig6.jpg)</div>

<div align="center">**_Figure 6: Comparison of values after human assessment (French-Spanish)_**</div>

Likewise, the percentages derived from the errors per phrase, whether subjective (the _subjective sentence error rate_ (sSER)) or automatic (the _sentence error rate_ (SER) and the _all references sentence error rate_ (aSER)), were lower for the translation from French than from German. One reason would be that these measures do not register any coincidence of words if the automatic translator has altered the word order with regard to the phrase of reference.

We may also interpret the _word error rate_ indicators depending on the kind of sentence or phrase. In the 200 phrases studied for each language, regardless of their length, it would be necessary to change, reorder, replace, or modify between four and six words of the string in order to achieve the ideal translation or equal the reference translation (Table 5).

<table width="60%" border="1" cellspacing="0" cellpadding="3" align="center" style="border-right: #444444 solid; border-top: #444444 solid; font-size: smaller; border-left: #444444 solid; border-bottom: #444444 solid; font-style: normal; font-family: verdana, geneva, arial, helvetica, sans-serif; background-color: #ffffff"><caption align="bottom">  
**Table 5: Average number of words that must be modified to arrive at the “perfect” translation**  
</caption>

<tbody>

<tr>

<th>Edit Distance</th>

<th>Google</th>

<th>WorldLingo</th>

<th>Promt</th>

</tr>

<tr>

<td>GERMAN</td>

<td align="center">4.29</td>

<td align="center">5.85</td>

<td align="center">5.57</td>

</tr>

<tr>

<td>FRENCH</td>

<td align="center">4.42</td>

<td align="center">4.12</td>

<td align="center">4.05</td>

</tr>

</tbody>

</table>

Evaluation of the error rate without taking into account the order of the terms within the phrase is reflected the _subjective sentence error rate_ measure: when translating from German into Spanish, this error rate was greater than for French translated into Spanish. In other words, evaluations of the translations are better when the word order is overlooked. For French (Table 4), where grammatical similarity leads to a considerable reduction in error, the _Promt_ translator offers the best results, followed by _Worldlingo_. However, when the phrases are translated from the German language, Google provides the best results in the automatic measurements (Table 3). The values are lower (better) for _Promt_ than for _Google_, with _Worldlingo_ taking last place. The fact that this measure relies on human assessment bears weight in the selection of the ideal online translator, since the main criterion to be upheld is the effectiveness of the resulting translation as input in a question-answering system.

### Human evaluation of the translations

For the manual evaluation of the translations generated by automatic online translators, we applied the Likert scale ([Uebersax 2006](#ueb06)), using six levels. We were thus able to reduce the excessive range of the classification method of Niessen _et al_. ([2000](#nie00)), with its eleven levels, adopted by EvalTrans. Taking into account the finality of the translation, the assessment implied that errors such as the position of the elements in the string would not have to be penalized to the same degree as ambiguity, or the loss of some characteristic of the question (e.g., interrogative adverb, or the entity to which the question refers). The resulting assessments were zero when the phrase was totally incorrect and meaningless as a translation, and therefore useless as a question for input in a question-answering system; up to five when the phrase was considered _perfect_. These values were then used to calculate the indexes given below.

The automatic evaluation compares the output with the reference sentence provided by the Cross-Language Evaluation Forum. First, we have a sample of 200 questions in Spanish and their French and German translations. The human evaluation is made without taking into account reference sentences to compare with the translator’s output. The role of a professional human translator is to monitor the outputs of the three new online translators and rating on a scale of 0 to 5 if the new translation is suitable from a functional or operational standpoint and without relying on one or more reference phrases. On the other hand, these measurements were complemented automatically with manual evaluation, in which a professional human translator who works in these three languages, has assigned scores (from 0 to 5). to assess the quality of the translation of each one of the phrases in both language pairs. Also, it was possible to identify the different types of errors that occurred throughout the translation process. The manual evaluation was consistently higher than the phrases translated into Spanish and we should bear in mind that a functional criterion was taken into account in this study to determine the translation quality. Figures 5 and 6 show the results of this human assessment.

As discussed in the section above, according to the _subjective sentence error rate_ index, in the case of German, _Promt_ (77%) is the best translator, followed by _Google_ (with 90.2%). By contrast, when dealing with French, _Worldlingo_ (53.7%) proved to be the best translator, although _Promt_ (55.5%) had a very similar rating. According to the human assessment, the behaviour of the three online translators analysed is more irregular (presenting a greater standard deviation) in the case of the translations from French than for those from German (Table 6). The resulting values were lower for German but more homogeneous for French.

<table width="60%" border="1" cellspacing="0" cellpadding="3" align="center" style="border-right: #444444 solid; border-top: #444444 solid; font-size: smaller; border-left: #444444 solid; border-bottom: #444444 solid; font-style: normal; font-family: verdana, geneva, arial, helvetica, sans-serif; background-color: #ffffff"><caption align="bottom">  
**Table 5: Standard deviation calculated over human assessments**  
</caption>

<tbody>

<tr>

<th> </th>

<th>Google</th>

<th>WorldLingo</th>

<th>Promt</th>

</tr>

<tr>

<td>GERMAN-SPANISH</td>

<td align="center">1.820</td>

<td align="center">1.573</td>

<td align="center">1.522</td>

</tr>

<tr>

<td>FRENCH-SPANISH</td>

<td align="center">2.010</td>

<td align="center">2.132</td>

<td align="center">2.136</td>

</tr>

</tbody>

</table>

Figure 6 shows the Bell curve and the normal distribution of the values found. Nevertheless, the irregularity of the translations from French is reflected in greater differences between the translators. In this sense, it is notable that _Worldlingo_, when translating from French (Figure 7), scores higher in the evaluation of its translations, with a mean value of 2: a nearly correct and quite consistent translation. This is seen in the asymmetric distribution tending toward the left, or lower values on the scale used. The normal distribution is almost fully centred, as in the case of the _Google Translator_; yet its values are much lower (Figures 7 and 8).

<div align="center">![Fig6 Distribution of the evaluations involving French](p450fig7.jpg)</div>

<div align="center">  
**Figure 7: Distribution of the evaluations involving French**</div>

<div align="center">![Fig8](p450fig8.jpg)</div>

<div align="center">  
**Figure 8: Distribution of the evaluations involving German**</div>

## Conclusions

We studied the automatic online translators _Google Translator, Promt_ and _Worldlingo_, applying different means of evaluation. Strictly automatic evaluation (in the absence of subjective assessment) was found to render high error indexes that are scarcely representative.

Automatic translators are the most widely used resource for multilingual question-answering systems, followed by textual corpora and dictionaries ([Nguyen _et al._ 2009](#ngu09)). Despite the problems of ambiguity and non-optimal quality of the texts (especially in case of restricted domain systems), automatic translators turn out to be one of the most economical and simple tools to integrate with these systems. However, while this is still the favorite tool of choice for developers, individually or in combination with other language resources, a tendency can be discerned in recent years to incorporate other resources. Indeed the language corpora are also useful, especially for question-answering multilingual systems in a specialized domain, since they are made by professional human translators.

The textual corpora that are located on the Web with pages available in several languages can overcome the problems of computational cost and storage, very common in this type of resource. Furthermore, the grammar and ambiguity problems have decreased the use of dictionaries as a resource for translation in question-answering systems; however, there is increased use of new resources such as ontologies, Wikipedia, databases, thesauri, multilingual lexico-semantic networks, such as [EuroWordNet](http://www.illc.uva.nl/EuroWordNet/), or tools such as computational grammars. Sometimes, a single application or tool is not complete enough to solve the problem of cross-lingual communication so that the use of several could offer better results.

The error indexes from automatic evaluation are higher when the translation is from the German into Spanish, because the most frequently used measurements for evaluating translations use indicators that compare word-by-word, looking for the very same order of elements in the translation produced online as in the initial reference phrase. Therefore, the syntactic errors detected are more numerous because of basic grammatical differences between the source language (German) and the target language (Spanish). Also greater are the error indexes resulting from subjective assessment, as made here, owing to the capacities of the tools themselves in translating from German into Spanish. The grammatical similarities between French and Spanish tend to give a lower error index.

Our findings identify _Promt_ as the most reliable translator for both pairs of languages overall. However, an even more reliable option would be to use two different translators, depending on which of the two source languages is being used. In this case, the selected translators would be _Google Translator_ or _Promt_ for the German language and _Promt_ for French.

At this point, evaluation measures for automatic translators need to be explored in greater depth in order to arrive at means that provide more flexible criteria (not strictly the dichotomy of exact match vs. not exact match) for assessing the translated phrase to be evaluated. This may be achieved using a larger set of lexical strings of reference, or by adjusting better to the order of the elements within the phrase, or even through some consideration of the roots and canonical forms, as well as the words with their complete flexive and identifying traits (exact match) . Improving the units of measure and techniques for automatic evaluation constitutes a research front which parallels the improvement of automatic translating systems themselves. Moreover, it would prove beneficial if the different tools now being used or developed for the evaluation of translations, such as EvalTrans, and the various research studies undertaken were to use the same scale of human assessment. This would make it easier to introduce data and to quantify the measures applied by human assessments (such as the _subjective sentence error rate_ measure).

The translation mistakes of the interrogative particles identified in Table 2 vary according to the question and the online automatic translator used. The findings show that there is no direct relationship between the type of interrogative particle and the resulting error. It is worth noting, however, that the mismatch among automatic translators when they make an error indicates that the information stored in each online automatic translator could complement each another so as to improve their efficiency.

Grammar can have an impact on meaning. For an instance in English, an apostrophe makes the contraction _it's_, which means _it is_, while the same three letters spell _its_, the possessive third person pronoun or adjective for _it_. The absence or presence of the apostrophe is not an option and changes the meaning of the word entirely and, therefore, an online translator should know the difference. In the same sense, a good automatic translator needs the set of rules that apply to the correct usage of a language. In our research, we have discovered that polysemous verbs in the target language lead to the wrong translation. This is the case of the verb _sein_ in German or _être_ in French (_to be_ in English) which has two possible meanings in Spanish, _ser_ or _estar_. This polysemous situation could be solved with a syntactic analysis of the sentence. In this example, we could introduce a grammatical rule explaining that the verbs _sein_ or _être_ can be translated as _estar_ if there is any noun of location in the sentence.

Finally, it bears mentioning here that although the quality of automatic online translations may be poor, the demand for this type of translation tool is widespread and growing, especially in the multilingual context of the Internet. Therefore, such services will be demanded to an increasing extent in the future and we should concentrate continuous effort on their improvement. In future studies our research team will follow this line deeper into the design of efficient and effective multilingual question-answering systems.

## Acknowledgements

We wish to thank the anonymous referees for their helpful comments.

## About the authors

Lola García-Santiago is a Doctor of Documentation, University of Granada, where she works as Professor. At present she teaches at both the University School of Documentation and the School of Translation and Interpretation. She is also part of the associated unit of the SCImago research group, in Spain’s Higher Council for Scientific Research (CSIC), where her lines of work and published articles focus mainly on Web-mining, Internet information retrieval, question-answering systems and gray literature. She can be contacted at [mdolo@ugr.es](mailto:mdolo@ugr.es)

María-Dolores Olvera-Lobo holds a Ph.D. in Documentation and is full Professor in the Department of Communication and Documentation of the University of Granada and also teaches in the School of Translation and Interpretation. As member of the associated unit of the SCImago team, she participates in a number of research projects now under way and has authored or co-authored several books and numerous articles published in specialized journal. She can be contacted at [molvera@ugr.es](molvera@ugr.es)

## References

*   Abusalah, M.,Tait, J. & Oakes, M. (2005). Literature review of cross language information retrieval. _Proceedings of World Academy of Science, Engineering and Technology_, **4**, 175-177.
*   Belkin, N.J. & Croft, W. B. (1987). Retrieval techniques. _Annual Review of Information Science and Technology_. **22** 109-146.
*   Bloom, B.S. & Krathwohl, D.R. (1956). Taxonomy of educational objectives: the classification of educational goals, by a committee of college and university examiners. Handbook 1: Cognitive domain. New York, NY: Longmans.
*   Bos, J. & Nissim, M. (2006). [Cross-lingual question answering by answer translation.](http://www.webcitation.org/5uJHOlGWR) In C. Peters (Ed.), _Working Notes for the CLEF 2006 Workshop, 20-22 September, Alicante, Spain._ Retrieved 17 November, 2010 from http://www.clef-campaign.org/2006/working_notes/workingnotes2006/bosCLEF2006.pdf (Archived by WebCite® at http://www.webcitation.org/5uJHOlGWR)
*   Chang Y., Xu H.B. & Bai, S. (2003). [TREC 2003 question answering track at CAS-ICT.](http://www.webcitation.org/5uJIJ2aEx) In . M. Voorhees and Lori P. Buckland (Eds.). _The Twelfth Text Retrieval Conference (TREC 2003), Gaithersburg, Maryland._ (pp. 147-151). Retrieved 17 November, 2010 from http://trec.nist.gov/pubs/trec12/papers/chinese-acad-sci.qa.final.pdf (Archived by WebCite® at http://www.webcitation.org/5uJIJ2aEx)
*   Clough, P., Müller, H., Deselaers, T., Grubinger, M., Lehmann, T., Jensen, J. & Hersh, W. (2006). The CLEF 2005 cross-language image retrieval track. In C. Peters, F.C. Gey, J. Gonzalo, H. Müller, G.J.F. Jones, M. Kluck, _et al._ (Eds.), _Accessing Multilingual Information Repositories. 6th Workshop of the Cross-Language Evaluation Forum, CLEF 2005, Vienna, Austria, 21-23 September, 2005,_ , (pp. 535-557). Berlin, Heidelberg: Springer-Verlag. (Lecture Notes in Computer Science, 4022)
*   Clough, P., Müller, H. & Sanderson, M. (2005), (2004). The CLEF cross-language image retrieval track (ImageCLEF) 2004\. In P. Enser, Y. Kompatsiaris, N. E. O'Connor, A. F. Smeaton & A.W.M. Smeulders, (Eds.). _Proceedings of the third International Conference Image and Video Retrieval (CIVR) 2004, Dublin, Ireland, July 21-23, 2004._ (p. 2066.) Berlin, Heidelberg: Springer-Verlag. (Lecture Notes in Computer Science, 3115)
*   Cross-Language Evaluation Forum. (2008). [Guidelines for the participants in QA@CLEF 2008](http://www.webcitation.org/5utnRpnH0). Retrieved 19 November 2010 from http://clef-qa.fbk.eu/2008/download/QA@CLEF08_Guidelines-for-Participants_new.pdf (Archived by WebCite® at http://www.webcitation.org/5utnRpnH0)
*   Dabbadie, M., Hartley A., King M., Miller K.J., Mustafa El Hadi W., Popescu-Belis A. _et al._ (2002). A hands-on study of the reliability and coherence of evaluation metrics. In M. King, (Ed.). _[Workbook of the LREC 2002 Workshop on Machine Translation Evaluation: Human Evaluators Meet Automated Metrics. Las Palmas de Gran Canaria, Spain, 27 May 2002](http://www.webcitation.org/5utoE1adF)_, (pp.8-16). Retrieved 18 november 2010 http://www.mt-archive.info/LREC-2002-WS-MTEval.pdf (Archived by WebCite® at http://www.webcitation.org/5utoE1adF)
*   Forehand, M. . (2005). [Bloom's taxonomy: original and revised](http://www.webcitation.org/5utoUtcPJ). In M. Orey (Ed.), _Emerging perspectives on learning, teaching and technology._ Athens, GA: University of Georgia. Retrieved 8 March, 2010 from http://www.coe.uga.edu/epltt/bloom.htm. (Archived by WebCite® at http://www.webcitation.org/5utoUtcPJ)
*   Garcí,a Cumbreras, M. ., Ureña López, L.A., Martínez Santiago, F., Montejo Raez, A. (2005). [Bú,squeda de respuestas multilingü,e: clasificació,n de preguntas en españ,ol basadas en aprendizaje [Multilingual question-answering: classification learning-based of questions in Spanish]]( http://www.webcitation.org/5uvGZxOCU) . Procesamiento del lenguaje natural. No. 34, 31-40\. Retrieved 18 November, 2010 from http://www.sepln.org/revistaSEPLN/revista/34/03.pdf (Archived by Webcite® at http://www.webcitation.org/5uvGZxOCU)
*   Goutte, C. (2006). [Automatic evaluation of machine translation quality](http://www.webcitation.org/5uvH3utpE). Presentation at the European Community, Xerox Research Centre Europe, on January 27 2006, Meylan, France. Retrieved 8 March 2010 from http://www.xrce.xerox.com/content/download/6980/52379/file/MTeval.pdf (Archived by Webcite® at http://www.webcitation.org/5uvH3utpE)
*   Grunwald, D. (2009). [Worldlingo fights to stay on top of Internet translation market niche](http://www.webcitation.org/5v4nmRnD7) ._GTS Blog_. http://blog.gts-translation.com/2009/08/17/worldlingo-fights-to-stay-on-top-of-internet-translation-market-niche/ (Archived by WebCite® at http://www.webcitation.org/5v4nmRnD7)
*   Grunwald, D. (2009). [Worldlingo fights to stay on top of Internet translation market niche](http://www.webcitation.org/5uL9r3xIg/) ._GTS Blog_. http://blog.gts-translation.com/2009/08/17/worldlingo-fights-to-stay-on-top-of-internet-translation-market-niche/ (Archived by Webcite® at http://www.webcitation.org/5uL9r3xIg )
*   Hallet, C., Scott, D &Power, R. (2007). Composing questions through conceptual authoring. _Computational Linguistics_, **33**(1) 105-133.
*   Hermjakob, U. (2001). [Parsing and question classification for question answering.](http://www.webcitation.org/5uL9vd9zX) In _Proceedings of the Workshop on Open-Domain Question Answering at Annual Meeting of the Association for Computational Linguistics (ACL) 2001_, Volume 12, (pp. 1-6). Stroudsburg, PA: Association for Computational Linguistics. Retrieved 18 November 2010\. http://www.isi.edu/~ulf/papers/acl01-qa-parsing.pdf (Archived by Webcite® at http://www.webcitation.org/5uL9vd9zX)

*   Kishida, K., Chen, K., Lee, S., Kuriyama, K., Kando, N. & Chen, H. (2007). [Overview of cross-lingual information retrieval (CLIR) task at the Sixth NTCIR Workshop](http://www.webcitation.org/5uLBOzqkn). In _Proceedings of NII Test Collection for IR Systems (NTCIR) 6 Workshop Meeting, June 15-18_. Tokyo: National Institute for Informatics. Retrieved 18 November 2010 from http://research.nii.ac.jp/ntcir/workshop/OnlineProceedings6/NTCIR/79.pdf (Archived by Webcite® at http://www.webcitation.org/5uLBOzqkn)
*   Lin, C.Y. & Hovy, E. (2003). [Automatic evaluation of summaries using N-gram co-occurrence statistics](http://www.webcitation.org/5uvHEaPBz). In _Proceedings of the 2003 Conference of the North American Chapter of the Association for Computational Linguistics on Human Language Technology - Volume 1 (NAACL '03) Edmonton, May-June 2003_. Volume 1 (NAACL '03), (pp. 71-78). Stroudsburg, PA: Association for Computational Linguistics. Retrieved 8 March 2010 from http://acl.ldc.upenn.edu/N/N03/N03-1020.pdf (Archived by Webcite® at http://www.webcitation.org/5uvHEaPBz)
*   López-Ostenero, F.,Gonzalo, J. &Verdejo, F. (2004). Búsqueda de información multilingüe: estado del arte. [Multilingual information searching:state of art] _Inteligencia Artificial, Revista Iberoamericana de Inteligencia Artificial_. **8**(22), 11-35.
*   Nguyen, D., Overwijk, A., Hauff, C., Trieschnigg, D. R.B., Hiemstra, D. & de Jong, F.M.G. (2009). WikiTranslate: query translation for cross-lingual information retrieval using only Wikipedia. In C. Peters, Th. Deselaers, N. Ferro, J. Gonzalo, G.J.F. Jones, M. Kurimo, _et al._ (Eds.). _Evaluating Systems for Multilingual and Multimodal Information Access. Proceedings of the 9th Workshop of the Cross-Language Evaluation Forum, CLEF 2008, Aarhus, Denmark, September 17-19, 2008._ (pp. 58-65). Berlin, Heidelberg: Springer-Verlag. (Lecture Notes in Computer Science, 5706)
*   Niessen, S., Och, F.J., Leusch, G. & Ney, H. (2000). [An evaluation tool for machine translation: fast evaluation for MT research](http://www.webcitation.org/5uMd0IGCE). In _Proceedings of the 2nd International Conference on Language Resources and Evaluation (LREC-2000), Athens, Greece, May-June 2000_. (pp. 39-45). Paris: European Language Resources Association. Retrieved 5 May 2008 from http://www.mt-archive.info/LREC-2000-Niessen.pdf (Archived by Webcite® at http://www.webcitation.org/5uMd0IGCE)
*   Oard, D. W. & Diekema, A.R. (1998). Cross-language information retrieval. _Annual Review of Information Science and Technology_, **33**, 223-256.
*   Oard, D. W., He, D. & Wang, J. (2008). User-assisted query translation for interactive cross-language information retrieval. _Information Processing & Management_, **44**(1) 181-211.
*   Pérez, A., González, J., Casacuberta, F. & Torres, I. (2004). [Traducció,n automá,tica mediante transductores estocá,sticos de estados finitos basados en gramá,ticas k-explorables](http://www.webcitation.org/5uvHQwbSL) . [Automatic translation by finite state stochastic transductors based on k-testable grammars]. In E. Sanchis Arnal, (Ed.). Actas de las III Jornadas en Tecnologías del Habla, Techabla, Valencia, Noviembre 2004\. (pp. 207-213). Retrieved 19 November 2010 from http://lorien.die.upm.es/~lapiz/rtth/JORNADAS/III/actas3JTH.pdf (Archived by WebCite® at http://www.webcitation.org/5uvHQwbSL)
_*   Sloman, A. (2005). _[Towards an ontology for factual questions](http://www.webcitation.org/5uMiAXuPG)._ Birmingham, UK: Birmingham University. [Incomplete draft notes (Part of CoSy deliverable DR.02.01: Requirements study for representation)]. Retrieved 11 December, 2010 from http://www.cs.bham.ac.uk/~axs/misc/question-ontology.pdf (Archived by Webcite® at )_
*   Sokolova, S. (2009). _[How the computer translates.](http://www.webcitation.org/5uJS8YAho)_ St. Petersburg, Russia: PROMT Ltd. Retrieved 17 November, 2010 from http://www.promt.com/company/technology/pdf/e_how_computer_translates_sokolova.pdf (Archived by WebCite® at http://www.webcitation.org/5uJS8YAho)
*   Tillman, C., Vogel, S., Ney, H. & Zubiaga, A. (1997). A DP based search using monotone alignments in statistical translation. In _Proceedings of the 35th Annual Meeting of the Association for Computational Linguistics and Eighth Conference of the European Chapter of the Association for Computational Linguistics, Madrid, Spain, July 1997_. (pp. 289-296). Stroudsburg, PA Association for Computational Linguistics.
*   Tomá,s, J., Mas, J.A. & Casacuberta, F. (2003). [A quantitative method for machine translation evaluation](http://www.webcitation.org/5uO4C88Ai). In _Proceedings of the Euoropean Association of Computational Linguistics Workshop on Evaluation initiatives in NLP: are evaluation methods, metrics and resources reusable?, Budapest, Hungary._ (pp. 27-34). Stroudsburg, PA: Association for Computational Linguistics. Retrieved 20 November 2010 from http://www.aclweb.org/anthology-new/W/W03/W03-2804.pdf (Archived by Webcite® at http://www.webcitation.org/5uO4C88Ai)
*   Turpin, A.H. & Hersh, W. (2001) [Why batch and user evaluations do not give the same results](http://www.webcitation.org/5uvGqzSJB) In _Proceedings of the 24th Annual International ACM SIGIR Conference on Research & Development on Information Retrieval, September 9-12, 2001, New Orleans, Louisiana, USA._ (pp. 225-231). New York, NY: ACM Press. Retrieved 20 November 2010 from http://www.seg.rmit.edu.au/research/download.php?manuscript=266 (Archived by Webcite® at http://www.webcitation.org/5uvGqzSJB)
*   Uebersax, J.S. (2006). [Likert scales: dispelling the confusion](http://www.webcitation.org/5uO7Qr2vU). Retrieved 10 November, 2010 from http://www.john-uebersax.com/stat/likert.htm (Archived by Webcite® at http://www.webcitation.org/5uO7Qr2vU)
*   Ueffing, N. & Ney, H. (2007). Word-level confidence estimation for machine translation. _Computational Linguistics_, **33**(1), 9-40.
*   Vidal, E. (1997). Finite-states speech-to-speech translation. In _Proceedings of the 1997 IEEE International Conference on Acoustics, Speech, and Signal Processing (ICASSP '97), Munich, Germany._. Volume 1 (p. 111). Washington, DC: IEEE Computer Society.
*   Voorhees, E.M. & Harman, D. (2000). Overview of the Sixth Text REtrieval Conference (TREC-6). _Information Processing & Management_, **36**(1), 3-35.