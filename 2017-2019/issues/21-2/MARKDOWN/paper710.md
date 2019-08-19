#### vol. 21 no. 2, June 2016

# Balancing efficiency and effectiveness for fusion-based search engines in the 'big data' environment

[Jieyu Li, Chunlan Huang, Xiuhong Wang](#authors) and [Shengli Wu](#authors)

#### Abstract

> **Introduction.** In the big data age, we have to deal with a tremendous amount of information, which can be collected from various types of sources. For information search systems such as Web search engines or online digital libraries, the collection of documents becomes larger and larger. For some queries, an information search system needs to retrieve a large number of documents. On the other hand, very often people are only willing to visit no more than a few top-ranked documents. Therefore, how to develop an information search system with desirable efficiency and effectiveness is a research problem.  
> **Method.** In this paper, we focus on the data fusion approach to information search, in which each component search model contributes a result and all the results are combined by a fusion algorithm. Through empirical study, we are able to find a feasible combination method that balances effectiveness and efficiency in the context of data fusion.  
> **Analysis.** It is a multi-optimisation problem that aims to balance effectiveness and efficiency. To support this, we need to understand how these two factors affect each other and to what extent.  
> **Results.** Using some groups of historical runs from TREC to carry out the experiment, we find that using much less information (e.g., less than 10% of the documents in the experiment), good efficiency is achievable with marginal loss on effectiveness.  
> **Conclusions.** We consider that the findings from our experiment are informative and this can be used as a guideline for providing more efficient search service in the big data environment.

## Introduction

In the big data age, we have to deal with a tremendous amount of information, which can be collected from various types of sources. For many information search systems, the corpora they use become larger and larger. A typical example is the Web. According to [worldwidewebsize](http://www.worldwidewebsize.com/), the indexed Web contains at least 4.64 billion pages as of 12April, 2015\. Some collections used in many information retrieval and Web search evaluation events such as TREC (the [Text REtrieval Conference](http://trec.nist.gov/), held annually by National Institute of Standard and Technology of the USA) are also very large. For example, _[ClueWeb09](http://lemurproject.org/clueweb09.php/)_ has over one billion documents and _[ClueWeb12](http://lemurproject.org/clueweb12.php/)_ has over 800 million documents.

The big data environment brings some challenges to information search. For some queries, an information search engine needs to retrieve a large number of documents. With very large number of documents, it is even more difficult for an information search engine to locate more useful and relevant information so as to satisfy users' information needs. To improve effectiveness of the results by locating more relevant document and ranking them on some top-ranked positions in the resultant lists, more and more complex and expensive search techniques have been explored and used. For example, when ranking Web documents for the given information need, Web search engines not only consider the relevance of the documents to the information need, they also take the authority of the Web sites that hold the Web pages into consideration.

Usually, the authority of Web sites is estimated by link analysis, which requires data about links ([Nunes, Ribeiro and Gabriel, 2013](#NRG13)) between large numbers of Web pages. Page rank ([Brin and Page, 1998](#BP98)) and HITS ([Kleinberg, 1999](#K99)) are two well-known algorithms for such a purpose. There are also many other methods such as entity detection, user log analysis for personalized preference, user feedback and query expansion, phrase recognition and structural analysis, knowledge-based approach for word correction and suggestion, and so on. Many of these data-intensive tasks are commonly used in Web search engines. On the other hand, efficiency, which concerns the time needed for the search system to do a search task, becomes a big problem because of the huge number of documents and related data involved and complex and expensive techniques used ([Baeza-Yates and Cambazoglu, 2014](#BC14);[Francis, Bai, Cambazoglu and Baeza-Yates, 2014](#Fal14)). This has to be considered when the response time of a search system reaches the level that might go beyond users' tolerance.

In this paper, we are going to address this within a particular type of information search system that is implemented through the fusion approach. This approach is popular and often referred to as _rank aggregation_ or _learn to rank_. Previous research shows that fusion is an attractive option on information search ([Wu, 2012](#Wu12); [Liu, 2011](#Liu11)).

Data fusion works as follows: instead of using one information search model, we use multiple search models working together for any search task. For a given query, all of the component search models search the same collection of documents and each of them contributes a ranked list of documents as a composite result. Then a selected data fusion algorithm is applied to all the results involved and the combined result is generated accordingly as the final result for the user. Usually we take all the documents from all component results for fusion because it is believed that the more documents we use, the more information we can obtain and, therefore, the better fused result we can obtain. Effectiveness is the only concern in almost all the cases. Figure 1 shows its structure with three search models.

<figure class="centre">![Figure1: Structure of a fusion-based information search system](p710fig1.png)

<figcaption>Figure 1: Structure of a fusion-based information search system</figcaption>

</figure>

In Figure 1, the first step is that the user issues a query to the search engine interface (Step 1), which forwards it to multiple search models (Step 2). Each of those search models works with the index files and the same document collection (Step 3) to obtain the result. After that, the models forward the results to the fusion algorithm (Step 4) and the fusion algorithm combines those results and transfers the fused result to the interface (Step 5). Finally, the result is presented to the user (Step 6). In Figure 1, all three search engines work with the same document collection and related index files. It is possible that each search model may work with a different document collection. This case is usually referred to as federated search ([Shokouhi and Si, 2011](#SS11)). In this paper, we focus on the scenario of data fusion with all search models working on the same document collection.

Data fusion has been extensively used in many information search tasks such as expert search ([Balog, Azzopardi and de Rijke, 2009](#BAD09)), blog opinion search ([Orimaye. Alhashmi and Siew, 2015](#OAS15)), and search for diversified results ([Santos, Macdonald and Ounis, 2012](#SMO12)), among others. In many information search tasks, a traditional search model like BM25 is not enough. A lot of other techniques have also been applied. Let us take Web search as an example. Many aspects including link analysis, personalized ranking of documents, diversified ranking of documents to let results cover more sub-topics, and so on, have been provided by many Web search engines ([Web search engine, 2015](#Wse15)). Traditional search models, such as BM25 or other alternatives, are just one part of the whole system. To combine those results from different ranking components, data fusion is required. In our experiments that use three groups of data from TREC, some of the information retrieval systems involved (such as uogTrA42, ICTNET11ADR3, srchvrs11b, uogTRA45Vm, ICTNET11ADR2, ivoryL2Rb, srchvrs12c09, uogTRA44xi) use BM25 as a component. Experimental results show that data fusion can improve performance over those component systems.

In the big data environment, we need to reconsider the whole process carefully. Compared with some other solutions, the data fusion approach is more complex because it runs multiple search models concurrently and an extra layer of fusion component is also necessary. It is more expensive in the sense that more resources and more time are required. Both effectiveness and efficiency become equally important aspects. This can be looked at from the sides of both user and system. First let us look at it from the user side. In some applications such as Web search, very often users want to find some, but not all, relevant documents. If the user finds some relevant pages, then it is very likely that s/he will stop looking for further relevant information ([Cossock and Zhang, 2006](#CZ06)). In this paper, we try to find solutions for such a situation. From the system side, we can deal with this in different ways. First of all, if a user has no interest in reading a lot of documents, then the search system does not need to retrieve too many of them in the first place. Secondly, if we consider this issue in the framework of data fusion, then we can deal with it in several ways. Among others, four of them are as follows:

*   If there are a lot of candidates for component search models, then we may just choose a subset of them for submitting results to the fusion algorithm.
*   We may let each search model to retrieve only a limited number of documents rather than all the documents that have a certain estimated probability of being relevant to the query.
*   For the fused result, we may generate a limited number of documents as the result.
*   Some data fusion methods need training data to determine weights for each search model or some parameters for the fusion algorithm. How much data we use for the training purpose can be investigated

For each aforementioned issue , we have different options of choosing how many documents or models or data. Generally speaking, if we use less information in those search models, then we may achieve higher efficiency, but with possible loss of effectiveness. Thus we need a balanced decision to addressing both of them at the same time. To our knowledge, these issues have not been addressed before. In this paper, we investigate the last two of the aforementioned issues.

The rest of this paper is organized as follows: in the next section we discuss some related work. This is followed by a presentation of the data fusion method used in this study and also some necessary background information. Related experimental settings and results are then reported and our conclusions are presented.

## Previous work

In information retrieval and Web search, many data fusion methods such as CombSum ([Fox and Shaw, 1994](#FS94)), CombMNZ and its variants ([Fox and Shaw, 1994](#FS94);[He and Wu, 2008](#HW08)), linear combination ([Vogt and Cottrell, 1999](#VC99); [Wu, 2012](#Wu12)), Borda count ([Aslam and Montague, 2001](#AM01)), Condorcet fusion ([Montague and Aslam, 2002](#MA02)),cluster-based fusion ([Kozorovitsky and Kurland, 2011](#KK11)), fusion-based implicit diversification method ([Liang and Ren and de Rijke, 2014](#LRD14)), and others have been proposed. Ng and Kantor ([2000](#NK00)) use a few variables to predict the effectiveness of data fusion (CombSum). However, almost all of them concern effectiveness of the fused result, while efficiency of the method has not been considered.

In some cases, fewer than all available documents are used for fusion. But the major reason of doing this is for some purpose other than improving efficiency.Two examples of this are by Lee ([1997](#Lee97)) and Spoerri ([2007](#S07)).

Lee ([1997](#Lee97)) carried out some experiments to compare the effectiveness of CombSum and CombMNZ. CombSum sums up the scores for each of the retrieved documents d, while CombMNZ multiplies this sum with an integer that indicates the number of results in which d obtains a score that is greater than 0\. He observed that in various cases that CombMNZ outperformed CombSum. Different numbers of documents were taken from all the results to carry out the fusion. He also explained why CombMNZ was a good fusion method.

Spoerri ([2007](#S07)) carried out some data fusion experiments with different numbers of documents that are taken from component results. It was found that performance is better when fusing a few top-ranked documents than by fusing more documents in the resultant lists. Some explanation to this phenomenon was given. In both cases, the purpose of researchers who use various numbers of documents for fusion is to try to understand the characteristics of data fusion methods CombSum and CombMNZ.

Linear combination ([Wu, 2012, Chapter 5](#Wu12)) is a good data fusion method because of its flexibility. Different weights can be assigned to different information search systems, so as to deal with various kinds of situations such as varying effectiveness among different search models. Then a weighted sum of all scores is given to any document involved. The key issue of linear combination is how to assign weights to all the component information search systems involved. Weights can be assigned in different ways including heuristic methods ([Wu, 2012, Chapter 5.1-5.3](#Wu12)), statistical methods such as multiple linear regression ([Wu, 2012, Chapter 5.4](#Wu12)), and optimization methods such as conjugate gradient ([Bartell, Cottrell and Belew 1994](#Bal94)), golden section search ([Vogt and Cottrell, 1999](#VC99)), and genetic algorithms ([Ghosh, Parui and Majumder, 2015](#GPM15)).

Score normalization is a related issue to data fusion in information retrieval. Score normalization can be divided into three categories: normalizing raw scores, converting ranking information into scores and mixed methods([Wu, 2012, Chapter4](#Wu12)). A number of methods have been proposed and investigated in each category. For normalizing raw scores, the successes of a specific method depends on how the raw scores are generated, which may be different from one system to another. For the second category, different curves such as the logistic function, the reciprocal function, the logarithmic function, the cubic function, and others have been investigated. Some of these functions are comparable in estimating ranking-score mapping.

The primary objective of this study is to find good fusion-based solutions for Web search in the big data search environment. Both effectiveness and efficiency are considered. Considering that linear combination with weights trained by multiple linear regression is very good, in this study we focus on this method. We would investigate the effect of different parameter settings to effectiveness and efficiency of this method.

## Data fusion and linear combination

In this section, we discuss some data fusion methods that will be used later in this paper and some related issues. Among different data fusion methods, CombSum, CombMNZ, and linear combination are commonly used in many data fusion experiments and system implementations.

Suppose there are _n_ information search systems ir<sub>i</sub> (1=i=n), and for a given query _q_ each of them retrieves a ranked list of _p_ documents for (1=k=p). For example, if there are five information search systems and a document _d_ obtains the scores of 0.4, 0.6, 0.6, 0.0, and 0.0 from them, then the final score of _d_ is 0.4+0.6+0.6=1.6 for CombSum and 1.6*3=4.8 for CombMNZ. Note that in this example three out of five scores are greater than 0.

The linear combination method uses the following formula to calculate score for every document _d_:

<figure class="centre">![Equation 1](p710eq1.png)</figure>

Here s<sub>i</sub>(d) is the score of document _d_ (normalized, see later for how to normalize scores) in result r<sub>i</sub> for (1=i=n), w<sub>i</sub> is the weight assigned to information search system ir<sub>i</sub>, and G(d) is the calculated global score of _d_. CombSum is a special form of the linear combination method in which all the weights w<sub>i</sub> sum to 1\. All the documents can be ranked according to their calculated scores.

A few different methods have been proposed for how to decide weights by using some training data. In this paper, we use a multiple linear regression based method. According to ([Wu, 2012, Chapter 5.4](#Wu12)), this method is effective. Suppose in the training data set, there are _n_ information search systems and _m_ queries, and for each query q<sub>k</sub> (1=k=m), each of the information search systems provides a result r<sub>i</sub> (1=i=n) that comprises a ranked list of _p_ documents (d<sub>1</sub>,d<sub>2</sub>,,d<sub>p</sub>). with associated normalized scores s = (s<sup>k</sup><sub>i1</sub>, s<sup>k</sup><sub>i2</sub>, ...,s<sup>k</sup><sub>ip</sub>). All the documents involved are judged by human assessors. That is to say, we know which document is relevant or non-relevant to which query. y<sup>k</sup><sub style=" margin:0 0 0 -8px;">j</sub> =1 means that document d<sub>j</sub> is relevant to query q<sub>k</sub> and y<sup>k</sup><sub style=" margin:0 0 0 -8px;">j</sub> =0 means that document d<sub>j</sub> is non-relevant to query q<sub>k</sub>. Thus multiple linear regression can be used to minimize the least squares of the difference between the estimated scores of all documents by linear combination (![eq](p710image015.png)) and the judged scores of those documents ( y<sup>k</sup><sub style="margin:0 0 0 -8px;">j</sub> ), or _u_ in the following equation:

<figure class="centre">![Equation 2](p710eq2.png)</figure>

where ![eq](p710image017.png) , ![eq](p710image018.png) ,?, ![eq](p710image019.png) are parameters that need to be determined. These estimated values are used as weights (w<sub>1</sub>= ![eq](./p710image018.png),?,w<sub>n</sub>= ![eq](p710image019.png)) in the fusion process.

In this method, every document in ranked-lists is an observable object. Scores from component systems and from corresponding relevance judgment are elements. One characteristic of multiple linear regression for weights assignment is it treats all the documents equally and does not distinguish documents at different ranking positions. This method is good when the resultant lists are short or medium. However, when the resultant lists are very long, the method may not be very appropriate; for example, in Web search. This is because a list includes many documents but only the top-ranked ones are important. When paying equal attention to documents at all positions, the estimation is equally accurate for all the documents involved. Considering that what users really need is good results only in the top portion, and using fewer documents for training means higher efficiency, we may take some top-ranked documents, rather than the whole list, for the training purpose. Even if such a measure may not be helpful for performance improvement, it surely will be helpful for speeding up the training process.

Therefore, we divide all the documents in a result into three categories based on their rankings: _important_, _average_ and _ignorable_. Different importance factors are set to documents in different categories for regression analysis. For the ignorable group, the importance factor is always zero in this study. For the other two categories of documents, we try different combinations to find good solutions. Importance factor f<sub>1</sub>, is assigned to group I (I for important) and importance factor f<sub>a</sub> is assigned to group A (A for average). We let f<sub>1</sub> be larger than f<sub>a</sub> so that we can pay more attention to the documents in group I. This causes a bias on top-ranked documents and their coefficients for regression obtained is more accurate.

In practice, different f<sub>i</sub> and f<sub>a</sub> can be used. One extreme situation is that f<sub>a</sub> can be set to zero, which means documents in group Average are also ignored, the same as the ignorable group. The other extreme situation is that f<sub>i</sub> and f<sub>a</sub> are set the same value. Then all the documents in these two groups are treated equally. The above discussion motivates the following quantity of the least square estimates:

<figure class="centre">![Equation 3](p710eq3.png)</figure>

The meanings of these parameters are the same as in Equation 2.

The raw scores provided by different component search systems are based on different search models, so they are not comparable. Score normalization is required for those results to be ready for fusion. A varietal reciprocal function of rank is used in this study. Suppose that d<sub>1</sub>, d<sub>2</sub>, ..., d<sub>t</sub> are a ranked list of documents whose ranks are r<sub>1</sub>, r<sub>2</sub>, ..., r<sub>t</sub> respectively. The scores are normalized by s<sub>i</sub>=1/(r<sub>i</sub>+60), 1=i=t, which decrease very rapidly with rank ([Cormack, Clarke and Buettcher, 2009](#Cal09); [Lillis, Toolan, Collier and Dunnion, 2006](#Lal06)). According to ([Cormack, _et al._, 2009](#Cal09)), scores generated by this function is good. A constant of 60 is used to reduce the impact of a few documents at the highest ranks.

## Experiments

The purpose of this empirical study is to investigate both effectiveness and efficiency of the linear combination method. Three groups of historical TREC data are used in the experiment. They are runs submitted to the _ad hoc_ task of the 2010, 2011 and 2012 Web tracks. In the three successive years between 2010 and 2012, a very large collection of documents _ClueWeb09_ was used. Every run submitted includes up to 10,000 documents for each query. In each year group, we select eight top runs that are submitted by different participants. Their information is summarized in Table 1.

<table class="center"><caption>  
Table 1: Information on top 8 runs in the Web track of TREC between 2010-2012 (figures in parentheses are their performance values measured by average precision over all relevant documents)</caption>

<tbody>

<tr>

<th>2010 Web Track</th>

<th>2011 Web Track</th>

<th>2012 Web Track</th>

</tr>

<tr>

<td>irra10b (0.1329)</td>

<td>DFalah11 (0.0794)</td>

<td>DFalah12 (0.1203)</td>

</tr>

<tr>

<td>IvoryL2Rb (0.1333)</td>

<td>ICTNET11ADR3 (0.1746)</td>

<td>ICTNET12ADR2 (0.0783)</td>

</tr>

<tr>

<td>msrsv3 (0.0822)</td>

<td>msrsv2011a3 (0.1720)</td>

<td>irra12c (0.1528)</td>

</tr>

<tr>

<td>THUIR10QaHt (0.1123)</td>

<td>srchvrs11b (0.1098)</td>

<td>QUTparaBline (0.1173)</td>

</tr>

<tr>

<td>UAMSA10mSF30 (0.0429)</td>

<td>UAmsM705tiLS (0.0852)</td>

<td>Qutwb (0.1307)</td>

</tr>

<tr>

<td>UMa10IASF (0.0804)</td>

<td>uogTrA45Vm (0.2025)</td>

<td>srchvrs12c09 (0.1256)</td>

</tr>

<tr>

<td>umassSDMW (0.1482)</td>

<td>UWatMDSqlt (0.1349)</td>

<td>uogTrA44xi (0.2123)</td>

</tr>

<tr>

<td>uogTrA42 (0.1271)</td>

<td>uwBAadhoc (0.0785)</td>

<td>utw2012fc1 (0.0610)</td>

</tr>

</tbody>

</table>

We consider that these results provide a good platform to test data fusion methods for our purpose because of the relatively large number of documents involved in each result and the huge number of documents in the whole collection. The reciprocal function is used to convert rankings to normalized scores for all the documents involved in the experiment. To make the results more reliable, we use the five-fold cross validation method ([Kohavi, 1995](#K95))to test the fusion method. In a year group, all fifty queries are divided into five groups of equal size (1-10, 11-20, 21-30, 31-40, and 41-50). Four groups of them are used as training data to obtain weights for all the search systems involved, and the remaining one is used for fusion. All five groups are tested in such a way. A number of commonly used metrics are used for retrieval evaluation ([Baeza-Yates and Ribeiro-Neto, 2011, Chapter 4](#BR11); [Clough and Sanderson, 2013](#CS13)). They are average precision over all relevant documents (AP), recall-level precision (RP), precision at 10 document levels (P@10), and normalized discount cumulative gain at 20 document level (NDCG@20). Apart from linear combination, we also test CombSum and CombMNZ for comparison.

In the following four subsections we report four groups of experimental results. The first three groups concern effectiveness of the fused result, each of which uses different settings; while the fourth group concerns efficiency.

### Experiment 1

Linear combination needs some training data to set weights for all the component search systems involved. The main purpose of this experiment is to answer the question: If we use less training data for weights assignment, how does it affect fusion results? Therefore, in this experiment, we use 100 to 1000 top-ranked documents in the training process for obtaining weights, then fuse all the available documents by linear combination. The baseline, LC-all, uses all 10000 documents available for training. In the fusion process, all 10000 documents are used for all the data fusion methods involved.

Tables 2-4 show the results, in which LC-all denotes linear combination with all the 10,000 documents available for training, while LC-x denotes linear combination with x top-ranked documents for training. For both CombSum and CombMNZ, all 10000 documents are used for fusion.

Compared with LC-all, LC-x may go either way in different settings. Generally speaking, using fewer documents in the training process does not affect fusion effectiveness very much. Even when using as few as 100 top-ranked documents (1 percent of all the documents available) for training, its fusion effectiveness is still comparable to that of using all the documents. This is the major observation point of this experiment.

Some other observations are also made. Compared with the average of all component results, data fusion methods perform much better. Compared with the best component result, all data fusion methods perform much better if measured by AP or RP (the only exception happens to CombMNZ in the year group of 2011 and measured by RP). Let us take AP as an example. The improvement rates of LC-1000 over the best component results are 70.99%, 38.17%, and 34.20% in the three data sets. But if measured by two other metrics RR and P@10, the fused results are comparable with the best component result. This suggests that data fusion methods are more favourable to system-oriented metrics such as AP and RP than to user-oriented metrics such as RR and P@10\. Comparing CombSum with CombMNZ, we find thatCombSum is very likely better than CombMNZ. But sometimes the conclusion is not consistent across different measures.

<table class="center"><caption>  
Table 2: Fusion effectiveness of linear combination in which weights are obtained by using partial training data (the 2010 year group)</caption>

<tbody>

<tr>

<th>Method</th>

<th>AP</th>

<th>RP</th>

<th>RR</th>

<th>P@10</th>

<th>NDCG@20</th>

</tr>

<tr>

<td>Best</td>

<td style="text-align:center;">0.1482</td>

<td style="text-align:center;">0.2067</td>

<td style="text-align:center;">0.6581</td>

<td style="text-align:center;">0.4979</td>

<td style="text-align:center;">0.2932</td>

</tr>

<tr>

<td>Average</td>

<td style="text-align:center;">0.1074</td>

<td style="text-align:center;">0.1639</td>

<td style="text-align:center;">0.5631</td>

<td style="text-align:center;">0.3794</td>

<td style="text-align:center;">0.2234</td>

</tr>

<tr>

<td>CombSum</td>

<td style="text-align:center;">0.2520</td>

<td style="text-align:center;">0.2954</td>

<td style="text-align:center;">0.7281</td>

<td style="text-align:center;">0.4729</td>

<td style="text-align:center;">0.3099</td>

</tr>

<tr>

<td>CombMNZ</td>

<td style="text-align:center;">0.2310</td>

<td style="text-align:center;">0.2766</td>

<td style="text-align:center;">0.7146</td>

<td style="text-align:center;">0.4896</td>

<td style="text-align:center;">0.2992</td>

</tr>

<tr>

<td>LC-all</td>

<td style="text-align:center;">0.2545</td>

<td style="text-align:center;">0.3042</td>

<td style="text-align:center;">0.7363</td>

<td style="text-align:center;">0.4792</td>

<td style="text-align:center;">0.3055</td>

</tr>

<tr>

<td>LC-100</td>

<td style="text-align:center;">**0.2410**</td>

<td style="text-align:center;">**0.2867**</td>

<td style="text-align:center;">0.6980</td>

<td style="text-align:center;">0.5063</td>

<td style="text-align:center;">0.3149</td>

</tr>

<tr>

<td style="text-align:center;"> </td>

<td style="text-align:center;">(-5.30%)</td>

<td style="text-align:center;">(-5.75%)</td>

<td style="text-align:center;">(-5.20%)</td>

<td style="text-align:center;">(+5.66%)</td>

<td style="text-align:center;">(+3.08%)</td>

</tr>

<tr>

<td>LC-200</td>

<td style="text-align:center;">0.2517</td>

<td style="text-align:center;">0.2994</td>

<td style="text-align:center;">0.7370</td>

<td style="text-align:center;">0.4896</td>

<td style="text-align:center;">0.3089</td>

</tr>

<tr>

<td style="text-align:center;"> </td>

<td style="text-align:center;">(-1.10%)</td>

<td style="text-align:center;">(-1.58%)</td>

<td style="text-align:center;">(+0.10%)</td>

<td style="text-align:center;">(+2.17%)</td>

<td style="text-align:center;">(+1.12%)</td>

</tr>

<tr>

<td>LC-300</td>

<td style="text-align:center;">0.2539</td>

<td style="text-align:center;">0.3030</td>

<td style="text-align:center;">0.7457</td>

<td style="text-align:center;">0.4813</td>

<td style="text-align:center;">0.3095</td>

</tr>

<tr>

<td style="text-align:center;"> </td>

<td style="text-align:center;">(-0.24%)</td>

<td style="text-align:center;">(-0.39%)</td>

<td style="text-align:center;">(+1.28%)</td>

<td style="text-align:center;">(+0.44%)</td>

<td style="text-align:center;">(+1.32%)</td>

</tr>

<tr>

<td>LC-400</td>

<td style="text-align:center;">0.2546</td>

<td style="text-align:center;">0.3046</td>

<td style="text-align:center;">0.7460</td>

<td style="text-align:center;">0.4708</td>

<td style="text-align:center;">0.3075</td>

</tr>

<tr>

<td style="text-align:center;"> </td>

<td style="text-align:center;">(+0.04%)</td>

<td style="text-align:center;">(+0.13%)</td>

<td style="text-align:center;">(+1.32%)</td>

<td style="text-align:center;">(-1.75%)</td>

<td style="text-align:center;">(+0.66%)</td>

</tr>

<tr>

<td>LC-500</td>

<td style="text-align:center;">0.2545</td>

<td style="text-align:center;">0.3040</td>

<td style="text-align:center;">0.7427</td>

<td style="text-align:center;">0.4750</td>

<td style="text-align:center;">0.3057</td>

</tr>

<tr>

<td style="text-align:center;"> </td>

<td style="text-align:center;">0.00%</td>

<td style="text-align:center;">(-0.07%)</td>

<td style="text-align:center;">(+0.87%)</td>

<td style="text-align:center;">(-0.88%)</td>

<td style="text-align:center;">(+0.07%)</td>

</tr>

<tr>

<td>LC-600</td>

<td style="text-align:center;">0.2546</td>

<td style="text-align:center;">0.3041</td>

<td style="text-align:center;">0.7423</td>

<td style="text-align:center;">0.4750</td>

<td style="text-align:center;">0.3059</td>

</tr>

<tr>

<td style="text-align:center;"> </td>

<td style="text-align:center;">-0.04%</td>

<td style="text-align:center;">(-0.03%)</td>

<td style="text-align:center;">(+0.81%)</td>

<td style="text-align:center;">(-0.88%)</td>

<td style="text-align:center;">(+0.12%)</td>

</tr>

<tr>

<td>LC-700</td>

<td style="text-align:center;">0.2547</td>

<td style="text-align:center;">0.3053</td>

<td style="text-align:center;">0.7425</td>

<td style="text-align:center;">0.4833</td>

<td style="text-align:center;">0.3056</td>

</tr>

<tr>

<td style="text-align:center;"> </td>

<td style="text-align:center;">(+0.08%)</td>

<td style="text-align:center;">(+0.36%)</td>

<td style="text-align:center;">(+0.84%)</td>

<td style="text-align:center;">(+0.86%)</td>

<td style="text-align:center;">(+0.03%)</td>

</tr>

<tr>

<td>LC-800</td>

<td style="text-align:center;">0.2548</td>

<td style="text-align:center;">0.3061</td>

<td style="text-align:center;">0.7427</td>

<td style="text-align:center;">0.4813</td>

<td style="text-align:center;">0.3057</td>

</tr>

<tr>

<td style="text-align:center;"> </td>

<td style="text-align:center;">(+0.12%)</td>

<td style="text-align:center;">(+0.62%)</td>

<td style="text-align:center;">(+0.87%)</td>

<td style="text-align:center;">(+0.44%)</td>

<td style="text-align:center;">(+0.08%)</td>

</tr>

<tr>

<td>LC-900</td>

<td style="text-align:center;">0.2549</td>

<td style="text-align:center;">0.3056</td>

<td style="text-align:center;">0.7404</td>

<td style="text-align:center;">0.4813</td>

<td style="text-align:center;">0.3063</td>

</tr>

<tr>

<td style="text-align:center;"> </td>

<td style="text-align:center;">(+0.16%)</td>

<td style="text-align:center;">(+0.46%)</td>

<td>(+0.56%)</td>

<td style="text-align:center;">(+0.44%)</td>

<td style="text-align:center;">(+0.27%)</td>

</tr>

<tr>

<td>LC-1000</td>

<td style="text-align:center;">0.2549</td>

<td style="text-align:center;">0.3056</td>

<td style="text-align:center;">0.7365</td>

<td style="text-align:center;">0.4813</td>

<td style="text-align:center;">0.3051</td>

</tr>

<tr>

<td style="text-align:center;"> </td>

<td style="text-align:center;">(+0.16%)</td>

<td style="text-align:center;">(+0.46%)</td>

<td style="text-align:center;">(+0.03%)</td>

<td style="text-align:center;">+0.44%)</td>

<td style="text-align:center;">(-0.11%)</td>

</tr>

<tr>

<td colspan="6">LC-all denotes training with all 10000 documents and LC-x denotes training with top x documents, the figures in bold indicate that they are different significantly from the one obtained from LC-all at a significance level of 0.05</td>

</tr>

</tbody>

</table>

<table class="center"><caption>  
Table 3: Fusion effectiveness of linear combination in which weights are obtained by using partial training data (the 2011 year group)</caption>

<tbody>

<tr>

<th>Method</th>

<th>AP</th>

<th>RP</th>

<th>RR</th>

<th>P@10</th>

<th>NDCG@20</th>

</tr>

<tr>

<td>Best</td>

<td style="text-align:center;">0.2025</td>

<td style="text-align:center;">0.2377</td>

<td style="text-align:center;">0.6479</td>

<td style="text-align:center;">0.3880</td>

<td style="text-align:center;">0.3052</td>

</tr>

<tr>

<td>Average</td>

<td style="text-align:center;">0.1296</td>

<td style="text-align:center;">0.1800</td>

<td style="text-align:center;">0.5548</td>

<td style="text-align:center;">0.3350</td>

<td style="text-align:center;">0.2393</td>

</tr>

<tr>

<td>CombMNZ</td>

<td style="text-align:center;">0.2133</td>

<td style="text-align:center;">0.2366</td>

<td style="text-align:center;">0.6442</td>

<td style="text-align:center;">0.3740</td>

<td style="text-align:center;">0.2502</td>

</tr>

<tr>

<td>CombSum</td>

<td style="text-align:center;">0.2517</td>

<td style="text-align:center;">0.2757</td>

<td style="text-align:center;">0.6376</td>

<td style="text-align:center;">0.400</td>

<td style="text-align:center;">0.2772</td>

</tr>

<tr>

<td>LC-all</td>

<td style="text-align:center;">0.2802</td>

<td style="text-align:center;">0.3008</td>

<td style="text-align:center;">0.6718</td>

<td style="text-align:center;">0.4340</td>

<td style="text-align:center;">0.3137</td>

</tr>

<tr>

<td>LC-100</td>

<td style="text-align:center;">0.2783</td>

<td style="text-align:center;">0.2962</td>

<td style="text-align:center;">0.6600</td>

<td style="text-align:center;">0.4360</td>

<td style="text-align:center;">0.3110</td>

</tr>

<tr>

<td style="text-align:center;"> </td>

<td style="text-align:center;">(-0.68%)</td>

<td style="text-align:center;">(-1.53%)</td>

<td style="text-align:center;">(-1.76%)</td>

<td style="text-align:center;">(+0.46%)</td>

<td style="text-align:center;">(-0.86%)</td>

</tr>

<tr>

<td>LC-200</td>

<td style="text-align:center;">0.2801</td>

<td style="text-align:center;">0.2986</td>

<td style="text-align:center;">0.6717</td>

<td style="text-align:center;">0.4360</td>

<td style="text-align:center;">0.3143</td>

</tr>

<tr>

<td style="text-align:center;"> </td>

<td style="text-align:center;">(-0.04%)</td>

<td style="text-align:center;">(-0.73%)</td>

<td style="text-align:center;">(-0.01%)</td>

<td style="text-align:center;">(+0.46%)</td>

<td style="text-align:center;">(+0.19%)</td>

</tr>

<tr>

<td>LC-500</td>

<td style="text-align:center;">0.2803</td>

<td style="text-align:center;">0.2994</td>

<td style="text-align:center;">0.6725</td>

<td style="text-align:center;">0.4340</td>

<td style="text-align:center;">0.3105</td>

</tr>

<tr>

<td style="text-align:center;"> </td>

<td style="text-align:center;">(+0.04%)</td>

<td style="text-align:center;">(-0.47%)</td>

<td style="text-align:center;">(+0.10%)</td>

<td style="text-align:center;">(?0.00%)</td>

<td style="text-align:center;">(-1.03%)</td>

</tr>

<tr>

<td>LC-1000</td>

<td style="text-align:center;">0.2804</td>

<td style="text-align:center;">0.3003</td>

<td style="text-align:center;">0.6718</td>

<td style="text-align:center;">0.4360</td>

<td style="text-align:center;">0.3107</td>

</tr>

<tr>

<td style="text-align:center;"> </td>

<td style="text-align:center;">(+0.07%)</td>

<td style="text-align:center;">(-0.17%)</td>

<td style="text-align:center;">(?0.00%)</td>

<td style="text-align:center;">(+0.46%)</td>

<td style="text-align:center;">(-0.97%)</td>

</tr>

<tr>

<td colspan="6">LC-all denotes training with all 10000 documents and LC-x denotes training with top x documents, the figures in bold indicate that they are different significantly from the one obtained from LC-all at a significance level of 0.05</td>

</tr>

</tbody>

</table>

<table class="center"><caption>  
Table 4: Fusion effectiveness of linear combination in which weights are obtained by using partial training data (the 2012 year group)</caption>

<tbody>

<tr>

<th>Method</th>

<th>AP</th>

<th>RP</th>

<th>RR</th>

<th>P@10</th>

<th>NDCG@20</th>

</tr>

<tr>

<td>Best</td>

<td style="text-align:center;">0.2123</td>

<td style="text-align:center;">0.2583</td>

<td style="text-align:center;">0.6515</td>

<td style="text-align:center;">0.5020</td>

<td style="text-align:center;">0.2383</td>

</tr>

<tr>

<td>Average</td>

<td style="text-align:center;">0.1248</td>

<td style="text-align:center;">0.1823</td>

<td style="text-align:center;">0.5381</td>

<td style="text-align:center;">0.3588</td>

<td style="text-align:center;">0.1634</td>

</tr>

<tr>

<td>CombMNZ</td>

<td style="text-align:center;">0.2397</td>

<td style="text-align:center;">0.2932</td>

<td style="text-align:center;">0.6718</td>

<td style="text-align:center;">0.4620</td>

<td style="text-align:center;">0.2248</td>

</tr>

<tr>

<td>CombSum</td>

<td style="text-align:center;">0.2732</td>

<td style="text-align:center;">0.3073</td>

<td style="text-align:center;">0.6901</td>

<td style="text-align:center;">0.4760</td>

<td style="text-align:center;">0.2260</td>

</tr>

<tr>

<td>LC-all</td>

<td style="text-align:center;">0.2827</td>

<td style="text-align:center;">0.3114</td>

<td style="text-align:center;">0.6530</td>

<td style="text-align:center;">0.4940</td>

<td style="text-align:center;">0.2259</td>

</tr>

<tr>

<td>LC-100</td>

<td style="text-align:center;">0.2797</td>

<td style="text-align:center;">0.3017</td>

<td style="text-align:center;">0.6680</td>

<td style="text-align:center;">0.4860</td>

<td style="text-align:center;">0.2280</td>

</tr>

<tr>

<td style="text-align:center;"> </td>

<td style="text-align:center;">(-1.06%)</td>

<td style="text-align:center;">(-3.11%)</td>

<td style="text-align:center;">(+2.30%)</td>

<td style="text-align:center;">(-1.62%)</td>

<td style="text-align:center;">(+0.93%)</td>

</tr>

<tr>

<td>LC-200</td>

<td style="text-align:center;">0.2841</td>

<td style="text-align:center;">0.3140</td>

<td style="text-align:center;">0.6699</td>

<td style="text-align:center;">**0.4800**</td>

<td style="text-align:center;">0.2279</td>

</tr>

<tr>

<td style="text-align:center;"> </td>

<td style="text-align:center;">(+0.50%)</td>

<td style="text-align:center;">(+0.83%)</td>

<td style="text-align:center;">(+2.59%)</td>

<td style="text-align:center;">(-2.83%)</td>

<td style="text-align:center;">(+0.87%)</td>

</tr>

<tr>

<td>LC-500</td>

<td style="text-align:center;">0.2852</td>

<td style="text-align:center;">0.3175</td>

<td style="text-align:center;">0.6703</td>

<td style="text-align:center;">**0.4820**</td>

<td style="text-align:center;">0.2242</td>

</tr>

<tr>

<td style="text-align:center;"> </td>

<td style="text-align:center;">(+0.88%)</td>

<td style="text-align:center;">(+1.96%)</td>

<td style="text-align:center;">(+2.65%)</td>

<td style="text-align:center;">(-2.43%)</td>

<td style="text-align:center;">(-0.77%)</td>

</tr>

<tr>

<td>LC-1000</td>

<td style="text-align:center;">0.2848</td>

<td style="text-align:center;">0.3170</td>

<td style="text-align:center;">0.6674</td>

<td style="text-align:center;">0.4860</td>

<td style="text-align:center;">0.2248</td>

</tr>

<tr>

<td style="text-align:center;"> </td>

<td style="text-align:center;">(+0.74%)</td>

<td style="text-align:center;">(+1.80%)</td>

<td style="text-align:center;">(+2.21%)</td>

<td style="text-align:center;">(-1.62%)</td>

<td style="text-align:center;">(-0.48%)</td>

</tr>

<tr>

<td colspan="6">LC-all denotes training with all 10000 documents and LC-x denotes training with top x documents, the figures in bold indicate that they are different significantly from the one obtained from LC-all at a significance level of 0.05</td>

</tr>

</tbody>

</table>

### Experiment 2

In this experiment, we use fewer documents for both training and fusion. For the training process, the top 1000 ranked documents (10% of all available documents) in all component results are used for multiple linear regression to obtain weights. For results fusion, linear combination is used with different number of documents from top 100 (1% of all 10000 documents), 200 (2%), 300 (3%),?, to 1000 (10%), as well as all the documents available (10000). The results are shown in Tables 5, 6 and 7 for three year groups, respectively. In these tables, LC-all denotes linear combination,which uses all 10000 documents for both weights assignment training and results fusion; LC-x, where x is a number, denotes linear combination that uses top-1000 documents for weights assignment training and uses x top-ranked documents for fusion. The figures in parentheses are the improvement of the method over LC-all and the figures in bold indicate that they are different from LC-all at a significance level of 0.05\. From these tables, we can see that compared with using all 10000 documents for training and fusion(LC-all), using 100 to 1000 top-ranked documents for training and fusion can achieve comparable effectiveness. In some cases, the differences between them are small and not significant.

<table class="center"><caption>  
Table 5: Fusion effectiveness with top-ranked documents in the 2010 year group (top 1000 documents are used in training for weight assignment)LC-all denotes linear combination with all 10000 documents for fusion, LC-x, denotes linear combination with x top-ranked documents for fusion)</caption>

<tbody>

<tr>

<th>Method</th>

<th>AP</th>

<th>RP</th>

<th>RR</th>

<th>P@10</th>

<th>NDCG@20</th>

</tr>

<tr>

<td>Best</td>

<td style="text-align:center;">0.1482</td>

<td style="text-align:center;">0.2067</td>

<td style="text-align:center;">0.6581</td>

<td style="text-align:center;">0.4979</td>

<td style="text-align:center;">0.2932</td>

</tr>

<tr>

<td>Average</td>

<td style="text-align:center;">0.1074</td>

<td style="text-align:center;">0.1639</td>

<td style="text-align:center;">0.5631</td>

<td style="text-align:center;">0.3794</td>

<td style="text-align:center;">0.2234</td>

</tr>

<tr>

<td>LC-all</td>

<td style="text-align:center;">0.2545</td>

<td style="text-align:center;">0.3042</td>

<td style="text-align:center;">0.7363</td>

<td style="text-align:center;">0.4792</td>

<td style="text-align:center;">0.3055</td>

</tr>

<tr>

<td>LC-100</td>

<td style="text-align:center;">**0.2342**</td>

<td style="text-align:center;">0.2992</td>

<td style="text-align:center;">0.7343</td>

<td style="text-align:center;">0.5042</td>

<td style="text-align:center;">0.3108</td>

</tr>

<tr>

<td style="text-align:center;"> </td>

<td style="text-align:center;">(-7.98%)</td>

<td style="text-align:center;">(-1.64%)</td>

<td style="text-align:center;">(-0.27%)</td>

<td style="text-align:center;">(+5.22%)</td>

<td style="text-align:center;">(+1.74%)</td>

</tr>

<tr>

<td>LC-200</td>

<td style="text-align:center;">**0.2472**</td>

<td style="text-align:center;">0.3073</td>

<td style="text-align:center;">0.7237</td>

<td style="text-align:center;">0.4833</td>

<td style="text-align:center;">0.303</td>

</tr>

<tr>

<td style="text-align:center;"> </td>

<td style="text-align:center;">(-2.87%)</td>

<td style="text-align:center;">(+1.02%)</td>

<td style="text-align:center;">(-1.71%)</td>

<td style="text-align:center;">(+0.86%)</td>

<td style="text-align:center;">(-0.82%)</td>

</tr>

<tr>

<td>LC-300</td>

<td style="text-align:center;">**0.2486**</td>

<td style="text-align:center;">0.3062</td>

<td style="text-align:center;">0.7350</td>

<td style="text-align:center;">0.4750</td>

<td style="text-align:center;">0.3044</td>

</tr>

<tr>

<td style="text-align:center;"> </td>

<td style="text-align:center;">(-2.32%)</td>

<td style="text-align:center;">(+0.66%)</td>

<td style="text-align:center;">(-0.18%)</td>

<td style="text-align:center;">(-0.88%)</td>

<td style="text-align:center;">(-0.35%)</td>

</tr>

<tr>

<td>LC-400</td>

<td style="text-align:center;">**0.2498**</td>

<td style="text-align:center;">0.3037</td>

<td style="text-align:center;">0.7346</td>

<td style="text-align:center;">0.4750</td>

<td style="text-align:center;">0.3027</td>

</tr>

<tr>

<td style="text-align:center;"> </td>

<td style="text-align:center;">(-1.85%)</td>

<td style="text-align:center;">(-0.16%)</td>

<td style="text-align:center;">(-0.23%)</td>

<td style="text-align:center;">(-0.88%)</td>

<td style="text-align:center;">(-0.92%)</td>

</tr>

<tr>

<td>LC-500</td>

<td style="text-align:center;">**0.2513**</td>

<td style="text-align:center;">0.3035</td>

<td style="text-align:center;">0.7356</td>

<td style="text-align:center;">0.4792</td>

<td style="text-align:center;">0.3032</td>

</tr>

<tr>

<td style="text-align:center;"> </td>

<td style="text-align:center;">(-1.26%)</td>

<td style="text-align:center;">(-0.23%)</td>

<td style="text-align:center;">(-0.10%)</td>

<td style="text-align:center;">(?0.00%)</td>

<td style="text-align:center;">(-0.75%)</td>

</tr>

<tr>

<td>LC-600</td>

<td style="text-align:center;">**0.2521**</td>

<td style="text-align:center;">0.3050</td>

<td style="text-align:center;">0.7340</td>

<td style="text-align:center;">0.4771</td>

<td style="text-align:center;">**0.3017**</td>

</tr>

<tr>

<td style="text-align:center;"> </td>

<td style="text-align:center;">(-0.94%)</td>

<td style="text-align:center;">(+0.26%)</td>

<td style="text-align:center;">(-0.31%)</td>

<td style="text-align:center;">(-0.44%)</td>

<td style="text-align:center;">(-1.24%)</td>

</tr>

<tr>

<td>LC-700</td>

<td style="text-align:center;">**0.2527**</td>

<td style="text-align:center;">0.3052</td>

<td style="text-align:center;">0.7340</td>

<td style="text-align:center;">0.4750</td>

<td style="text-align:center;">0.3028</td>

</tr>

<tr>

<td style="text-align:center;"> </td>

<td style="text-align:center;">(-0.71%)</td>

<td style="text-align:center;">(+0.33%)</td>

<td style="text-align:center;">(-0.31%)</td>

<td style="text-align:center;">(-0.88%)</td>

<td style="text-align:center;">(-0.86%)</td>

</tr>

<tr>

<td>LC-800</td>

<td style="text-align:center;">0.2532</td>

<td style="text-align:center;">0.3054</td>

<td style="text-align:center;">0.7365</td>

<td style="text-align:center;">0.4792</td>

<td style="text-align:center;">0.3031</td>

</tr>

<tr>

<td style="text-align:center;"> </td>

<td style="text-align:center;">(-0.51%)</td>

<td style="text-align:center;">(+0.39%)</td>

<td style="text-align:center;">(+0.03%)</td>

<td style="text-align:center;">(?0.00%)</td>

<td style="text-align:center;">(-0.77%)</td>

</tr>

<tr>

<td>LC-900</td>

<td style="text-align:center;">0.2534</td>

<td style="text-align:center;">0.3046</td>

<td style="text-align:center;">0.7365</td>

<td style="text-align:center;">0.4771</td>

<td style="text-align:center;">0.3027</td>

</tr>

<tr>

<td style="text-align:center;"> </td>

<td style="text-align:center;">(-0.43%)</td>

<td style="text-align:center;">(+0.13%)</td>

<td style="text-align:center;">(+0.03%)</td>

<td style="text-align:center;">(-0.44%)</td>

<td style="text-align:center;">(-0.92%)</td>

</tr>

<tr>

<td>LC-1000</td>

<td style="text-align:center;">0.2534</td>

<td style="text-align:center;">0.3047</td>

<td style="text-align:center;">0.7365</td>

<td style="text-align:center;">0.4792</td>

<td style="text-align:center;">0.3034</td>

</tr>

<tr>

<td style="text-align:center;"> </td>

<td style="text-align:center;">(-0.43%)</td>

<td style="text-align:center;">(+0.16%)</td>

<td style="text-align:center;">(+0.03%)</td>

<td style="text-align:center;">(?0.00%)</td>

<td style="text-align:center;">(-0.67%)</td>

</tr>

</tbody>

</table>

<table class="center"><caption>  
Table 6: Fusion effectiveness with top-ranked documents in the 2011 year group (top 1000 documents are used for training)</caption>

<tbody>

<tr>

<th>Method</th>

<th>AP</th>

<th>RP</th>

<th>RR</th>

<th>P@10</th>

<th>NDCG@20</th>

</tr>

<tr>

<td>Best</td>

<td style="text-align:center;">0.2025</td>

<td style="text-align:center;">0.2377</td>

<td style="text-align:center;">0.6479</td>

<td style="text-align:center;">0.3880</td>

<td style="text-align:center;">0.3052</td>

</tr>

<tr>

<td>Average</td>

<td style="text-align:center;">0.1296</td>

<td style="text-align:center;">0.1800</td>

<td style="text-align:center;">0.5548</td>

<td style="text-align:center;">0.3350</td>

<td style="text-align:center;">0.2393</td>

</tr>

<tr>

<td>LC-all</td>

<td style="text-align:center;">0.2802</td>

<td style="text-align:center;">0.3008</td>

<td style="text-align:center;">0.6718</td>

<td style="text-align:center;">0.4340</td>

<td style="text-align:center;">0.3137</td>

</tr>

<tr>

<td>LC-100</td>

<td style="text-align:center;">**0.2686**</td>

<td style="text-align:center;">0.2959</td>

<td style="text-align:center;">0.6694</td>

<td style="text-align:center;">0.4260</td>

<td style="text-align:center;">0.3098</td>

</tr>

<tr>

<td style="text-align:center;"> </td>

<td style="text-align:center;">(-4.14%)</td>

<td style="text-align:center;">(-1.63%)</td>

<td style="text-align:center;">(-0.36%)</td>

<td style="text-align:center;">(-1.84%)</td>

<td style="text-align:center;">(-1.23%)</td>

</tr>

<tr>

<td>LC-200</td>

<td style="text-align:center;">0.2769</td>

<td style="text-align:center;">**0.2952**</td>

<td style="text-align:center;">0.6703</td>

<td style="text-align:center;">0.4340</td>

<td style="text-align:center;">0.3098</td>

</tr>

<tr>

<td style="text-align:center;"> </td>

<td style="text-align:center;">(-1.18%)</td>

<td style="text-align:center;">(-1.86%)</td>

<td style="text-align:center;">(-0.22%)</td>

<td style="text-align:center;">(?0.00%)</td>

<td style="text-align:center;">(-1.24%)</td>

</tr>

<tr>

<td>LC-500</td>

<td style="text-align:center;">0.2794</td>

<td style="text-align:center;">**0.2951**</td>

<td style="text-align:center;">0.6719</td>

<td style="text-align:center;">0.4300</td>

<td style="text-align:center;">0.3128</td>

</tr>

<tr>

<td style="text-align:center;"> </td>

<td style="text-align:center;">(-0.29%)</td>

<td style="text-align:center;">(-1.89%)</td>

<td style="text-align:center;">(+0.01%)</td>

<td style="text-align:center;">(-0.92%)</td>

<td style="text-align:center;">(-0.29%)</td>

</tr>

<tr>

<td>LC-1000</td>

<td style="text-align:center;">0.2798</td>

<td style="text-align:center;">0.2978</td>

<td style="text-align:center;">0.6719</td>

<td style="text-align:center;">0.4300</td>

<td style="text-align:center;">0.3123</td>

</tr>

<tr>

<td style="text-align:center;"> </td>

<td style="text-align:center;">(-0.14%)</td>

<td style="text-align:center;">(-1.00%)</td>

<td style="text-align:center;">(+0.01%)</td>

<td style="text-align:center;">(-0.92%)</td>

<td style="text-align:center;">(-0.44%)</td>

</tr>

<tr>

<td colspan="6">LC-all denotes linear combination with all 10000 documents for fusion, LC-x, denotes linear combination with x top-ranked documents for fusion</td>

</tr>

</tbody>

</table>

<table class="center"><caption>  
Table 7: Fusion effectiveness with top-ranked documents in the 2012 year group (top 1000 documents are used for training)</caption>

<tbody>

<tr>

<th>Method</th>

<th>AP</th>

<th>RP</th>

<th>RR</th>

<th>P@10</th>

<th>NDCG@20</th>

</tr>

<tr>

<td>Best</td>

<td style="text-align:center;">0.2123</td>

<td style="text-align:center;">0.2583</td>

<td style="text-align:center;">0.6515</td>

<td style="text-align:center;">0.5020</td>

<td style="text-align:center;">0.2383</td>

</tr>

<tr>

<td>Average</td>

<td style="text-align:center;">0.1248</td>

<td style="text-align:center;">0.1823</td>

<td style="text-align:center;">0.5381</td>

<td style="text-align:center;">0.3588</td>

<td style="text-align:center;">0.1634</td>

</tr>

<tr>

<td>LC-all</td>

<td style="text-align:center;">0.2827</td>

<td style="text-align:center;">0.3114</td>

<td style="text-align:center;">0.6530</td>

<td style="text-align:center;">0.4940</td>

<td style="text-align:center;">0.2259</td>

</tr>

<tr>

<td>LC-100</td>

<td style="text-align:center;">0.2811</td>

<td style="text-align:center;">0.3196</td>

<td style="text-align:center;">0.6699</td>

<td style="text-align:center;">0.4780</td>

<td style="text-align:center;">0.2223</td>

</tr>

<tr>

<td> </td>

<td style="text-align:center;">(-0.57%)</td>

<td style="text-align:center;">(+2.63%)</td>

<td style="text-align:center;">(+2.59%)</td>

<td style="text-align:center;">(-3.24%)</td>

<td style="text-align:center;">(-1.58%)</td>

</tr>

<tr>

<td>LC-200</td>

<td style="text-align:center;">0.2826</td>

<td style="text-align:center;">**0.3194**</td>

<td style="text-align:center;">0.6672</td>

<td style="text-align:center;">0.4840</td>

<td style="text-align:center;">0.2235</td>

</tr>

<tr>

<td> </td>

<td style="text-align:center;">(-0.04%)</td>

<td style="text-align:center;">(+2.57%)</td>

<td style="text-align:center;">(+2.17%)</td>

<td style="text-align:center;">(-2.02%)</td>

<td style="text-align:center;">(-1.08%)</td>

</tr>

<tr>

<td>LC-500</td>

<td style="text-align:center;">0.2847</td>

<td style="text-align:center;">0.3162</td>

<td style="text-align:center;">0.6687</td>

<td style="text-align:center;">**0.4860**</td>

<td style="text-align:center;">0.2247</td>

</tr>

<tr>

<td> </td>

<td style="text-align:center;">(+0.71%)</td>

<td style="text-align:center;">(+1.54%)</td>

<td style="text-align:center;">(+2.40%)</td>

<td style="text-align:center;">(-1.62%)</td>

<td style="text-align:center;">(-0.52%)</td>

</tr>

<tr>

<td>LC-1000</td>

<td style="text-align:center;">0.2849</td>

<td style="text-align:center;">0.3168</td>

<td style="text-align:center;">0.6674</td>

<td style="text-align:center;">0.4880</td>

<td style="text-align:center;">0.2249</td>

</tr>

<tr>

<td> </td>

<td style="text-align:center;">(+0.78%)</td>

<td style="text-align:center;">(+1.73%)</td>

<td style="text-align:center;">(+2.21%)</td>

<td style="text-align:center;">(-1.21%)</td>

<td style="text-align:center;">(-0.46%)</td>

</tr>

<tr>

<td colspan="6">LC-all denotes linear combination with all 10,000 documents for fusion, LC-x, denotes linear combination with x top-ranked documents for fusion</td>

</tr>

</tbody>

</table>

### Experiment 3

For the third experiment we divided the top-ranked 1000 documents into two categories. To emphasize the more significant documents, the top 100 documents are in category Important and are assigned with a heavier importance factor than the documents in category Average (documents at ranking position 101 to 1000). The importance factor for category Average is set to 1, while the importance factor for category Important is set to different values (1.2, 1.4, 1.6, 1.8 and 2.0). Thus we are able to train weights by using Equation 3\. For the fusion process, all 10000 documents in every result are used for linear combination. The other parts of the setting are similar to that of Experiment 2.

The experimental results are shown in Tables 8, 9 and 10\. The figures in parentheses are improvement rate of the method over LC-all. WR-x uses weighted regression method to train final components' weights, where x is the importance factor assigned to documents in category Important. Heavier weights than 2.0 are also tried but the results are worse. Therefore, those experimental results are not presented.

We can also see that the linear combination performs well on AP and RP, always better than the best component result. For all other three measures the difference between linear combination and other methods is small. In many cases, the difference between WR-x and LC-all is small.

<table class="center"><caption>  
Table 8: Fusion effectiveness with diversity weights assigned to top-ranked documents (average of three year groups, documents in categories Important and Average are treated differently)</caption>

<tbody>

<tr>

<th>Method</th>

<th>AP</th>

<th>RP</th>

<th>RR</th>

<th>P@10</th>

<th>NDCG@20</th>

</tr>

<tr>

<td>Best</td>

<td style="text-align:center;">0.1877</td>

<td style="text-align:center;">0.2342</td>

<td style="text-align:center;">0.6525</td>

<td style="text-align:center;">0.4626</td>

<td style="text-align:center;">0.2789</td>

</tr>

<tr>

<td>Average</td>

<td style="text-align:center;">0.1206</td>

<td style="text-align:center;">0.1754</td>

<td style="text-align:center;">0.5520</td>

<td style="text-align:center;">0.3577</td>

<td style="text-align:center;">0.2087</td>

</tr>

<tr>

<td>LC-all</td>

<td style="text-align:center;">0.2730</td>

<td style="text-align:center;">0.3054</td>

<td style="text-align:center;">0.6870</td>

<td style="text-align:center;">0.4691</td>

<td style="text-align:center;">0.2817</td>

</tr>

<tr>

<td>WR-1.2</td>

<td style="text-align:center;">0.2731</td>

<td style="text-align:center;">0.3049</td>

<td style="text-align:center;">0.6936</td>

<td style="text-align:center;">0.4630</td>

<td style="text-align:center;">0.2817</td>

</tr>

<tr>

<td style="text-align:center;"> </td>

<td style="text-align:center;">(+0.04%)</td>

<td style="text-align:center;">(-0.16%)</td>

<td style="text-align:center;">(+0.96%)</td>

<td style="text-align:center;">(-1.30%)</td>

<td style="text-align:center;">(?0.00%)</td>

</tr>

<tr>

<td>WR-1.4</td>

<td style="text-align:center;">0.2729</td>

<td style="text-align:center;">0.3044</td>

<td style="text-align:center;">0.6935</td>

<td style="text-align:center;">0.4650</td>

<td style="text-align:center;">0.2829</td>

</tr>

<tr>

<td style="text-align:center;"> </td>

<td style="text-align:center;">(-0.04%)</td>

<td style="text-align:center;">(-0.33%)</td>

<td style="text-align:center;">(+0.95%)</td>

<td style="text-align:center;">(-0.87%)</td>

<td style="text-align:center;">(+0.43%)</td>

</tr>

<tr>

<td>WR-1.6</td>

<td style="text-align:center;">0.2720</td>

<td style="text-align:center;">0.3039</td>

<td style="text-align:center;">0.6866</td>

<td style="text-align:center;">0.4658</td>

<td style="text-align:center;">0.2842</td>

</tr>

<tr>

<td style="text-align:center;"> </td>

<td style="text-align:center;">(-0.36%)</td>

<td style="text-align:center;">(-0.49%)</td>

<td style="text-align:center;">(-0.06%)</td>

<td style="text-align:center;">(-0.70%)</td>

<td style="text-align:center;">(+0.89%)</td>

</tr>

<tr>

<td>WR-1.8</td>

<td style="text-align:center;">0.2714</td>

<td style="text-align:center;">0.3023</td>

<td style="text-align:center;">0.6866</td>

<td style="text-align:center;">0.4699</td>

<td style="text-align:center;">0.2845</td>

</tr>

<tr>

<td style="text-align:center;"> </td>

<td style="text-align:center;">(-0.59%)</td>

<td style="text-align:center;">(-1.01%)</td>

<td style="text-align:center;">(-0.06%)</td>

<td style="text-align:center;">(+0.17%)</td>

<td style="text-align:center;">(+0.99%)</td>

</tr>

<tr>

<td>WR-2.0</td>

<td style="text-align:center;">0.2710</td>

<td style="text-align:center;">0.3009</td>

<td style="text-align:center;">0.6876</td>

<td style="text-align:center;">0.4706</td>

<td style="text-align:center;">0.2847</td>

</tr>

<tr>

<td style="text-align:center;"> </td>

<td style="text-align:center;">(-0.73%)</td>

<td style="text-align:center;">(-1.47%)</td>

<td style="text-align:center;">(+0.09%)</td>

<td style="text-align:center;">(+0.32%)</td>

<td style="text-align:center;">(+1.06%)</td>

</tr>

</tbody>

</table>

The results look different when different metrics are used. When AP and RP are used as evaluation metrics, the fused results with WR-1.2 to WR-2.0 are more likely to be a little worse than with LC-all. On the other hand, when RR, P@10, and NDCG@20 are used as evaluation metrics, the fused results with WR-1.2 to WR-2.0 are more likely to be a little better than with LC-all. This is understandable because AP and RP are system-oriented metrics, which consider relevant documents at all ranks; while RR, P@10, and NDCG@20 are user-oriented metrics, which only consider a few top-ranked documents. In all the cases difference is small and not significant.

From the above three experiments, we have a few observations. 1\. Using a small percentage of top-ranked documents for weight assignment can be as effective as using all the documents available; 2\. For weights assignment, further dividing top-ranked documents into two different categories may not obtain consistent improvement, no matter which measure is used. 3\. For the fused results, a long list of documents is more likely to be helpful for improving effectiveness than a short one, especially on those system-oriented metrics such as AP and RP. The effect is not obvious when user-oriented measures such as P@10 and RR are used. Therefore, if possible, we should avoid using too few documents (e.g., less than 5%) for fusion so as to allow the fused result to attain reasonably good effectiveness.

<figure class="centre">![figure 2a](p710fig2a.png)  
<span style="font-size:12; line-height:115%; text-align:center;">(a) Without the case of 10,000 documents</span>  

![figure 2b](p710fig2b.png)  
<span style="font-size:12; line-height:115%;text-align:center;">(b) With the case of 10,000 documents</span>  

<figcaption>  
Figure 2: Time (in seconds) needed for multiple linear regression of fused results with different numbers of training documents in three year groups</figcaption>

</figure>

### Experiment 4

Finally we tested efficiency of fusing different number of documents. In this experiment we test the time required for weights assignment training and fusion with different number of documents. The curve in Figure 2 demonstrates that with fewer documents for the training process, the time cost in linear regression is much less than that with all the documents available. According to the above effectiveness of the fused results with part training data, it is useful to reduce the scale of training data by selecting the documents in top positions instead of the whole set, so that we can save more time to achieve a not bad or an equally-effective result.

<figure class="center">![figure 3a](p710fig3a.png)  
<span style="font-size:12; line-height:115%; text-align:center;">(a) Without the case of 10,000 documents</span>  

![figure 3b](p710fig3b.png)  
<span style="font-size:12; line-height:115%; text-align:center;">(b) With the case of 10,000 documents</span>  

<figcaption>  
Figure 3: Efficiency of fusing different number of documents</figcaption>

</figure>

We also tested the time required for fusing different number of documents. Figure 3 shows the time taken. If fusing results with top 100 documents, the time needed is 0.11-0.13 seconds for each of the three data sets. Then the time needed increases almost linearly when more documents are fused. The time needed for fusing top-1000 documents is 0.19-0.22 seconds, and the time needed for fusing all 10000 documents is 1.47-1.76 seconds. Considerable difference exists between fusing all 10000 documents and fusing several hundred to one thousand documents. Considering both effectiveness and efficiency, we can see that fusing top 500 to 1000 documents in all component results is a very good solution. Compared with fusing all the documents in all component results, the latter can generate as effective final result as the former, while the time needed for the latter is only 10% to 15% of the time for the former.

## Conclusions

In this paper we have investigated some key strategic issues when implementing information search systems through data fusion with a big collection of documents. The major contribution of this paper is that it considers both effectivness and efficiency of data fusion methods in information search (previous related research has focused on effectivenss of the methods with little attention paid to efficiency). Efficiency becomes more important when using big document collections and related data search.

Through experiments with three groups of TREC data, we have demonstrated that if the component resultant lists are very long then data fusion with a small percentage of top-ranked documents (5% to 10% in our experiment) can achieve as effective a result as data fusion with all the documents in the resultant lists. On the other hand, the efficiency of the system can be improved considerably by fusing fewer documents (10 times fast in our erperiment). Similarly, using a small percentage of top-ranked documents for weights assignment can obtain effective weights, but further dividing documents into more categories does not bring any improvement.

We believe that the results of this research are useful for the implementation of information search systems in the big data age. With large document collections, it is not necessary to pay equal attention to all the documents in the resultant lists. It is a better policy to consider only those top-ranked documents that are more likely to be relevant to the information need, either for training or for fusion. Thus effectiveness and efficiency of the search system can be balanced.

In the future, we plan to carry out more experiments with other data fusion methods such as Condorcet fusion and weighted Condorcet fusion. Two other questions raised in the introductory part of this paper also demand further investigation.

## Acknowledgements

We thank the anonymous reviewers for their helpful comments.

## About the authors

**Jieyu Li** is a Researcher in the Library of Jiangsu University, Zhenjiang, China. Her research interests include evaluation of information retrieval/Web search systems. She can be contacted at [jli@ujs.edu.cn](mailto:jli@ujs.edu.cn).  
**Chunlan Huang** is a Ph.D. student in the School of Computer Science, Jiangsu University, Zhenjiang, China. Her research interests include data fusion models and query processing in information retrieval/Web search. She can be contacted at [palaceo77@163.com](mailto:palaceo77@163.com).  
**Xiuhong Wang** is a Professor in the Library of Jiangsu University, Jiangsu University, Zhenjiang, China. Her research interests include patent retrieval systems and user retrieval studies. She can be contacted at [Lib510@ujs.edu.cn](mailto:Lib510@ujs.edu.cn).  
**Shengli Wu** is a Professor in the School of Computer Science, Jiangsu University, Zhenjiang, China. His research interests include information retrieval/Web search, data mining and machine learning. He can be contacted at [swu@ujs.edu.cn](mailto:swu@ujs.edu.cn).  

#### References

*   Aslam, J. & Montague, M. (2001).Models for metasearch. In _Proceedings of the 24th international ACM SIGIR Conference on Research and Development in Information Retrieval_ (pp. 275-284). New York, NY: ACM Press.
*   Bartell, B.T., Cottrell, G. W. & Belew, R. K. (1994).Automatic combination of multiple ranked retrieval systems._Proceedings of the 17th international ACM SIGIR Conference on Research and Development in Information Retrieval_ (pp. 173-184). New York, NY: ACM Press.
*   Baeza-Yates, R. & Cambazoglu, B. (2014). Scalability and efficiency challenges in large-scale Web search engines. In _Proceedings of the Companion Publication of the 23rd International Conference on World Wide Web Companion Volume_ (pp.185-186). New York, NY: ACM Press.
*   Baeza-Yates, R. & Riberiro-Neto, B. (2011). _Modern information retrieval: the concepts and technology behind search_ (2nd. ed.). New York, NY: ACM Press.
*   Balog, K., Azzopardi, L. & de Rijke, M. (2009). A language modelling framework for expert finding._Information Processing & Management, 45_(1), 1-19.
*   Brin, S. & Page, L. (1998).The anatomy of a large-scale hypertextual Web search engine._Computer Networks and ISDN Systems, 30_(1-7), 107-117.
*   Clough, P. & Sanderson, M. (2013). Evaluating the performance of information retrieval systems using test collections. _Information Research, 18_(2), paper 582\. Retrieved from http://www.informationr.net/ir/18-2/paper582.html (Archived by WebCite<sup>®</sup> at http://www.webcitation.org/VOdnJyweU6A).
*   Cormack, G.V., Clarke, C.L. & Buettcher, S. (2009). Reciprocal rank fusion outperforms Condorcet and individual rank learning methods. In _Proceedings of the 32nd international ACM SIGIR Conference on Research and Development in Information Retrieval_ (pp. 758-759). New York, NY: ACM Press.
*   Cossock, D. & Zhang, T. (2006).Subset ranking using regression. In _Proceedings of the 19th annual conference on Learning Theory_ (pp.605-619). Berlin: Springer. (Lecture Notes in Computer Science, 4005).
*   Fox, E. A. & Shaw, J.A. (1994). Combining of multiple searches. In _Proceedings of the 2nd Annual Text Retrieval Conference (TREC-2)_ (pp. 35-44). Gaithersburg, MD: NIST.
*   Francès, G.,Bai, X., Cambazoglu, B. & Baeza-Yates, R. (2014). Improving the efficiency of multi-site web search engines.In _Proceedings of the 7th ACM international conference on Web search and data mining_(pp. 3-12). New York, NY: ACM Press.
*   Ghosh, K., Parui, S.K. & Majumder, P. (2015). Learning combination weights in data fusion using genetic algorithms. _Information Processing &Management, 51_(3), 306-328.
*   He, D. & Wu, D. (2008).Toward a robust data fusion for document retrieval. In _Proceedings of the 4th International Conference on Natural Language Processing and Knowledge Engineering_ (pp. 1-8). New York, NY: IEEE.
*   Kleinberg, J. (1999). Authoritative sources in a hyperlinked environment. _Journal of the ACM, 46_(5), 604?632.
*   Kohavi, R. (1995). A study of cross-validation and bootstrap for accuracy estimation and model selection. In _Proceedings of the 14th International Joint Conference on Artificial Intelligence_ (Volumn 2) (pp. 1137-1145). San Francisco, CA: Morgan Kaufmann Publishers Inc.
*   Kozorovitsky, A.K. & Kurland, O. (2011). Cluster-based fusion of retrieved lists. In _Proceedings of the 34th International ACM SIGIR Conference on Research and Development in Information Retrieval_ (pp.893-902). New York, NY: ACM Press.
*   Lee, J. H. (1997). Analyses of multiple evidence combination. In _Proceedings of the 20th International ACM SIGIR Conference on Research and Development in Information Retrieval_ (pp 276-276). New York, NY: ACM Press.
*   Liang, S., Ren, S. & de Rijke, M. (2014). Fusion helps diversification. In _Proceedings of the 37th International ACM SIGIR Conference on Research and Development in Information Retrieval_ (pp303-312). New York, NY: ACM Press.
*   Lillis, D., Toolan, F., Collier, R. & Dunnion, J. (2006). Probfuse: a probabilistic approach to data fusion. In _Proceedings of the 29th International ACM SIGIR Conference on Research and Development in Information Retrieval_ (pp.139-146). New York, NY: ACM Press.
*   Liu, Y. (2011). _Learning to rank for information retrieval_.Berlin: Springer.
*   Montague, M. & Aslam, J. (2002). Condorcet fusion for improved retrieval. In _Proceedings of the 11th ACM International Conference on Conference on Information and Knowledge Management (_pp. 538-548). New York, NY: ACM Press.
*   Ng, K.B. &Kantor, P.B. (2000). Predicting the effectiveness of naive data fusion on the basis of system characteristics. _Journal of American Society for Information Sciences, 51_(13), 1177-1189.
*   Nunes, S., Ribeiro, C. & Gabriel, D. (2013). [The impact of time in link-based Web ranking.](http://www.webcitation.org/VOdtYiweU6A) _Information Research, 18_(3), paper 586\. Retrieved from http://www.informationr.net/ir/18-3/paper586.html (Archived by WebCite<sup>®</sup> at http://www.webcitation.org/VOdtYiweU6A).
*   Orimaye, S. O., Alhashmi, S. M. & Siew.E. (2015). Performance and trends in recent opinion retrieval techniques. _Knowledge Engineering Review,30_(1), 76-105.
*   Santos, R. L.T., Macdonald, C. & Ounis, I. (2012). On the role of novelty for search result diversification._Information Retrieval,15_(5), 478-502.
*   Shokouhi, S. & Si, L. (2011). Federated Search. _Foundations and Trends in Information Retrieval,5_(1), 1-102.
*   Spoerri, A. (2007). Examining the authority and ranking effects as the result list depth used in data fusion is varied. _Information Processing & Management, 43_(4), 1044-1058.
*   Vogt, C. C. & Cottrell, G. W. (1999).Fusion via a linear combination of scores. _Information Retrieval, 1_(3), 151-173.
*   [Web search engine](http://http://en.wikipedia.org/wiki/Web_search_engine). (2015). In _Wikipedia: the free encyclopaedia_. Retrieved from http://http://en.wikipedia.org/wiki/Web_search_engine
*   Wu, S. (2012). _Data fusion in information retrieval_.Berlin: Springer.