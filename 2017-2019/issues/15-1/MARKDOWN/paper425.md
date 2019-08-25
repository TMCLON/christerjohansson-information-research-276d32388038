#### vol. 15 no. 1, March, 2010



# Using a two-stage technique to design a keyword suggestion system



#### [Lin-Chih Chen](#author)  
Department of Information Management, National Dong Hwa University, Hualien 97401, Taiwan

#### Abstract

> **Introduction.** The study of keyword suggestion in the field of search engine marketing is an important issue for paid search advertising or sponsored advertisements. The challenge of this issue is not only to suggest the relevant keywords, but also to find more such keywords.  
> **Method.** In this paper, we propose a system, the main goal of which is not only to suggest a list of relevant keywords, but also to determine the degree of similarity between the user's query and each suggested keyword.  
> **Analysis.** Three experiments were performed to illustrate the performance comparison between different systems and the relevant parameters considered in our system.  
> **Results.** According to the results of the first experiment, our system was found to be better than other online systems. According to the results of the second experiment, we concluded that the performance of the latent semantic analysis probability model is better than the random probability model. According to the results of the third experiment, we verified that the termination criteria of our system could yield a cost effective solution within a controlled period of time.  
> **Conclusions.** In this paper, we make several contributions. First, we propose an intelligent system that is based on several semantic analysis methods. Second, we define a new performance metric to compare the results of different systems. Third, we design a combined technique to find a cost effective solution within controlled period of time.



## Introduction

Search engine marketing is a method of Internet marketing that increases the visibility of a company's Website in search engine listings. In this marketing method, the business opportunity of paid search advertising is growing fast. According to existing historical evidence, the growing scale of this marketing method is very fast compared to traditional advertising or other online marketing methods ([Elliott 2006](#ell06)). In North American, the total market size of this marketing method was about US$12.2 billion in 2007, and it grew by 30% in 2006\. Moreover, and even more significant, this marketing method spending is now projected to grow to US$25.2 billion in 2011 ([Sherman 2008](#she08)).

Search engine marketing can be divided into two broad areas: search engine optimization and pay-per-click ([Sherman 2008](#she08)).

Search engine optimization is the process of developing, customizing or retooling a Web page so that it achieves a sustained high-ranking on search engine listings. According to the literature (see, for example, [Spink __et al.__ 2001](#spi01)), the majority of users (85.2%) view only the first page of the listings. Thus, if the entry page of a Website can be placed into the top rankings by a suitable optimisation process, then it can achieve a best advertising effect. However, it is a hard task to place a Web page into the top rankings unless the quality of the page content is superior to others.

Pay-per-click is another technique, whereby the advertisers typically bid on the advertisers' keyword list relevant to their target market. When the user's query matches the list, the advertiser's destination URL may be shown to the user. These links are called sponsored links or sponsored advertisements, and appear adjacent to or above the normal results. The search engine owners place the advertiser's destination URL into the top position of sponsored links for the advertiser who bids on the highest price and the bidding process may result in higher bidding price for popular keywords.

Alternatively, the advertisers also can focus on relatively low-cost keywords or phrases, called _suggested keywords_, which are relevant to the popular keywords, by a keyword suggestion process. On the one hand, the advertisers can adequately bid on a large number of suggested keywords to minimize their total cost, although the advertising effect of these keywords may be lower than the popular keywords. On the other hand, the search engine owners must provide an appropriate tool to attract more advertisers to buy advertisements to maximize their total revenue. Thus, using a suitable keyword suggestion process to generate a list of target keywords is an important issue for advertisers and search engine owners. In this paper, we focus on to propose a new keyword suggestion process to the search engine owners. When this process is built from the search engine owners, the advertisers can bid on the suggested keywords generated from this process. If the suggested keywords are highly related to the popular keywords, the search engine owners should attract more advertisers to increase their advertising budget.

Although many pay-per=click search providers exist in the current Internet, _Yahoo Search Marketing_ ([Yahoo 2006](#yah06)), _Google AdWords_ ([Google 2006](#goo06)), and Microsoft adCenter ([Microsoft 2006](#mic06)) were the largest in 2007 ([Sherman 2008](#she08)).

_Yahoo_ (formerly _Overture_, formerly _Goto.com_) was first to propose the concept of pay-per-click. Previously, the search engines had extracted the description values of the meta tags in HTML to obtain the description of the page content. Obviously, some webmasters may try to improve the ranking of their Website by a manual process to manipulate the content of the meta tags. _Goto.com_ focused on roughly the top 1,000 most popular keywords, employing experts and consultants to create hand-crafted pages ([Jansen and Mullen 2008](#jan08)) to overcome this problem. When _Goto.com_ introduced the concept of sponsored search, each page was associated with a suggested keyword list. The suggested keyword list was open to bids and the advertisers could request to add the advertiser's keyword list into a suitable _suggested_ keyword list by a bidding process. In other words, _Goto.com_ could ensure that the advertising content was relevant to the suggested keyword list. Given the rapid growth of sponsored search, the bidding process is now partially automated ([Mordkovich and Mordkovich 2007](#mor07)).

_Google_ proposed an _AdWords_ service in 2000 and it became _Google_'s main source of revenue ([2008](#goo08)). The main characteristic of _AdWords_ is the charging model of sponsored links, which uses the click through rate and cost per click to charge a suitable price for advertisers ([Lves 2005](#lve05)). The advertisers can control the amount of budget and time they wish to spend on advertising.

Microsoft was the last of the three big search engines (_Google_, _Yahoo_ and _MSN Live Search_, now _Bing_) to develop its own pay-per-click service. Previously, the advertising of Microsoft was provided by _Overture_. Microsoft decided to launch its own _adCenter_ service in 2006 when search engine marketing is growing fast. In _adCenter_, the position of sponsored links is decided by the advertisers' budget and is similar to __Google AdWords__. The main difference between _adCenter_ and _AdWords_ is that the former is integrated with MSN's member database, that is, the advertisers can decide the position of sponsored links according to sex, age, and place of residence by tracking the member database.

The existing providers fail to consider the semantic relationships between the user's query and the suggested keywords. That is, the relevant suggested keywords, not containing the input query, are often ignored to suggest.

This paper proposes a novel keyword suggestion system, called LIK, to suggest relevant and important keywords, and to measure the degree of similarity between the user's query and each relevant keyword. This system contains the following two stages: training and suggestion. In the training stage, it updates the training parameter based on the methods of latent semantic analysis ([Deerwester __et al.__ 1990](#dee90)) and probabilistic latent semantic analysis ([Hofmann 1999](#hof99)). In the suggestion stage, it first applies breadth-first search and the concept of inverse link to build a semantic graph. Then, it transforms the training parameter into the edge weight of the graph. Finally, the relevant keywords with the degree of similarity are suggested to the user for viewing or accessing according to the edge weight of the graph. In summary, the bases of latent semantic analysis, probabilistic latent semantic analysis and the semantic graph are all based on the semantic analysis between the query terms and the Web pages.

We make the following salient contributions in this paper. We propose a system that is based on several semantic analysis methods. We define a new performance metric, DIST, to compare the experimental results of different systems to fairly evaluate the performance of different systems. Moreover, this metric also can be applied to evaluate other information retrieval problems, such as document clustering and content matching. We design several mechanisms to achieve highly cost effective and noticeable improvements.

The rest of this paper is organized as follows. Next, previous research is reviewd; the following section presents the system's architecture, after which the performance comparisons between our system and other systems are shown, along with the simulation results for various parameters and the final section concludes the paper and discusses future directions.

## Related work

In this section, we discuss two related literatures: keyword suggestion and termination criteria for probabilistic latent semantic analysis.

### Keyword suggestion

Keyword suggestion is a relatively new and rapidly expanding research field, whose main goal is to generate a list of suggested keywords. Many systems are available on the Internet and currently available systems are shown in Table 1\. __CatS__ ([Radovanovic and Ivanovic 2006](#rad06)) used a separate category tree that derived from the dmoz taxonomy to arrange all suggested keywords. __Highlight__ ([Wu and Chen 2003](#wu03)) adopted a lexical analysis and a probabilistic analysis to construct a concept hierarchy for all relevant keywords. __Credo__ ([Carpineto and Romano 2004](#car04)) applied a formal concept analysis to construct all suggested keywords in a hierarchy form that allows users to query Web pages and judges the relevant results. __Carrot2__ ([Osinski and Weiss 2005](#osi05)) used the sentences with variable length words as the candidate keywords, then, it utilized a suffix tree clustering to identify which one should be suggested. _Google Proximity Search_ ([Ranks.NL 2008](#ran08)) used several search engines to collect the relevant Web pages in response to the seed keyword, then, it expanded new suggested keywords in its proximity range. __Google AdWords__ ([Google 2006](#goo06)) and __Yahoo Search Marketing__ ([Yahoo 2006](#yah06)) analysed the content of the query log file to suggest the relevant keywords. __Clusty__ ([Segev __et al.__ 2007](#seg07)) adopted the concept of concise all-pairs profiling to match all possible pairs of relevant keywords. _WordTracker_ ([2008](#wor08)) produced a list of suggested keywords by using the concept of query expansion.

<table width="60%" border="1" cellspacing="0" cellpadding="3" align="center" style="border-right: #99f5fb solid; border-top: #99f5fb solid; font-size: smaller; border-left: #99f5fb solid; border-bottom: #99f5fb solid; font-style: normal; font-family: verdana, geneva, arial, helvetica, sans-serif; background-color: #fdffdd"><caption align="bottom">  
**Table 1: The list of the online keyword suggestion systems that available on the Internet**</caption>

<tbody>

<tr>

<td>**System**</td>

<td>**Access URL**</td>

</tr>

<tr>

<td>[_CatS_](http://www.webcitation.org/query?url=http%3A%2F%2Fstribog.im.ns.ac.yu%2Fcats%2Fservlet%2FCatS%3FsearchEngine%3DAltaVista&date=2010-03-07)</td>

<td>http://stribog.im.ns.ac.yu/cats/servlet/CatS?searchEngine=AltaVista</td>

</tr>

<tr>

<td>[Highlight](http://www.webcitation.org/query?url=http%3A%2F%2FHighlight.njit.edu%2F&date=2010-03-06)</td>

<td>http://Highlight.njit.edu/</td>

</tr>

<tr>

<td>[Credo](http://www.webcitation.org/query?url=http%3A%2F%2FCredo.fub.it%2F&date=2010-03-06)</td>

<td>http://Credo.fub.it/</td>

</tr>

<tr>

<td>[Carrot2](http://www.webcitation.org/query?url=http%3A%2F%2Fsearch.Carrot2.org%2F&date=2010-03-06)</td>

<td>http://search.Carrot2.org/</td>

</tr>

<tr>

<td>[Google Proximity Search](http://www.webcitation.org/query?url=http%3A%2F%2Fwww.rapidkeyword.com%2F&date=2010-03-06)</td>

<td>http://www.rapidkeyword.com/</td>

</tr>

<tr>

<td>[Google AdWords](http://www.webcitation.org/query?url=https%3A%2F%2Fadwords.google.com%2F&date=2010-03-06)</td>

<td>https://adwords.google.com/</td>

</tr>

<tr>

<td>[Yahoo Search Marketing](http://www.webcitation.org/query?url=https%3A%2F%2Fsignup13.marketingsolutions.yahoo.com%2F&date=2010-03-06)</td>

<td>https://signup13.marketingsolutions.yahoo.com/</td>

</tr>

<tr>

<td>[Clusty](http://www.webcitation.org/query?url=http%3A%2F%2FClusty.com%2F&date=2010-03-06)</td>

<td>http://Clusty.com/</td>

</tr>

<tr>

<td>[WordTracker](http://www.webcitation.org/query?url=http%3A%2F%2Ffreekeywords.wordtracker.com%2F&date=2010-03-06)</td>

<td>http://freekeywords.wordtracker.com/</td>

</tr>

<tr>

<td>[LIK](http://www.webcitation.org/query?url=http%3A%2F%2Fcayley.sytes.net%2FLIK_english&date=2010-03-06)</td>

<td>http://cayley.sytes.net/LIK_english</td>

</tr>

</tbody>

</table>

### Termination criteria for probabilistic latent semantic analysis

A classical method to represent the co-occurrences of terms and documents is term matching. However, this method exists two problems: synonymy and polysemy. Deerwester _et al_. ([1990](#dee90)) proposed a latent semantic analysis model to address the problem of synonymy. Latent semantic analysis uses the singular value decomposition, a mathematical technique that reduces the dimension of the matrix, to capture lexical similarities between terms and documents. However, it fails to deal with the problem of polysemy since a single vector in the result of singular value decomposition represents only one term ([Ishida and Ohta 2002](#ish02)). Another drawback of latent semantic analysis is that it lacks a solid statistical foundation and, hence, is more difficult to use by combining it with other models ([Hofmann 1999](#hof99)).

To overcome these drawbacks, Hofmann ([1999](#hof99)) proposed a probabilistic method, called probabilistic latent semantic analysis, to discover a latent semantic space from terms and documents. It is more flexible and has a more solid statistical foundation than standard latent semantic analysis. Additionally, probabilistic latent semantic analysis can deal with the problem of polysemy and can explicitly distinguish between different meanings and different types of term usage. Probabilistic latent semantic analysis uses an aspect model to identify the hidden semantic relationships among terms and documents. In the aspect model, the terms and documents are considered as independent of each other.

Probabilistic latent semantic analysis uses an expectation maximization algorithm for maximum likelihood estimation; it also guarantees a convergent behaviour for the iterative procedure. The target of probabilistic latent semantic analysis is to maximize the log-likelihood function by using the expectation maximization algorithm. Probabilistic latent semantic analysis defines that a local optimal solution is reached if the improvement value of the log-likelihood function between two consecutive iterations is less than a predefined threshold.

Although probabilistic latent semantic analysis can converge to the local optimal solution, it may take a long time to reach this solution. To achieve faster response time for expectation maximization algorithm, many researchers used the following two termination criteria to decide whether the algorithm should stop or whether the processing should proceed: (1) setting a fixed number of iterations to stop the algorithm or (2) using a more relaxed threshold to determine whether the algorithm should terminate.

Some researchers ([Gibson __et al.__ 2005](#gib05); [Metaxoglou and Smith 2007](#met07); [Nguyen __et al.__ 2007](#ngu07)) used a fixed number of iterations to stop the algorithm to save execution time when it cannot to reach the local optimal solution within the range of iterations.

Other researchers used a more relaxed threshold to determine whether the algorithm should terminate. Ristad and Yianilos ([1998](#ris98)) terminated the algorithm when the increased total probability of training corpus among consecutive iterations falls below a fixed threshold rate. Markatou ([2000](#mar00)) calculated the weighted likelihood estimates on the bootstrap sub-samples that were drawn from whole data set by the method of moment estimates for each iteration. The algorithm should be terminated if the estimate values are less than or equal to a predefined quantile value. Zhang and Goldman ([2001](#zha01)) first selected a set of unlabelled data in the expectation step, then they calculated a diverse density probability from all selected data in the maximization step. The algorithm should be terminated if the probability is less than or equal to a predefined probability value. Petersen and Winther ([2005](#pet05)) applied a negative log-likelihood function as the cost function of the algorithm. Please revise the sentence as follows: The termination criterion is defined as the difference in cost function values of two successive iterations less than the threshold value.

The expectation maximization algorithm uses a fixed number of iterations or a relaxed threshold as the termination criterion has the following two main problems. First, if it takes a small number of iterations or a larger threshold value, it may result in the difference being large compared with the final solution and the local optimal solution. Secondly, if it takes a large number of iterations or a small threshold value, it may result in the number of iterations becoming very large when the improvement value is very small when the solution is close to the local optimal solution.

To solve theses problems, we decided to combine the concept of the improvement value and improvement progress history as the termination criterion. Since the improvement value and improvement progress history are not always equal for each iteration, the number of iterations required to run varies. That is, the combined technique can ensure that the number of iterations is dynamically determined. In summary, we focus on applying this technique to find a cost effective solution within a controlled period of time rather than to find the local optimal solution.

## Keyword suggestion system

In this section, we propose an integrated keyword suggestion system, called LIK, as shown in Figure 1\. The system involves the following two stages: training and suggestion, which are described below.

### Training stage

The main objective of this stage is to generate the training parameter, called the query-by-document matrix, which is the main source of the suggestion stage, based on the methods of latent semantic analysis and probabilistic latent semantic analysis.

First, the training stage uses the _AOL Query Log_ ([AOL 2006](#aol06)) as terms and all collected Web pages as documents to form a vector-space-model matrix. The query log consists of about twenty million search query terms collected from about 650,000 users. Then, this stage transforms the vector-space-model matrix into the query-by-document matrix using the latent semantic analysis and intelligent probabilistic latent semantic analysis modules.

The core module of this stage is intelligent probabilistic latent semantic analysis, which is extended from the probabilistic latent semantic analysis method, and which improves the termination criteria of probabilistic latent semantic analysis. Compared to probabilistic latent semantic analysis, the termination criteria of our proposed method have two mechanisms: one based on the local optimal solution, the other based on the improvement value at each iteration and the improvement progress history. The benefit of the second criterion is that it can prevent a relatively small improvement in performance when the solution is close to the local optimal solution. Thus, intelligent probabilistic latent semantic analysis can skilfully reduce the number of iterations required to run this stage and this property should be able to form the query-by-document matrix relatively quickly. In short, the purpose of intelligent probabilistic latent semantic analysis is intended to yield a cost effective solution within a controlled period of time rather than to reach the local optimal solution.

The probabilistic latent semantic analysis method computes the relevant probability distributions by selecting the model parameters that maximize the probability of the observed data, i.e., the likelihood function. The standard method for maximum likelihood estimation is the expectation maximization algorithm. For a given initialization, the likelihood function increases with each iteration of the expectation maximization algorithm until the local optimal solution is reached, so that the quality of solution can be highly variable depends on the initialization values. In this stage, we use the parameters of the latent semantic analysis probability model as the initial parameters in the latent semantic analysis module. Rather than trying to predict the best initial parameters from a set of data, this probability model focuses on how to find a good way to initialize.

Repeatedly, the training stage consecutively executes the modules of latent semantic analysis and intelligent probabilistic latent semantic analysis in background to form a new query-by-document matrix. The detailed descriptions of these two modules follow..

<div align="center" id="fig-1">![Figure 1: The system architecture of LIK](p425fig1.gif)</div>

<div align="center">  
**Figure 1: The system architecture of LIK**</div>

#### Latent semantic analysis module

The main objective of this module (marked 'A' in the figure) is to use the latent semantic analysis probability model to form the initial parameters. This model is based on a dual '_latent semantic analysis-and-probabilistic latent semantic analysis_' probability model developed by Ding ([2005](#din05)) and Bellegarda ([2008](#bel08)). We must accomplish the following three tasks to form this model: (a) use terms and documents to form a vector-space-model matrix; (b) use the result of the vector-space-model matrix to form the relevant latent semantic analysis parameters; and (c) transform these latent semantic analysis parameters into the latent semantic analysis probability model. All the above-mentioned three tasks are corresponding to "Form Vector-Space-Model", "Vector-Space-Model to Latent Semantic Analysis", and "Latent Semantic Analysis to Probability-Latent Semantic Analysis" sub-modules, respectively, as shown in the following lists.

*   Form vector-space-model sub-module

The main task of this sub-module (A.1 in Figure 1) is to calculate the co-occurrence weight in a vector-space-model matrix by a general search engine as shown in Figure 2, where _M_ is all query terms derived from the 'AOL Query Log' and _N_ is all the collected Web pages.

<div align="center" id="fig-2">![Figure 2: The form of the vector-space-model matrix](p425fig2.gif)</div>

<div align="center">  
**Figure 2: The form of the vector-space-model matrix**</div>

Currently, the element of the matrix, _w_(_q<sub>i</sub>_,_d<sub>j</sub>_), is using an SVV algorithm ([Chen and Luh 2005](#che05)) to calculate its weight. SVV is based on the primacy effect of browsing behaviour ([Lempel and Moran 2000](#lem00); [Morris and Maisto 2001](#mor01); [Paepcke _et al._ 2000](#pae00)), that is, the users prefer top ranking items in the search results and this preference gradually decreases. Based on the above observation, we first defined a user behaviour function ([Chen and Luh 2005](#che05)) to state this effect, as shown in the following equation:

<div align="center">![equation](p425eq1.gif)</div>

where _α_ denotes the degree of the user preference for the first item; _l<sub>obj</sub>_ denotes the relative order of the object _obj_ within an ordered item list _l_; and _β_ denotes the decline degree of the user preference.

According to user behaviour function's definition, we then defined _w_(_q<sub>i</sub>_,_d<sub>j</sub>_) based on the dot product between different user behaviour functions that are derived from various search engines, as shown in the following equation:

<div align="center">![equation](p425eq2.gif)</div>

where _e_ is the number of search engines used in SVV; _s_ is a search engine number; _α<sub>s,qi</sub>_ is the degree of the user preference for the first listing returned from search engine _s_ in response to the user's query _q<sub>i</sub>_; _x<sub>s,dj,qi</sub>_ is the relative order of a Web page _d<sub>j</sub>_ within the search listings _x_ returned from _s_ in response to _q<sub>i</sub>_; and _β_ is the decline degree of the user preference. According to the definition of equation (2), we know that a Web page has a larger weight if it either wins more votes from different search engines or ranks high in the listings of at least one search engine. More details of SVV are described in our previous work ([Chen and Luh 2005](#che05)).

*   Vector-space-model to latent semantic analysis sub-module

The main task of this sub-module (A.2 in Figure 1) is to convert the vector-space-model matrix into the relevant latent semantic analysis parameters. Latent semantic analysis is an important information retrieval technique, which is used to solve the problem of synonymy. Latent semantic analysis finds a low-rank approximation matrix, which is smaller and less noisy than the vector-space-model matrix. For a fixed _k_, using a truncated singular value decomposition technique, which conserves _k_ largest singular values and sets others tobe zero, to approximate the vector-space-model matrix, as shown in the following equation:

<div align="center">![equation](p425eq3.gif)</div>

where _D<sub>k</sub>_=diag(_σ_<sub>1</sub>,_σ_<sub>2</sub>,...,_σ<sub>k</sub>_) is a _k*k_ diagonal matrix, which contain the singular value of the vector-space-model matrix arranged in decreasing order; _U<sub>k</sub>_=(_u_<sub>1</sub>,_u_<sub>2</sub>,...,_u<sub>k</sub>_) is a _M*k_ left singular matrix, which is a unitary matrix; and _V<sub>k</sub>_=(_v_<sub>1</sub>,_v_<sub>2</sub>,...,_v<sub>k</sub>_) is a _N*k_ right singular matrix, which is also a unitary matrix.

*   Latent semantic analysis to probability-latent semantic analysis sub-module

The main task of this sub-module (A.3) is to transform the relevant latent semantic analysis parameters, _U<sub>k</sub>_, _D<sub>k</sub>_, and _V<sub>k</sub>_ into the latent semantic analysis probability model that provides the initial parameters.

Although probabilistic latent semantic analysis can converge to the local optimal solution ([Hofmann 2001](#hof01)), its result is closely related to how one decides which methods are appropriate to initialize its parameters. According to literature reviews ([Brants 2005](#bra05); [Brants and Stolle 2002](#bra02)), the initial parameters of probabilistic latent semantic analysis can be determined by using either random initialization or according to some prior knowledge.

Hofmann ([2001](#hof01)) proposed a dual model to express the relationship of latent semantic analysis and probabilistic latent semantic analysis. This model uses the parameters of probabilistic latent semantic analysis to estimate the relevant latent semantic analysis parameters, as shown in the following equations:

<div align="center">![equation](p425eq4.gif)</div>

<div align="center">![equation](p425eq5.gif)</div>

<div align="center">![equation](p425eq6.gif)</div>

where _P_(_q<sub>i</sub>_|_z<sub>k</sub>_), _P_(_z<sub>k</sub>_), and _P_(_d<sub>j</sub>|z<sub>k</sub>_) are all probabilistic latent semantic analysis parameters, as described in section 3.1.2\. After viewing equations (4) to (6), we can determine the initial parameters of probabilistic latent semantic analysis according to the result of singular value decomposition.

However, singular value decomposition may introduce negative values in the elements of _U<sub>k</sub>_ and _V<sub>k</sub>_ matrices, and such values cannot be treated as a probability distribution. Thus, we cannot directly use the result of singular value decomposition to be the initial parameters.

To solve the problem of negative values in singular value decomposition, Ding ([2005](#din05)) and Bellegarda ([2008](#bel08)) used a dual probability model to estimate the elements of _U<sub>k</sub>_ and _V<sub>k</sub>_, as shown in the following equations, where _u<sub>k</sub>_ and _v<sub>k</sub>_ are the left and right singular vectors, respectively:

<div align="center">![equation](p425eq7.gif)</div>

<div align="center">![equation](p425eq8.gif)</div>

Moreover, according to the definition of singular value decomposition, we know that the singular values of the vector-space-model matrix, _σ<sub>k</sub>_, are all larger than zero. Thus, we use a probability form to estimate the elements of _D<sub>k</sub>_, as shown in the following equation:

<div align="center">![equation](p425eq9.gif)</div>

where _f_(_σ<sub>k</sub>_) is any non-decreasing function and its value is larger than zero. According to the definition of singular value decomposition, _σ<sub>i</sub>_≥_σ_<sub>_i_+1</sub>>0 where _i_≥1, we can guarantee _f_(_σ<sub>i</sub>_)≥_f_(_σ_<sub>_i_+1</sub>)>0\. Below, we will simulate three non-decreasing functions to verify that different _f_(_σ<sub>k</sub>_) functions how to affect the value of the objective function, as described in the following lists:

1.  _f_(_σ<sub>k</sub>_)=_exp_(_σ<sub>k</sub>_): The property of this function is growing sufficiently fast. It means that the latent semantic analysis probability model reinforces _σ<sub>k</sub>_ on the initial parameters.
2.  _f_(_σ<sub>k</sub>_)=_sinh_<sup>-1</sup>(_σ<sub>k</sub>_): The property of this function is growing sufficiently slow. It means that the latent semantic analysis probability model weakens _σ<sub>k</sub>_ on the initial parameters.
3.  _f_(_σ<sub>k</sub>_)=_σ<sub>k</sub>_: This function is represented as a control group.

#### Intelligent probabilistic latent semantic analysis module

The main objective of this module (B) is to generate the training parameter, called query-by-document matrix, which is then used for the suggestion stage. The basis of this module is the probabilistic latent semantic analysis developed by Hofmann ([1999](#hof99)).

To effectively generate the query-by-document matrix, we must accomplish the following two tasks: (a) adopt the probabilistic latent semantic analysis method to generate the query-by-document matrix and (b) use an adaptive mechanism to reduce the number of iterations required to run probabilistic latent semantic analysis. In the first task, we use the sub-modules _calculate query-by-document_, _likelihood function_, _expectation step_, and _maximization step_ to generate the query-by-document matrix. In the second task, we use the sub-modules of _calculate improvement value_, _calculate consecutive non-improvement_, _max allow iteration_ and _stop expectation maximization_ to determine whether probabilistic latent semantic analysis should be terminated or not. All the above-mentioned sub-modules are shown in the following lists.

*   Calculate query-by-document sub-module

The main task of this sub-module (B.1) is to form the query-by-document matrix, as shown in Figure 3, based on the observed data.

<div align="center" id="fig-3">![Figure 3: The form of the query-by-document matrix](p425fig3.gif)</div>

<div align="center">  
**Figure 3: The form of the query-by-document matrix**</div>

Probabilistic latent semantic analysis applies a probabilistic aspect model to derive the element of the matrix, called _P_(_q<sub>i</sub>_,_d<sub>j</sub>_). Probabilistic latent semantic analysis assumes that term _q<sub>i</sub>_ and document _d<sub>j</sub>_ exist as a series of latent topics _Z_={_z_<sub>1</sub>,...,_z<sub>k</sub>_,...,_z<sub>L</sub>_}, where _L_ is the total number of topics. To calculate _P_(_q<sub>i</sub>_,_d<sub>j</sub>_), we first need to define the relevant parameters in the following lists:

1.  _P_(_q<sub>i</sub>_) denotes the probability that _q<sub>i</sub>_ has been selected
2.  _P_(_q<sub>i</sub>_|_z<sub>k</sub>_) denotes the posterior probability of _q<sub>i</sub>_ given a latent topic _z<sub>k</sub>_
3.  _P_(_z<sub>k</sub>_|_q<sub>i</sub>_) denotes the posterior probability of _z<sub>k</sub>_ given _q<sub>i</sub>_
4.  _P_(_d<sub>j</sub>_|_z<sub>k</sub>_) denotes the posterior probability of _d<sub>j</sub>_ given _z<sub>k</sub>_

Based on the parameters above, we now calculate the joint probability of an observed pair (_q<sub>i</sub>_,_d<sub>j</sub>_) by summing over all possible choices of _Z_={_z_<sub>1</sub>,...,_z<sub>k</sub>_,...,_z<sub>L</sub>_} from which the observation could have been generated (it is clearly shown in Figure 4(a)), as shown in the following equation:

<div align="center">![equation](p425eq10.gif)</div>

Then, by applying Bayes's rule, it is straightforward to transform equation (10) into the following form (it is clearly shown in Figure 4(b)), as shown in the following equation:

<div align="center">![equation](p425eq11.gif)</div>

<div align="center" id="fig-4">![Figure 4: The aspect model of probabilistic latent semantic analysis](p425fig4.gif)</div>

<div align="center">  
**Figure 4: The aspect model of probabilistic latent semantic analysis**</div>

*   Likelihood function sub-module

The main task of this sub-module (B.2) is to calculate the value of the likelihood function L. To calculate the joint probability of an observed pair (_q<sub>i</sub>_,_d<sub>j</sub>_), probabilistic latent semantic analysis follows the likelihood principle to estimate the parameters _P_(_q<sub>i</sub>_|_z<sub>k</sub>_), _P_(_z<sub>k</sub>_), and _P_(_d<sub>j</sub>_|_z<sub>k</sub>_) by maximization of the likelihood function _L<sub>n</sub>_(_q<sub>i</sub>_,_d<sub>j</sub>_) at iteration _n_, as shown in the following equation:

<div align="center">![equation](p425eq12.gif)</div>

*   Expectation step sub-module

The main task of this sub-module (B.7) is to achieve the expectation step of the expectation maximization algorithm. The expectation maximization algorithm ([Dempster _et al._ 1977](#dem77)) is a well-known method to perform maximum likelihood parameter estimation in latent variable models. Generally, the expectation and maximization steps are needed to perform in this algorithm alternately. In the expectation step, probabilistic latent semantic analysis can simply apply Bayes's formula to generate the latent variable _z<sub>k</sub>_ based on the current estimates of the parameters _q<sub>i</sub>_ and _d<sub>j</sub>_ as follows:

<div align="center">![equation](p425eq13.gif)</div>

*   Maximization step sub-module

The main task of this sub-module (B.8) is to achieve the maximization step of the expectation maximization algorithm. In the maximization step, probabilistic latent semantic analysis applies the Lagrange multipliers method (see ([Hofmann 2001](#hof01)) for details) to solve the constraint maximization problem to get the following equations for re-estimated parameters _P_(_q<sub>i</sub>_|_z<sub>k</sub>_), _P_(_z<sub>k</sub>_), and _P_(_d<sub>j</sub>_|_z<sub>k</sub>_) as follows:

<div align="center">![equation](p425eq14.gif)</div>

<div align="center">![equation](p425eq15.gif)</div>

<div align="center">![equation](p425eq16.gif)</div>

Now, either intelligent probabilistic latent semantic analysis can substitute equations (7) to (9) or equations (14) to (16) into equations (11) and (12) until the termination criteria are reached.

*   Calculate improvement value (B.3), calculate consecutive non-improvement (B.4), max allow iteration (B.5), and stop expectation maximization (B.6) sub-modules

The main task of these sub-modules is to develop a performance-based termination criterion. This termination criterion can drastically reduce the number of iterations required to run at this stage, and it should be able to produce the training parameter relatively quickly.

Probabilistic latent semantic analysis is a time consuming and expensive process for each iteration and is related to the convergence speed of the expectation maximization algorithm ([Tsoi 2001](#tso01)). Dempster _et al._ ([1977](#dem77)) proved that the log-likelihood function is monotonically increasing until the local optimal solution is reached. Hofmann ([2004](#hof04)) proved that the time complexity is O(M*N*L), where O(M*N) is the time complexity of the expectation maximization algorithm for each iteration.

However, in the information retrieval environment, the total number of query terms (_M_) and the total number of Web pages (_N_) are both large. Moreover, the total number of topics (_L_) is increased along with increased _M_ and _N_ ([Inoue 2005](#ino05)). According to the observation of Kunder ([2008](#kun08)), the number of query terms and Web pages is enormous and the number of Web pages is still increasing, and this situation might will result in system performance being quite disappointing when probabilistic latent semantic analysis is applied to solve various large-scale information retrieval problems.

Thus, we must design an effective mechanism that skilfully balances cost (the number of iterations required to run) and performance (the value of the log-likelihood function). In this mechanism, we use the log-likelihood function (equation 12) to define the termination criteria (the _stop expectation maximization_ sub-module), which are not only to converge to the local optimal solution, but also the maximum required number of iterations is reached. We discuss these two criteria below.

In the first criterion, we define that the local optimal solution is reached if the improvement value between two consecutive iterations is less than a predefined threshold. We let _Diff<sub>n</sub>_ be the improvement value of the log-likelihood function at the _n<sup>th</sup>_ iteration (_calculate improvement value_ sub-module), as shown in the following equation:

<div align="center">![equation](p425eq17.gif)</div>

We then define the local optimal solution as shown in the following equation, where _ε_ denotes the predefined threshold of the first criterion.

<div align="center">![equation](p425eq18.gif)</div>

In the second criterion, the maximum required number of iterations is usually set as a fixed number through experiments. However, it is a difficult task to claim what the maximum required number of iterations should be. On the one hand, a large number of iterations may waste a significant amount of computing resources on a relatively small improvement. On the other hand, a small number iterations may result in the difference being large, compared with the final solution and the local optimal solution. It will be a cost-effective solution if the maximum required number of iterations is dynamically determined according to a case of real improvement for each iteration.

We then formally define the second criterion as follows: the consecutive number of iterations without improvement is larger than the maximum allowable number of iterations without significant improvement at current iteration. We consider that is a sign that further computation could not yield much progress.

The second criterion must define two important curves, one for the increasing cost curve and the other one for the decreasing performance curve. This criterion is fulfilled if there exists an iteration _n_ such that the value of the cost curve is larger than the value of the performance curve. In the cost curve at iteration _n_ #_IteNonImp<sub>n</sub>_, the consecutive number of iterations without improvement (_calculate consecutive non-improvement_ sub-module), is defined as the following equation:

<div align="center">![equation](p425eq19.gif)</div>

where _avg_(_Diff_<sub>_n_-1</sub>) denotes the average of all _Diff<sub>s</sub>_, 1≤_s_≤_n_-1\. That is, the _n<sup>th</sup>_ iteration is said to make _no improvement_ if _Diff<sub>n</sub>_ < _avg_(_Diff_<sub>_n_-1</sub>). Next, in the performance curve at iteration _n_ _MI<sub>n</sub>_, the maximum allowable number of iterations without significant improvement (_max allow iteration_ sub-module), is defined as the following equation:

<div align="center">![equation](p425eq20.gif)</div>

where _L_ denotes the total number of topics; _σ_(_Diff<sub>n</sub>_) denotes the standard deviation of all _Diff<sub>s</sub>_, 1≤_s_≤_n_-1; _avg_(_σ_(_Diff_<sub>_n_-1</sub>)) denotes the average of all _σ_(_Diff<sub>s</sub>_). As indicated in the definition of equation (20), the performance curve _MI<sub>n</sub>_ is dynamically determined based on the ratio of improvement history progress _Diff<sub>n</sub>_/_avg_(_Diff_<sub>_n_-1</sub>) and the ratio of variation history progress _σ_(_Diff<sub>n</sub>_)/_avg_(_σ_(_Diff_<sub>_n_-1</sub>)). If either _Diff<sub>n</sub>_/_avg_(_Diff_<sub>_n_-1</sub>) or _σ_(_Diff<sub>n</sub>_)/_avg_(_σ_(_Diff_<sub>_n_-1</sub>)) is large, there is a significant progress or variation progress in the log-likelihood function. Finally, let us formally define the second criterion as follows:

<div align="center">![equation](p425eq21.gif)</div>

### Suggestion stage

The main objective of this stage is using the query-by-document matrix to generate the desirable result of our system by a keyword suggestion module. To suggest the relevant keywords, this stage first constructs a semantic graph. Then, it transforms the query-by-document matrix into the edge weight of each directed edge in the graph. Finally, it is sorting a list of suggested keyword according to the edge weight.

#### Keyword suggestion module

This main objective of this module ('C' in figure 1) is to adopt breadth-first-search and the concept of inverse link to build a semantic graph, called KeywordsNet and then this graph is applied to generate a list of suggested keywords.

To generate a list of suggested keywords and the degree of similarity between the user's query and each suggested keyword, we must accomplish the following two tasks: (a) build a KeywordsNet and (b) transform the query-by-document matrix into the edge weight of KeywordsNet. These two tasks are corresponding to the _build KeywordsNet_ and _calculate edge weight_ sub-modules, as shown in the following lists.

*   Build KeywordsNet sub-module

The main task of this sub-module (C.1) is to build a KeywordsNet graph based on breadth-first-search and the concept of inverse link. In the graph, based on a user query _q<sub>i</sub>_, nodes represent all candidate keywords _q<sub>ks</sub>_s, and each directed edge (_q<sub>i</sub>_,_q<sub>ks</sub>_) between _q<sub>i</sub>_ and _q<sub>ks</sub>_ represents these two keywords exist in a strong semantic relationship and _q<sub>ks</sub>_ is suggested from _q<sub>i</sub>_. Figure 5 is a partial KeywordsNet graph to illustrate the strong semantic relationships between _p2p_ and some candidate keywords.

<div align="center" id="fig-5">![Figure 5: The result of a partial KeywordsNet graph when qi is p2p](p425fig5.gif)</div>

<div align="center">  
**Figure 5: The result of a partial KeywordsNet graph when q<sub>i</sub> is p2p**</div>

**Definition (strong semantic relationship)**: _q<sub>i</sub>_ and _q<sub>ks</sub>_ exist in a strong semantic relationship feature and (_q<sub>i</sub>_,_q<sub>ks</sub>_) is a directed edge if and only if these two keywords satisfy at least one of the following three relationships: (1) equivalence, (2) hierarchy, and (3) association ([NISO 2005](#nis05)). If there is an equivalent relationship between _q<sub>i</sub>_ and _q<sub>ks</sub>_, these two keywords are expressing the same concept. If _q<sub>i</sub>_ and _q<sub>ks</sub>_ can obtain a parent-child relationship through an intermediate candidate keyword, these two keywords have a hierarchical relationship. If _q<sub>i</sub>_ and _q<sub>ks</sub>_ can obtain an ancestor-descendant relationship through a series of intermediate candidate keywords, these two keywords have an association relationship. Note that we only show the directed edges of the equivalence relationship to prevent needlessly complex in Figure 5.

The main assumption of KeywordsNet is that if many important candidate keywords link to an important Web page, it can use the inverted index of the vector-space-model matrix to identify these important candidate keywords. KeywordsNet uses a series of recursive breadth-first-search calls to form a strong semantic relationship feature, as shown in the following pseudo code.

> 1.  Algorithm Breadth-First-Search(_q<sub>i</sub>_ as string, _PathLength_ as integer)
> 2.  {
> 3.  If (_PathLength_>_MaxLen_)
> 4.  Return(_KeywordsNetGraph<sub>qi</sub>_);
> 5.  Else {
> 6.  _D_=Fetch all important Web pages corresponding to _q<sub>i</sub>_;
> 7.  Foreach (_D_ as _d<sub>j</sub>_) {
> 8.  _ImportantKEYS_=Use the inverted index of _d<sub>j</sub>_ listed in the vector-space-model matrix to identify all important candidate keywords corresponding to _q<sub>i</sub>_;
> 9.  Foreach (_ImportantKEYS_ as _q<sub>ks</sub>_) {
> 10.  _KeywordsNetGraph<sub>qi</sub>_+=(_q<sub>i</sub>_,_q<sub>ks</sub>_);
> 11.  Breadth-First-Search(_q<sub>ks</sub>_, _PathLength_+1);
> 12.  } End of Foreach
> 13.  } End of Foreach
> 14.  } End of Else
> 15.  } End of Algorithm

In the first recursive call, _q<sub>i</sub>_ generates a candidate keyword _q_<sub>_ks_(1)</sub>. Hence, _q<sub>i</sub>_ is equivalent to _q_<sub>_ks_(1)</sub> since they share a same concept (Web page) _d<sub>j</sub>_. In the second recursive call, _q_<sub>_ks_(1)</sub> generates a candidate keyword _q_<sub>_ks_(2)</sub>. Hence, _q<sub>i</sub>_ and _q_<sub>_ks_(2)</sub> exist in a hierarchical relationship since the child candidate keyword _q_<sub>_ks_(2)</sub> can be accessed from the parent candidate keyword _q<sub>i</sub>_ through an intermediate candidate keyword _q_<sub>_ks_(1)</sub>. In the _t<sup>th</sup>_ (1 < t ≤ _MaxLen_) recursive call, _q_<sub>_ks_(t-1)</sub> generates a candidate keyword _q_<sub>_ks_(t)</sub>. Hence, _q<sub>i</sub>_ is associated with _q_<sub>_ks_(t)</sub> since there is a shortest path whose length is _t_ from _q<sub>i</sub>_ to _q_<sub>_ks_(t)</sub>.

**Example 1** (build a partial keywordsNet)  
In examples 1 and 2, we assume that the query terms are _q_<sub>1</sub>=_p2p_", _q_<sub>2</sub>=_peer to peer_, _q_<sub>3</sub>=_in peer to peer_, _q_<sub>4</sub>=_bittorrent_, _q_<sub>5</sub>=_torrent find_ and the collected Web pages are _d_<sub>1</sub>=_en.wikipedia.org/wiki/Peer-to-peer_, _d_<sub>2</sub>=_www.bittorrent.com_, _d_<sub>3</sub>=_isohunt.com_. Figure 6 shows an example of the vector-space-model matrix by using our SVV algorithm.

<div align="center" id="fig-6">![Figure 6: An example of the vector-space-model matrix](p425fig6.gif)</div>

<div align="center">  
**Figure 6: An example of the vector-space-model matrix**</div>

1.  For the case of the equivalence relationship, _q_<sub>1</sub> is equivalent to _q_<sub>2</sub> and _q_<sub>3</sub> since they share a same Web page (concept) _d_<sub>1</sub> and the directed edges are (_q_<sub>1</sub>,_q_<sub>2</sub>) and (_q_<sub>1</sub>,_q_<sub>3</sub>), respectively.
2.  For the case of the hierarchy relationship, _q_<sub>4</sub> can be accessed from _q_<sub>1</sub> through an intermediate keyword _q_<sub>2</sub> since _q_<sub>1</sub> is equivalent to _q_<sub>2</sub> (these two keywords share a same Web page _d_<sub>1</sub>) and _q_<sub>2</sub> is equivalent to _q_<sub>4</sub> (these two keywords share a same Web page _d_<sub>2</sub>), and the directed edge is (_q_<sub>1</sub>,_q_<sub>4</sub>).
3.  For the case of the association relationship, _q_<sub>5</sub> can be accessed from _q_<sub>1</sub> through two candidate keywords _q_<sub>2</sub> and _q_<sub>4</sub> since we can find the relationship of _q_<sub>1</sub>→_q_<sub>2</sub>→_q_<sub>4</sub>→_q_<sub>5</sub>, where '→' is the equivalence relationship exists in any two candidate keywords, and the directed edge is (_q_<sub>1</sub>,_q_<sub>5</sub>).

*   Calculate edge weight sub-module

The main task of this sub-module (C.2) is to transform the query-by-document matrix into the edge weight of KeywordsNet. We use a cosine similarity metric ([Salton 1989](#sal89); [Zhang and Nasraoui 2008](#zha08)) to achieve this transformation process, as shown in the following equation:

<div align="center">![equation](p425eq22.gif)</div>

where _P_(_q<sub>x</sub>_,_d<sub>j</sub>_), _x_∈{_i_,_ks_}, denotes the element of the query-by-document matrix, which is the joint probability of an observed pair (_q<sub>x</sub>_,_d<sub>j</sub>_) derived from the training stage. All suggested keywords with the degree of similarity are shown in sorted order according to the edge weight. Additionally, we also discard such keywords whose directed edges with a relative small edge weight. For example, in Figure 7, the degree of similarity for the directed edge (_p2p_, _peer sharing_) is 75% (Cosine(_p2p_, _peer sharing_)=75%).

<div align="center" id="fig-7">![Figure 7: The desirable result of our system in response to the user's query is p2p](p425fig7.gif)</div>

<div align="center">  
**Figure 7: The desirable result of our system in response to the user's query is p2p**</div>

**Example 2** (suggest keywords with the degree of similarity)  
According to the results of example 1, the directed edges are (_q_<sub>1</sub>,_q_<sub>2</sub>), (_q_<sub>1</sub>,_q_<sub>3</sub>), (_q_<sub>1</sub>,_q_<sub>4</sub>) and (_q_<sub>1</sub>,_q_<sub>5</sub>) for the seed keyword _q_<sub>1</sub>. Figure 8 shows an example of the result of the query-by-document matrix by the modules of latent semantic analysis and intelligent probabilistic latent semantic analysis.

<div align="center" id="fig-8">![Figure 8: An example of the query-by-document matrix](p425fig8.gif)</div>

<div align="center">  
**Figure 8: An example of the query-by-document matrix**</div>

In Table 2, we list the edge weight for each directed edge by adopting equation (22). Finally, the directed edge (_q_<sub>1</sub>,_q_<sub>3</sub>) should be discarded since it is a directed edge with a relatively small edge weight.

<table width="60%" border="1" cellspacing="0" cellpadding="3" align="center" style="border-right: #99f5fb solid; border-top: #99f5fb solid; font-size: smaller; border-left: #99f5fb solid; border-bottom: #99f5fb solid; font-style: normal; font-family: verdana, geneva, arial, helvetica, sans-serif; background-color: #fdffdd"><caption align="bottom">  
**Table 2: An example of different edge weights**</caption>

<tbody>

<tr>

<td align="left">**Directed edge**</td>

<td align="left">**(_q_<sub>1</sub>, _q_<sub>2</sub>)**</td>

<td>**(_q_<sub>1</sub>, _q_<sub>3</sub>)**</td>

<td>**(_q_<sub>1</sub>, _q_<sub>4</sub>)**</td>

<td>**(_q_<sub>1</sub>, _q_<sub>5</sub>)**</td>

</tr>

<tr>

<td align="left">**Edge weight**</td>

<td align="left">93.40%</td>

<td>59.87%</td>

<td>89.39%</td>

<td>88.38%</td>

</tr>

<tr>

<td align="left">**Discard**</td>

<td align="left"></td>

<td>X</td>

<td></td>

<td></td>

</tr>

</tbody>

</table>

## Preliminary experimental results

In this section, we present three experiments to illustrate the performance comparison between different systems and the relevant parameters considered in our system. First, we present the performance comparisons between our system and other systems. Second, we verify that the performance of the latent semantic analysis probability model is better than the random probability model. Third, we also verify that the termination criteria of intelligent probabilistic latent semantic analysis can yield a cost effective solution within a controlled period of time.

### Experiment results on different systems

In this experiment, we pay attention to how to rate the performance of different systems compared with _CatS_, _Highlight_, _Credo_, _Carrot2_,_Google Proximity Search_, _Google AdWords_, _Yahoo Search Marketing_, _Clusty_, _WordTracker_, and LIK. All the systems except LIK are described in section 2.1\. On the one hand, we evaluate the performance of these systems by a simulation and a user evaluation studies. On the other hand, we also simulate the performance of the training parameter generated from different models to verify that which step in the training stage has a major impact on the quality of our system.

In this experiment, we randomly selected 1,000 query terms from Dogpile ([InfoSpace 2008](#inf08)), which people were using to search the Internet. The 1,000 random query terms were listed in ([Dogpile 2008](#dog08)).

To compare the performance of different systems for our simulation program, we need to define a new performance metric, DIST, to fairly measure the average distance between the seed keyword _q<sub>i</sub>_ and any one of suggested keywords _q<sub>ks</sub>_ when the number of _q<sub>i</sub>_ is 1, as shown in the following equation:

<div align="center">![equation](p425eq23.gif)</div>

where _WP_(<sub>_qi_∩_qks_</sub>) (_WP_(<sub>_qi_∪_qks_</sub>)) is the intersection (union) of the top ten Web pages returned from _q<sub>i</sub>_ and _q<sub>ks</sub>_ when the search engine _s_ is used to measure; _R_(_WP_(<sub>_qi_∩_qks_</sub>) in _q<sub>x</sub>_), _x_∈{_i_,_ks_}, is the ranking of _WP_(<sub>_qi_∩_qks_</sub>) in response to _q<sub>x</sub>_ if _R_(_WP_(<sub>_qi_∩_qks_</sub>) in _q<sub>x</sub>_)>0, and 1/_R_(_WP_(<sub>_qi_∩_qks_</sub>) in _q<sub>x</sub>_)=0 if _WP_(<sub>_qi_∩_qks_</sub>) cannot be found in _q<sub>x</sub>_.

The motivation of this study is to minimize the average distance between _q<sub>i</sub>_ and _q<sub>ks</sub>_. Equation (23) implies the following three important properties. First, the number of _WP_(<sub>_qi_∩_qks_</sub>) is comparatively large, which implies that the Web pages returned from _q<sub>i</sub>_ and _q<sub>ks</sub>_ are close to each other. Second, the value of |1/_R_(_WP_(<sub>_qi_∩_qks_</sub>) in _q<sub>i</sub>_) - 1/_R_(_WP_(<sub>_qi_∩_qks_</sub>) in _q<sub>ks</sub>_)| is much less, which implies that the rankings of _WP_(<sub>_qi_∩_qks_</sub>) appearing in _q<sub>i</sub>_ and _q<sub>ks</sub>_ are similar. Third, the front rankings of _WP_(<sub>_qi_∩_qks_</sub>) have greater impact on DIST than the rear rankings, which implies that the dominant factor of DIST is the ranking of _WP_(<sub>_qi_∩_qks_</sub>).

We then use MDIST to measure the average distance between _q<sub>i</sub>_ and all suggested keywords when the number of _q<sub>i</sub>_ is 1, as shown in the following equation:

<div align="center">![equation](p425eq24.gif)</div>

where _C<sub>qi</sub>_ is all suggested keywords returned from _q<sub>i</sub>_. We set the number of _C<sub>qi</sub>_ (#_C<sub>qi</sub>_) equal to 10 to save the simulation time. That is, we calculate the average distance between _q<sub>i</sub>_ and the top 10 suggested keywords. Figure 9 shows the distribution of _MDIST<sub>SVV,qi</sub>_

<div align="center" id="fig-9">![Figure 9: The distribution of MDIST for SVV](p425fig9.gif)</div>

<div align="center">  
**Figure 9: The distribution of MDIST for SVV**</div>

For comparison purpose, we average all _MDIST<sub>SVV,qi</sub>_ when the number of _q<sub>i</sub>_ is 1000, as shown in Table 3\. We found that the average score of _MDIST<sub>SVV,qi</sub>_ obtained from LIK is 4.214660, which implies that it generates the suggested keywords with the minimal average distance score. Table 3 also shows the average score of _MDIST<sub>s,qi</sub>_ when Google and Yahoo are used to measure. No matter which search engines are used to measure, the average score of _MDIST<sub>s,qi</sub>_ for LIK is lowest that implies that the performance of our system is best.

<table width="70%" border="1" cellspacing="0" cellpadding="3" align="center" style="border-right: #99f5fb solid; border-top: #99f5fb solid; font-size: smaller; border-left: #99f5fb solid; border-bottom: #99f5fb solid; font-style: normal; font-family: verdana, geneva, arial, helvetica, sans-serif; background-color: #fdffdd"><caption align="bottom">  
**Table 3: The average score of _MDIST<sub>s,qi</sub>_ when different search engines are used to measure**</caption>

<tbody>

<tr>

<td align="left">**System**</td>

<td align="left">**Average _MDIST<sub>SVV,qi</sub>_**</td>

<td>**Average _MDIST<sub>Google,qi</sub>_**</td>

<td>**Average _MDIST<sub>Yahoo,qi</sub>_**</td>

</tr>

<tr>

<td align="left">_CatS_</td>

<td align="left">9.452357</td>

<td>9.466205</td>

<td>9.439944</td>

</tr>

<tr>

<td align="left">_Highlight_</td>

<td align="left">6.013398</td>

<td>6.015043</td>

<td>6.016055</td>

</tr>

<tr>

<td align="left">_Credo_</td>

<td align="left">8.365567</td>

<td>8.362261</td>

<td>8.359115</td>

</tr>

<tr>

<td align="left">_Carrot2_</td>

<td align="left">5.412458</td>

<td>5.420196</td>

<td>5.414073</td>

</tr>

<tr>

<td align="left">Google Proximity Search</td>

<td align="left">7.242496</td>

<td>7.250456</td>

<td>7.235417</td>

</tr>

<tr>

<td align="left">_Google AdWords_</td>

<td align="left">5.252066</td>

<td>5.275507</td>

<td>5.281719</td>

</tr>

<tr>

<td align="left">_Yahoo Search Marketing_</td>

<td align="left">5.245478</td>

<td>5.256330</td>

<td>5.282105</td>

</tr>

<tr>

<td align="left">_Clusty_</td>

<td align="left">4.893964</td>

<td>4.886279</td>

<td>4.844971</td>

</tr>

<tr>

<td align="left">WordTracker</td>

<td align="left">6.103158</td>

<td>6.115633</td>

<td>6.138991</td>

</tr>

<tr>

<td align="left">LIK</td>

<td align="left">4.214660</td>

<td>4.143232</td>

<td>4.164376</td>

</tr>

</tbody>

</table>

Next, we also simulate the training parameter generated from which step in the training stage that has a major impact on the performance of our system. In this simulation, we mainly compare the performance of the models of _non-latent semantic analysis_, _latent semantic analysis_, _latent semantic analysis-prob_, and _probabilistic latent semantic analysis_, that is, we use the results of the vector-space-model matrix (_non-latent semantic analysis_), singular value decomposition (_latent semantic analysis_), dual-probability (_latent semantic analysis-prob_), and expectation maximization (_probabilistic latent semantic analysis_), respectively, as the element of the query-by-document matrix. Table 4 shows the average score of _MDIST<sub>s,qi</sub>_ when SVV, Google, and Yahoo are used to measure.

<table width="70%" border="1" cellspacing="0" cellpadding="3" align="center" style="border-right: #99f5fb solid; border-top: #99f5fb solid; font-size: smaller; border-left: #99f5fb solid; border-bottom: #99f5fb solid; font-style: normal; font-family: verdana, geneva, arial, helvetica, sans-serif; background-color: #fdffdd"><caption align="bottom">  
**Table 4: The average score of _MDIST<sub>s,qi</sub>_ when the training parameter generated from different models**</caption>

<tbody>

<tr>

<td align="left">**Model**</td>

<td align="left">**Average _MDIST<sub>SVV,qi</sub>_**</td>

<td>**Average _MDIST<sub>Google,qi</sub>_**</td>

<td>**Average _MDIST<sub>Yahoo,qi</sub>_**</td>

</tr>

<tr>

<td align="left">Non-Latent Semantic Analysis</td>

<td align="left">5.512683</td>

<td>5.562672</td>

<td>5.501257</td>

</tr>

<tr>

<td align="left">Latent Semantic Analysis</td>

<td align="left">4.912361</td>

<td>4.812367</td>

<td>4.851436</td>

</tr>

<tr>

<td align="left">Latent Semantic Analysis-Prob</td>

<td align="left">5.134633</td>

<td>5.150166</td>

<td>5.114612</td>

</tr>

<tr>

<td align="left">Probabilistic Latent Semantic Analysis"</td>

<td align="left">4.635162</td>

<td>4.602481</td>

<td>4.612465</td>

</tr>

</tbody>

</table>

According to Table 4, we found that the training parameter generated from probabilistic latent semantic analysis has the lowest average MDIST score, which means that probabilistic latent semantic analysis has a major impact on the performance of our system. The average score of probabilistic latent semantic analysis is superior to latent semantic analysis since it can provide a better polysemy capability against latent semantic analysis. That is, the keywords suggested from probabilistic latent semantic analysis have more polysemous means than latent semantic analysis, and thus, we use the result of probabilistic latent semantic analysis as the core step of our system.

Although _latent semantic analysis-prob_ takes more computer time than latent semantic analysis, because it is derived from the result of latent semantic analysis, the performance of _latent semantic analysis-prob_" is worse than _latent semantic analysis_ because it uses a probability form to estimate the result of latent semantic analysis and it certainly results in a small amount of noise from this estimation process. In our system, the _latent semantic analysis-prob_ model is a bridge connecting latent semantic analysis to probabilistic latent semantic analysis. We cannot directly use the result of latent semantic analysis as the initial parameters since singular value decomposition may introduce negative values in the result of latent semantic analysis and such values cannot be treated as a probability distribution. Therefore, we use the result of _latent semantic analysis-prob_ as the initial parameters.

Finally, we selected thirty-nine of the most searched query terms in 2007 from Google ([2007](#goo07)), Yahoo ([Saremi 2007](#sar07)) and Lycos ([2007](#lyc07)) that belonging to many different topics (_anna nicole smith_, _badoo_, _beyonce_, _britney spears_, _club penguin_, _dailymotion_, _disney_, _ebuddy_, _facebook_, _fantasy football_, _fergie_, _fifa_, _golf_, _heroes_, _hi5_, _iphone_, _jessica alba_, _kazaa_, _lindsay lohan_, _Mozart_, _mp3_, _myspace_, _naruto_, _paris hilton_, _pokemon_, _poker_, _rebelled_, _rune scape_, _second life_, _shakira_, _sudoku_, _tmz_, _transformers_, _webdetente_, _webkinz_, _world cup_, _wwe_, _xanga_, _youtube_), and asked to thirty undergraduate and six graduate students from National Dong Hwa University to compare the results of different systems.

For each of the thirty-nine query terms, the thirty-sex users computed the precision at the first _N_ suggested keywords associated with the query terms generated by each system. Precision at top _N_ is defined as

<div align="center">![equation](p425eq25.gif)</div>

where _M_@_N_ is the number of suggested keywords that have been manually tagged as relevant among the first _N_ suggested keywords computed by each system.

The results of the experiment for _P_@3 are shown in Table 5\. The number in each percentage cell (except the last row) is the average _P_@3 score of each system on a given evaluated query for thirty-six users. For example, _CatS_ has an average _P_@3 score of 49.3% when the query is _anna nicole smith_. The number in the last row is the average _P_@3 score of each system on all evaluated query terms for thirty-six users.

<table width="90%" border="1" cellspacing="0" cellpadding="3" align="center" style="border-right: #99f5fb solid; border-top: #99f5fb solid; font-size: smaller; border-left: #99f5fb solid; border-bottom: #99f5fb solid; font-style: normal; font-family: verdana, geneva, arial, helvetica, sans-serif; background-color: #fdffdd"><caption align="bottom">  
**Table 5: _P_@3 over thirty-nine most searched query terms**</caption>

<tbody>

<tr>

<td align="left">**Query terms**</td>

<td align="left">**_CatS_**</td>

<td>**_Highlight_**</td>

<td>**_Credo_**</td>

<td>**_Carrot2_**</td>

<td>**Google Proximity Search**</td>

<td>**_Google AdWords_**</td>

<td>**_Yahoo Search Marketing_**</td>

<td>**_Clusty_**</td>

<td>**WordTracker**</td>

<td>**LIK**</td>

</tr>

<tr>

<td align="left">anna nicole smith</td>

<td align="left">49.3%</td>

<td>76.9%</td>

<td>63.5%</td>

<td>72.3%</td>

<td>67.7%</td>

<td>75.2%</td>

<td>82.3%</td>

<td>82.3%</td>

<td>76.1%</td>

<td>82.7%</td>

</tr>

<tr>

<td align="left">badoo</td>

<td align="left">42.7%</td>

<td>75.2%</td>

<td>58.1%</td>

<td>76.0%</td>

<td>68.6%</td>

<td>84.0%</td>

<td>78.3%</td>

<td>76.6%</td>

<td>76.5%</td>

<td>91.2%</td>

</tr>

<tr>

<td align="left">beyonce</td>

<td align="left">44.3%</td>

<td>73.9%</td>

<td>60.7%</td>

<td>80.4%</td>

<td>61.9%</td>

<td>80.4%</td>

<td>81.6%</td>

<td>82.3%</td>

<td>66.3%</td>

<td>83.3%</td>

</tr>

<tr>

<td align="left">britney spears</td>

<td align="left">45.6%</td>

<td>68.3%</td>

<td>64.6%</td>

<td>71.7%</td>

<td>62.2%</td>

<td>83.3%</td>

<td>73.3%</td>

<td>81.8%</td>

<td>69.7%</td>

<td>84.7%</td>

</tr>

<tr>

<td align="left">club penguin</td>

<td align="left">56.4%</td>

<td>67.6%</td>

<td>64.7%</td>

<td>82.3%</td>

<td>64.3%</td>

<td>74.5%</td>

<td>77.3%</td>

<td>81.8%</td>

<td>66.8%</td>

<td>82.7%</td>

</tr>

<tr>

<td align="left">dailymotion</td>

<td align="left">56.6%</td>

<td>70.1%</td>

<td>61.9%</td>

<td>75.1%</td>

<td>66.4%</td>

<td>83.8%</td>

<td>79.2%</td>

<td>77.1%</td>

<td>68.4%</td>

<td>86.6%</td>

</tr>

<tr>

<td align="left">disney</td>

<td align="left">55.3%</td>

<td>71.1%</td>

<td>56.0%</td>

<td>83.2%</td>

<td>62.2%</td>

<td>85.1%</td>

<td>80.5%</td>

<td>79.5%</td>

<td>68.5%</td>

<td>93.6%</td>

</tr>

<tr>

<td align="left">ebuddy</td>

<td align="left">56.0%</td>

<td>74.1%</td>

<td>62.9%</td>

<td>73.1%</td>

<td>64.3%</td>

<td>82.4%</td>

<td>80.0%</td>

<td>79.9%</td>

<td>74.1%</td>

<td>93.3%</td>

</tr>

<tr>

<td align="left">facebook</td>

<td align="left">46.3%</td>

<td>69.8%</td>

<td>55.9%</td>

<td>80.5%</td>

<td>66.8%</td>

<td>83.4%</td>

<td>78.1%</td>

<td>77.4%</td>

<td>74.6%</td>

<td>87.5%</td>

</tr>

<tr>

<td align="left">fantasy football</td>

<td align="left">53.7%</td>

<td>76.2%</td>

<td>56.4%</td>

<td>77.3%</td>

<td>69.1%</td>

<td>79.8%</td>

<td>77.3%</td>

<td>81.3%</td>

<td>69.7%</td>

<td>94.0%</td>

</tr>

<tr>

<td align="left">fergie</td>

<td align="left">46.1%</td>

<td>72.5%</td>

<td>59.0%</td>

<td>79.4%</td>

<td>65.6%</td>

<td>76.2%</td>

<td>75.8%</td>

<td>84.9%</td>

<td>65.6%</td>

<td>84.3%</td>

</tr>

<tr>

<td align="left">fifa</td>

<td align="left">43.6%</td>

<td>74.5%</td>

<td>65.4%</td>

<td>80.2%</td>

<td>61.9%</td>

<td>85.0%</td>

<td>84.9%</td>

<td>82.0%</td>

<td>75.8%</td>

<td>87.6%</td>

</tr>

<tr>

<td align="left">golf</td>

<td align="left">57.6%</td>

<td>76.0%</td>

<td>62.3%</td>

<td>71.9%</td>

<td>65.5%</td>

<td>73.2%</td>

<td>81.6%</td>

<td>77.6%</td>

<td>75.5%</td>

<td>85.0%</td>

</tr>

<tr>

<td align="left">heroes</td>

<td align="left">52.5%</td>

<td>72.8%</td>

<td>60.5%</td>

<td>76.2%</td>

<td>62.8%</td>

<td>81.6%</td>

<td>74.5%</td>

<td>80.8%</td>

<td>66.9%</td>

<td>91.2%</td>

</tr>

<tr>

<td align="left">hi5</td>

<td align="left">50.8%</td>

<td>70.5%</td>

<td>56.6%</td>

<td>71.9%</td>

<td>69.0%</td>

<td>76.4%</td>

<td>75.2%</td>

<td>79.5%</td>

<td>69.9%</td>

<td>88.5%</td>

</tr>

<tr>

<td align="left">iphone</td>

<td align="left">48.4%</td>

<td>75.1%</td>

<td>55.9%</td>

<td>71.5%</td>

<td>63.6%</td>

<td>75.3%</td>

<td>83.6%</td>

<td>81.2%</td>

<td>66.8%</td>

<td>84.1%</td>

</tr>

<tr>

<td align="left">jessica alba</td>

<td align="left">55.1%</td>

<td>73.2%</td>

<td>56.0%</td>

<td>83.2%</td>

<td>69.1%</td>

<td>81.7%</td>

<td>76.7%</td>

<td>79.6%</td>

<td>68.4%</td>

<td>91.4%</td>

</tr>

<tr>

<td align="left">kazaa</td>

<td align="left">48.0%</td>

<td>73.3%</td>

<td>62.7%</td>

<td>81.3%</td>

<td>66.8%</td>

<td>75.8%</td>

<td>81.3%</td>

<td>82.8%</td>

<td>73.8%</td>

<td>85.7%</td>

</tr>

<tr>

<td align="left">lindsay lohan</td>

<td align="left">56.3%</td>

<td>70.4%</td>

<td>55.9%</td>

<td>75.6%</td>

<td>62.0%</td>

<td>75.6%</td>

<td>82.8%</td>

<td>78.4%</td>

<td>73.9%</td>

<td>94.0%</td>

</tr>

<tr>

<td align="left">mozart</td>

<td align="left">49.9%</td>

<td>67.7%</td>

<td>58.2%</td>

<td>80.3%</td>

<td>67.0%</td>

<td>77.6%</td>

<td>75.2%</td>

<td>80.7%</td>

<td>65.5%</td>

<td>85.7%</td>

</tr>

<tr>

<td align="left">mp3</td>

<td align="left">56.0%</td>

<td>76.1%</td>

<td>58.6%</td>

<td>78.1%</td>

<td>61.4%</td>

<td>84.3%</td>

<td>77.5%</td>

<td>77.9%</td>

<td>74.3%</td>

<td>82.1%</td>

</tr>

<tr>

<td align="left">myspace</td>

<td align="left">47.9%</td>

<td>75.1%</td>

<td>60.4%</td>

<td>78.4%</td>

<td>67.8%</td>

<td>74.7%</td>

<td>74.6%</td>

<td>83.6%</td>

<td>71.9%</td>

<td>93.2%</td>

</tr>

<tr>

<td align="left">naruto</td>

<td align="left">48.6%</td>

<td>71.9%</td>

<td>58.2%</td>

<td>80.1%</td>

<td>61.5%</td>

<td>74.6%</td>

<td>78.1%</td>

<td>81.9%</td>

<td>71.2%</td>

<td>83.2%</td>

</tr>

<tr>

<td align="left">paris hilton</td>

<td align="left">43.7%</td>

<td>74.1%</td>

<td>60.0%</td>

<td>82.9%</td>

<td>65.3%</td>

<td>83.1%</td>

<td>79.0%</td>

<td>82.0%</td>

<td>71.8%</td>

<td>93.4%</td>

</tr>

<tr>

<td align="left">pokemon</td>

<td align="left">55.9%</td>

<td>68.8%</td>

<td>60.9%</td>

<td>81.2%</td>

<td>67.1%</td>

<td>83.9%</td>

<td>83.1%</td>

<td>81.4%</td>

<td>65.9%</td>

<td>86.7%</td>

</tr>

<tr>

<td align="left">poker</td>

<td align="left">43.8%</td>

<td>75.3%</td>

<td>59.9%</td>

<td>74.7%</td>

<td>63.9%</td>

<td>82.2%</td>

<td>82.2%</td>

<td>84.7%</td>

<td>72.7%</td>

<td>85.7%</td>

</tr>

<tr>

<td align="left">rebelde</td>

<td align="left">43.0%</td>

<td>71.2%</td>

<td>65.5%</td>

<td>71.9%</td>

<td>65.8%</td>

<td>79.6%</td>

<td>78.1%</td>

<td>78.9%</td>

<td>71.0%</td>

<td>93.0%</td>

</tr>

<tr>

<td align="left">rune scape</td>

<td align="left">47.7%</td>

<td>68.4%</td>

<td>64.5%</td>

<td>81.5%</td>

<td>64.6%</td>

<td>78.4%</td>

<td>84.6%</td>

<td>84.4%</td>

<td>75.9%</td>

<td>88.4%</td>

</tr>

<tr>

<td align="left">second life</td>

<td align="left">56.0%</td>

<td>76.2%</td>

<td>63.1%</td>

<td>83.1%</td>

<td>68.3%</td>

<td>77.7%</td>

<td>77.3%</td>

<td>79.9%</td>

<td>74.9%</td>

<td>85.8%</td>

</tr>

<tr>

<td align="left">shakira</td>

<td align="left">55.7%</td>

<td>70.7%</td>

<td>62.9%</td>

<td>72.4%</td>

<td>67.5%</td>

<td>82.7%</td>

<td>82.9%</td>

<td>86.8%</td>

<td>68.0%</td>

<td>83.2%</td>

</tr>

<tr>

<td align="left">sudoku</td>

<td align="left">57.6%</td>

<td>72.7%</td>

<td>61.0%</td>

<td>73.2%</td>

<td>63.8%</td>

<td>75.8%</td>

<td>80.6%</td>

<td>80.9%</td>

<td>70.1%</td>

<td>92.5%</td>

</tr>

<tr>

<td align="left">tmz</td>

<td align="left">42.8%</td>

<td>75.4%</td>

<td>57.5%</td>

<td>76.0%</td>

<td>69.0%</td>

<td>84.5%</td>

<td>85.0%</td>

<td>83.0%</td>

<td>72.3%</td>

<td>82.3%</td>

</tr>

<tr>

<td align="left">transformers</td>

<td align="left">50.5%</td>

<td>75.8%</td>

<td>63.2%</td>

<td>79.0%</td>

<td>64.2%</td>

<td>81.6%</td>

<td>75.2%</td>

<td>78.8%</td>

<td>69.4%</td>

<td>93.8%</td>

</tr>

<tr>

<td align="left">webdetente</td>

<td align="left">55.0%</td>

<td>74.8%</td>

<td>59.2%</td>

<td>74.3%</td>

<td>64.9%</td>

<td>84.8%</td>

<td>77.1%</td>

<td>85.3%</td>

<td>76.3%</td>

<td>84.3%</td>

</tr>

<tr>

<td align="left">webkinz</td>

<td align="left">55.7%</td>

<td>73.6%</td>

<td>60.0%</td>

<td>82.3%</td>

<td>68.3%</td>

<td>78.5%</td>

<td>81.7%</td>

<td>78.4%</td>

<td>66.1%</td>

<td>90.2%</td>

</tr>

<tr>

<td align="left">world cup</td>

<td align="left">55.6%</td>

<td>69.3%</td>

<td>56.6%</td>

<td>80.6%</td>

<td>62.4%</td>

<td>76.5%</td>

<td>84.2%</td>

<td>78.7%</td>

<td>66.4%</td>

<td>85.6%</td>

</tr>

<tr>

<td align="left">wwe</td>

<td align="left">43.8%</td>

<td>73.8%</td>

<td>57.5%</td>

<td>76.6%</td>

<td>63.7%</td>

<td>83.0%</td>

<td>80.6%</td>

<td>84.4%</td>

<td>76.2%</td>

<td>89.3%</td>

</tr>

<tr>

<td align="left">xanga</td>

<td align="left">49.4%</td>

<td>73.0%</td>

<td>56.9%</td>

<td>76.1%</td>

<td>66.8%</td>

<td>79.4%</td>

<td>75.4%</td>

<td>78.2%</td>

<td>73.3%</td>

<td>91.3%</td>

</tr>

<tr>

<td align="left">youtube</td>

<td align="left">53.7%</td>

<td>73.1%</td>

<td>55.9%</td>

<td>74.6%</td>

<td>68.2%</td>

<td>77.0%</td>

<td>79.0%</td>

<td>78.8%</td>

<td>66.0%</td>

<td>82.6%</td>

</tr>

<tr>

<td align="left">Average</td>

<td align="left">50.7%</td>

<td>72.8%</td>

<td>60.0%</td>

<td>77.4%</td>

<td>65.4%</td>

<td>79.8%</td>

<td>79.4%</td>

<td>80.9%</td>

<td>70.9%</td>

<td>87.8%</td>

</tr>

</tbody>

</table>

The average scores of _CatS_, _Highlight_, _Credo_, _Carrot2_,_Google Proximity Search_, _Google AdWords_, _Yahoo Search Marketing_, _Clusty_, _WordTracker_ and LIK for _P_@3 are 50.7%, 72.8%, 60.0%, 77.4%, 65.4%, 79.8%, 79.4%, 80.9%, 70.9%, and 87.8%, respectively. Moreover, we have extended this analysis to the analyses of _P_@5, _P_@7, and _P_@10, as shown in Table 6.

<table width="90%" border="1" cellspacing="0" cellpadding="3" align="center" style="border-right: #99f5fb solid; border-top: #99f5fb solid; font-size: smaller; border-left: #99f5fb solid; border-bottom: #99f5fb solid; font-style: normal; font-family: verdana, geneva, arial, helvetica, sans-serif; background-color: #fdffdd"><caption align="bottom">  
**Table 6: Average _P_@3, _P_@5, _P_@7, _P_@10 scores for different systems**</caption>

<tbody>

<tr>

<td align="left">**Average _P@N_**</td>

<td align="left">**_CatS_**</td>

<td>**_Highlight_**</td>

<td>**_Credo_**</td>

<td>**_Carrot2_**</td>

<td>**Google Proximity Search**</td>

<td>**_Google AdWords_**</td>

<td>**_Yahoo Search Marketing_**</td>

<td>**_Clusty_**</td>

<td>**WordTracker**</td>

<td>**LIK**</td>

</tr>

<tr>

<td align="left">Average _P_@3</td>

<td align="left">50.7%</td>

<td>72.8%</td>

<td>60.0%</td>

<td>77.4%</td>

<td>65.4%</td>

<td>79.8%</td>

<td>79.4%</td>

<td>80.9%</td>

<td>70.9%</td>

<td>87.8%</td>

</tr>

<tr>

<td align="left">Average _P_@5</td>

<td align="left">47.0%</td>

<td>69.1%</td>

<td>57.2%</td>

<td>72.2%</td>

<td>60.9%</td>

<td>75.2%</td>

<td>75.4%</td>

<td>77.9%</td>

<td>67.0%</td>

<td>85.5%</td>

</tr>

<tr>

<td align="left">Average _P_@7</td>

<td align="left">42.2%</td>

<td>62.9%</td>

<td>51.3%</td>

<td>68.9%</td>

<td>56.5%</td>

<td>70.1%</td>

<td>69.9%</td>

<td>73.1%</td>

<td>62.5%</td>

<td>79.6%</td>

</tr>

<tr>

<td align="left">Average _P_@10</td>

<td align="left">35.7%</td>

<td>58.0%</td>

<td>45.2%</td>

<td>61.8%</td>

<td>50.6%</td>

<td>64.6%</td>

<td>64.6%</td>

<td>66.0%</td>

<td>55.9%</td>

<td>74.6%</td>

</tr>

</tbody>

</table>

We then used SPSS 11.0 for Windows to analyse the results of above experiment. Considering the performance of _CatS_, _Highlight_, _Credo_, _Carrot2_,_Google Proximity Search_, _Google AdWords_, _Yahoo Search Marketing_, _Clusty_, _WordTracker_, and LIK. We used the statistical methodology, ANOVA analysis, to show that _F_<sub>(_PR_@3)</sub>=386.443, _F_<sub>(_PR_@5)</sub>=470.596, _F_<sub>(_PR_@7)</sub>=463.473, and _F_<sub>(_PR_@10)</sub>=496.528 (Table 7) are all greater than _F_<sub>0.001</sub>(9,380)=2.454 (F-distribution). This provides extremely strong evidence against the null hypothesis, indicating that there is a significant difference in the performance of different systems on the user's evaluation.

<table width="70%" border="1" cellspacing="0" cellpadding="3" align="center" style="border-right: #99f5fb solid; border-top: #99f5fb solid; font-size: smaller; border-left: #99f5fb solid; border-bottom: #99f5fb solid; font-style: normal; font-family: verdana, geneva, arial, helvetica, sans-serif; background-color: #fdffdd"><caption align="bottom">  
**Table 7: The results of the ANOVA analysis**</caption>

<tbody>

<tr>

<td colspan="2"></td>

<td>**Sum of Squares**</td>

<td>**Degree of Freedom**</td>

<td>**Mean Square**</td>

<td>**F**</td>

<td>**Sig.**</td>

</tr>

<tr>

<td rowspan="3">**_PR_@3**</td>

<td>**Between Groups**</td>

<td>4.348</td>

<td>9</td>

<td>0.483</td>

<td>386.443</td>

<td>0</td>

</tr>

<tr>

<td>**Within Groups**</td>

<td>0.475</td>

<td>380</td>

<td>0.001</td>

<td></td>

<td></td>

</tr>

<tr>

<td>**Total**</td>

<td>4.823</td>

<td>389</td>

<td></td>

<td></td>

<td></td>

</tr>

<tr>

<td rowspan="3">**_PR_@5**</td>

<td>**Between Groups**</td>

<td>4.417</td>

<td>9</td>

<td>0.491</td>

<td>470.596</td>

<td>0</td>

</tr>

<tr>

<td>**Within Groups**</td>

<td>0.396</td>

<td>380</td>

<td>0.001</td>

<td></td>

<td></td>

</tr>

<tr>

<td>**Total**</td>

<td>4.814</td>

<td>389</td>

<td></td>

<td></td>

<td></td>

</tr>

<tr>

<td rowspan="3">**_PR_@7**</td>

<td>**Between Groups**</td>

<td>4.367</td>

<td>9</td>

<td>0.485</td>

<td>463.473</td>

<td>0</td>

</tr>

<tr>

<td>**Within Groups**</td>

<td>0.398</td>

<td>380</td>

<td>0.001</td>

<td></td>

<td></td>

</tr>

<tr>

<td>**Total**</td>

<td>4.765</td>

<td>389</td>

<td></td>

<td></td>

<td></td>

</tr>

<tr>

<td rowspan="3">**_PR_@10**</td>

<td>**Between Groups**</td>

<td>4.520</td>

<td>9</td>

<td>0.502</td>

<td>496.528</td>

<td>0</td>

</tr>

<tr>

<td>**Within Groups**</td>

<td>0.384</td>

<td>380</td>

<td>0.001</td>

<td></td>

<td></td>

</tr>

<tr>

<td>**Total**</td>

<td>4.905</td>

<td>389</td>

<td></td>

<td></td>

<td></td>

</tr>

</tbody>

</table>

We conducted a _post hoc_ Fisher's least significant difference for pair-wise comparison at the 1% significance level. Because the results of least significant difference are tedious, we refer readers to the full report ([LIK 2009](#lik09)). As illustrated in the results of least significant difference, our system was found to overwhelmingly better than other systems.

For a large part of the query terms, the users did not like _CatS_ since it suggests keywords that only show the category names that derived from the dmoz taxonomy. __Credo__ only suggests keywords with a single term. __Highlight__ obtains the top-level suggested keywords by using a classification technology, so that they are few and of little use._Google Proximity Search_, _WordTracker_, _Google AdWords_, and _Yahoo Search Marketing_ are failing to suggest any keywords that do not contain the seed keyword. Although _Carrot2_ and _Clusty_ can create the suggested keywords with a semantic feature, however, they only use a pattern matching technique to analysis the Web snippet returned from different search engines. That is, they will fail to suggest the keywords if it do not appear in the Web snippet. Our system uses the methods of latent semantic analysis and probabilistic latent semantic analysis to construct the latent topics from the vector-space-model matrix and the suggested keywords are all based on these results. Thus, our system can guarantee any suggested keywords that have a synonymy or polysemy feature with the seed keyword. Moreover, our system can suggest the keywords with an association relationship since it uses a graph search method to derive the candidate keywords from a semantic graph. For example, in Figure 7, our system can suggest the keyword _isohunt.com_ (the most comprehensive bit torrent search engine) when the seed keyword is _p2p_.

### Experiment results on the initial parameters

In this experiment, we use the random and latent semantic analysis probability models to compare the performance of the log-likelihood function as described in equation (12) in order to decide the initial parameters.

The random probability model, RAND, uses a random probability as the initial parameters. The latent semantic analysis probability model first uses singular value decomposition to transform the vector-space-model matrix into the relevant latent semantic analysis parameters, then it uses a dual probability model to transform the relevant latent semantic analysis parameters into the initial parameters. According to the definition of the function _f_(_σ<sub>k</sub>_) in equation (9), the latent semantic analysis probability model can be divided into three submodels: (1) _f_(_σ<sub>k</sub>_)=_exp_(_σ<sub>k</sub>_) (_latent semantic analysis-prob_1_), (2) _f_(_σ<sub>k</sub>_)=_sinh_<sup>-1</sup>(_σ<sub>k</sub>_) (_latent semantic analysis-prob_2_), and (3) _f_(_σ<sub>k</sub>_)=_σ<sub>k</sub>_ (_latent semantic analysis-prob_3_).

Hofmann ([2004](#hof04)) concluded that three parameters, _M_ (the total number of query terms), _N_ (the total number of Web pages), and _L_ (the total number of topics), have a major impact on the performance of the log-likelihood function, thus, we experiment with three different cases. Let us now define _IRatio_ for _Model<sub>x</sub>_ based on the RAND model where _Model<sub>x</sub>_∈{RAND, _latent semantic analysis-prob_1_, _latent semantic analysis-prob_2_, _latent semantic analysis-prob_3_}, as shown in the following equation:

<div align="center">![equation](p425eq26.gif)</div>

where _L<sub>n</sub>_(_q<sub>i</sub>_,_d<sub>j</sub>_) in _Model<sub>x</sub>_ is the local optimal solution derived from _Model<sub>x</sub>_. The interested readers can simulate this experiment at [http://cayley.sytes.net/simulation/init_lik.php](http://cayley.sytes.net/simulation/init_lik.php).

In the first case, we focus on how to improve _IRatio_ for different _L_. In this case, we set _M_=1000, _N_=1000, and the range of _L_ from 10 to 200\. The simulation results for this case are shown in Figure 10 (a). We then average over all _IRatio_s, and the average values for each _Model<sub>x</sub>_ are 0% (RAND), 7.38% (_latent semantic analysis-prob_1_), 7.16% (_latent semantic analysis-prob_2_), and 7.12% (_latent semantic analysis-prob_3_), respectively.

<div align="center" id="fig-10">![Figure 10: The simulation results for the initial parameters](p425fig10.gif)</div>

<div align="center">  
**Figure 10: The simulation results for the initial parameters**</div>

Similarly, in the second and third cases, we focus on how to improve _IRatio_ for different _N_ and _M_. The simulation results are listed in Figures 10 (b) and (c). We also average over all _IRatios_ for the second case, and the average values for each _Model<sub>x</sub>_ are 0% (RAND), 8.69% (_latent semantic analysis-prob_1_), 8.56% (_latent semantic analysis-prob_2_), and 8.58% (_latent semantic analysis-prob_3_), respectively. For the third case, the average values for each _Model<sub>x</sub>_ are 0% (RAND), 6.19% (_latent semantic analysis-prob_1_), 7.23% (_latent semantic analysis-prob_2_), and 5.24% (_latent semantic analysis-prob_3_), respectively.

According to above experimental results, we concluded that the performance of the latent semantic analysis probability model is better than the random probability model. Moreover, no matter what experiments are performed, the performances of _latent semantic analysis-prob_1_, _latent semantic analysis-prob_2_, and _latent semantic analysis-prob_3_ are similar, which means that different _f_(_σ<sub>k</sub>_) functions will result in a near identical result for the latent semantic analysis probability model.

### Experiment results on the termination criteria

In this experiment, we pay attention to verify that intelligent probabilistic latent semantic analysis can yield a cost effective solution. The termination criteria have the following two cases: (1) it converges to the local optimal solution or (2) the consecutive number of iterations without improvement exceeds its maximum allowable number of iterations without significant improvement. In this experiment, we randomly chose the following parameters: _M_ (the total number of query terms), _N_ (the total number of Web pages), _L_ (the total number of topics), and _w_(_q<sub>i</sub>_,_d<sub>j</sub>_) (the weight of term _i_ in document _j_). The interested readers can simulate this experiment at [http://cayley.sytes.net/simulation/term_lik.php](http://cayley.sytes.net/simulation/term_lik.php).

The simulation results of two cases are shown in Figure 11, where _n_ is the number of iterations; #_IteNonImp<sub>n</sub>_ is the consecutive number of iterations without improvement. All other parameters, including _L<sub>n</sub>_(_q<sub>i</sub>_,_d<sub>j</sub>_), _Diff<sub>n</sub>_, _avg_(_Diff_<sub>_n_-1</sub>), _σ_(_Diff<sub>n</sub>_), _avg_(_σ_(_Diff_<sub>_n_-1</sub>)), and _MI<sub>n</sub>_ are as previously defined.

<div align="center" id="fig-11">![Figure 11: The simulation results of the termination criteria, where M = 370, N = 895, and L = 104](p425fig11.gif)</div>

<div align="center">  
**Figure 11: The simulation results of the termination criteria, where _M_ = 370, _N_ = 895, and _L_ = 104**</div>

In the first case, we set _ε_ equal to 0.01, which means that the improvement value of the log-likelihood function at the _n<sup>th</sup>_ iteration (_Diff<sub>n</sub>_) is less than or equal to 0.01\. In this simulation, the local optimal solution has already been reached at iteration 61\. At this time, we found that the value of the log-likelihood function is 8547.283874.

In the second case, the maximum required number of iterations has already been reached at iteration 43, where the consecutive number of iterations without improvement (#_IteNonImp<sub>n</sub>_=11) is larger than the maximum allowable number of iterations without significant improvement (_MI<sub>n</sub>_=4). At this time, we found that the value of the log-likelihood function is 8544.663281.

In this simulation, the termination criteria were reached at iteration 43 rather than iteration 61 since it takes additional 18 iterations to increase the value of the log-likelihood function only 2.620593\. It means that we perform additional computing resources than the second case, which result in little improvement.

For the second case, we further verify whether our method is a cost effective solution. In this verification, we also simulated 10,000 runs on overall performance improvement, to compare the number of iteration derived from the second case, SYSTEM, with some predefined number of iterations. At each run of this simulation, we also randomly chose the parameters of _M_, _N_, _L_, and _w_(_q<sub>i</sub>_,_d<sub>j</sub>_). The predefined number of iterations is based on the local optimal solution that can classify the number of iterations required to run into the following situations: _OPTIMAL_ (local optimal solution), _OPTIMAL-20_ (OPTIMAL minus 20) and _OPTIMAL-40_ (OPTIMAL minus 40). Let us now define achievement rate between the real value of the log-likelihood function and the local optimal solution as shown in the following:

<div align="center">![equation](p425eq27.gif)</div>

where _L<sub>τ</sub>_(_q<sub>i</sub>_,_d<sub>j</sub>_) denotes the value of the log-likelihood function derived from different _τ_s, where _τ_∈{_SYSTEM_, _OPTIMAL_, _OPTIMAL-20_, _OPTIMAL-40_}.

Table 8 shows all achievement rates over 10,000 simulation runs. For paper length limit, the number in each digit cell (except the first column and the last row) is the average value over 2,000 simulation runs. The average achievement rates for different _τ_s are 1 (_OPTIMAL_), 0.998425 (_OPTIMAL-20_), 0.998162 (_SYSTEM_), and 0.638627 (_OPTIMAL-40_), respectively.

<table width="70%" border="1" cellspacing="0" cellpadding="3" align="center" style="border-right: #99f5fb solid; border-top: #99f5fb solid; font-size: smaller; border-left: #99f5fb solid; border-bottom: #99f5fb solid; font-style: normal; font-family: verdana, geneva, arial, helvetica, sans-serif; background-color: #fdffdd"><caption align="bottom">  
**Table 8: Achievement rate for 10,000 simulation runs**</caption>

<tbody>

<tr>

<td align="left">**Number of Runs**</td>

<td>**OPTIMAL**</td>

<td>**OPTIMAL-20**</td>

<td>**SYSTEM**</td>

<td>**OPTIMAL-40**</td>

</tr>

<tr>

<td align="left">2000</td>

<td>1</td>

<td>0.998327</td>

<td>0.998132</td>

<td>0.642190</td>

</tr>

<tr>

<td align="left">4000</td>

<td>1</td>

<td>0.998604</td>

<td>0.998397</td>

<td>0.636356</td>

</tr>

<tr>

<td align="left">6000</td>

<td>1</td>

<td>0.998499</td>

<td>0.998174</td>

<td>0.636982</td>

</tr>

<tr>

<td align="left">8000</td>

<td>1</td>

<td>0.998423</td>

<td>0.998086</td>

<td>0.639718</td>

</tr>

<tr>

<td align="left">10000</td>

<td>1</td>

<td>0.998274</td>

<td>0.998023</td>

<td>0.637890</td>

</tr>

<tr>

<td align="left">Average</td>

<td>1</td>

<td>0.998425</td>

<td>0.998162</td>

<td>0.638627</td>

</tr>

</tbody>

</table>

Table 9 shows the number of iterations required to run for different _τ_s. The average number of iterations for different _τ_s are 58.41875 (_OPTIMAL_), 38.41875 (_OPTIMAL-20_), 31.36200 (_SYSTEM_), and 18.41875 (_OPTIMAL-40_), respectively. The average number of iterations for _OPTIMAL-20_ and _OPTIMAL-40_ can be derived from _OPTIMAL_. In the case of _SYSTEM_, the number of iterations fluctuates since each run was dynamically terminated.

<table width="70%" border="1" cellspacing="0" cellpadding="3" align="center" style="border-right: #99f5fb solid; border-top: #99f5fb solid; font-size: smaller; border-left: #99f5fb solid; border-bottom: #99f5fb solid; font-style: normal; font-family: verdana, geneva, arial, helvetica, sans-serif; background-color: #fdffdd"><caption align="bottom">  
**Table 9: Number of iterations for 10,000 simulation runs**</caption>

<tbody>

<tr>

<td align="left">**Number of Runs**</td>

<td>**OPTIMAL**</td>

<td>**OPTIMAL-20**</td>

<td>**SYSTEM**</td>

<td>**OPTIMAL-40**</td>

</tr>

<tr>

<td align="left">2000</td>

<td>58.28225</td>

<td>38.28225</td>

<td>31.19150</td>

<td>18.28225</td>

</tr>

<tr>

<td align="left">4000</td>

<td>58.13029</td>

<td>38.13029</td>

<td>31.17996</td>

<td>18.13029</td>

</tr>

<tr>

<td align="left">6000</td>

<td>58.28259</td>

<td>38.28259</td>

<td>31.27647</td>

<td>18.28259</td>

</tr>

<tr>

<td align="left">8000</td>

<td>58.70122</td>

<td>38.70122</td>

<td>31.58823</td>

<td>18.70122</td>

</tr>

<tr>

<td align="left">10000</td>

<td>58.69741</td>

<td>38.69741</td>

<td>31.57382</td>

<td>18.69741</td>

</tr>

<tr>

<td align="left">Average</td>

<td>58.41875</td>

<td>38.41875</td>

<td>31.36200</td>

<td>18.41875</td>

</tr>

</tbody>

</table>

For any two cases, we define cost effective ratio between _τ_1 and _τ_2 by dividing the increased achievement rate by the increased percentage of the number of iterations as follows:

<div align="center">![equation](p425eq28.gif)</div>

Using _τ_2=_OPTIMAL-40_ as a benchmark, the cost effective ratio values for different _τ_s, _SYSTEM_, _OPTIMAL-20_, and _OPTIMAL_ are shown in Table 10\. We found that _τ_1=_SYSTEM_ significantly outperforms other _τ_s, and the cost effective ratio values drop rapidly beyond _τ_1=_SYSTEM_.

<table width="70%" border="1" cellspacing="0" cellpadding="3" align="center" style="border-right: #99f5fb solid; border-top: #99f5fb solid; font-size: smaller; border-left: #99f5fb solid; border-bottom: #99f5fb solid; font-style: normal; font-family: verdana, geneva, arial, helvetica, sans-serif; background-color: #fdffdd"><caption align="bottom">  
**Table 10: Cost effective ratios for different _τ_s based on _τ_2="OPTIMAL-40"**</caption>

<tbody>

<tr>

<td align="left"></td>

<td>**OPTIMAL-40**</td>

<td>**SYSTEM**</td>

<td>**OPTIMAL-20**</td>

<td>**OPTIMAL**</td>

</tr>

<tr>

<td align="left">_Average Achievement Rate_</td>

<td>0.638627</td>

<td>0.998162</td>

<td>0.998425</td>

<td>1</td>

</tr>

<tr>

<td align="left">_Average Number of Iterations_</td>

<td>18.41875</td>

<td>31.36200</td>

<td>38.41875</td>

<td>58.41875</td>

</tr>

<tr>

<td align="left">_Improved Average Achievement Rate_</td>

<td></td>

<td>0.562981208</td>

<td>0.563393</td>

<td>0.565859</td>

</tr>

<tr>

<td align="left">_Improved Average Number of Iteration Ratio_</td>

<td></td>

<td>0.702721412</td>

<td>1.085850</td>

<td>2.171700</td>

</tr>

<tr>

<td align="left">_Cost Effective Ration_</td>

<td></td>

<td>0.801144236</td>

<td>0.518850</td>

<td>0.260561</td>

</tr>

</tbody>

</table>

In summary, we conclude that our method can yield a cost effective solution in a comparatively short amount of time.

## Conclusions and future work

In this paper, we presented an integrated keyword suggestion system that consists of two stages: training and suggestion. The training stage applies the latent semantic analysis and probabilistic latent semantic analysis methods to form the training parameter. Then, the suggestion stage applies a semantic graph to generate a list of suggested keywords. The suggested keywords generated from our system have a strong semantic relationship between the user's query and each suggested keyword.

This paper has three main contributions: first, we have presented a high-performance keyword suggestion system. According to the results of the simulation and user evaluation studies, our system was found to be better than other online systems. Secondly, we have shown that the value of the log-likelihood function obtained from our system is a cost effective solution in a comparatively short amount of time. Thirdly, we also have shown that the initial parameters obtained from the latent semantic analysis probability model are superior to the random probability model.

Currently, we used the latent semantic analysis probability model as the initial parameters since singular value decomposition may introduce negative values in the result of latent semantic analysis and such values cannot be treated as a probability distribution. In the future, we plan to use the non-negative matrix factorization model to deal with the problem of negative values in the process of singular value decomposition. On the other hand, the suggested keywords may be out-of-date since the training stage uses a batch processing to update the relevant parameters. We also plan to integrate the Web snippet analysis into our training stage to suggest up-to-date keywords.

## Acknowledgements

This work was supported in part by National Science Council, Taiwan under grant NSC 97-2221-E-259-026.

## About the author

Lin-Chih Chen is an assistant professor in the Department of Information Management at National Dong Hwa University, Taiwan. His research interests include Web intelligent and Web technology. He develops many Web intelligent systems include the Cayley search engine, the LIK keyword suggestion system, the Cayley digital content system, the iClubs community, language agents, and a Web snippet clustering system. He is also a leader of the Cayley group. He can be contacted at [lcchen@mail.ndhu.edu.tw](mailto:lcchen@mail.ndhu.edu.tw)

## References

*   <a id="aol06" name="aol06"></a>AOL. (2006). [AOL search data](http://www.webcitation.org/5nnpHYBQe). Retrieved 7 November, 2009 from http://www.gregsadetsky.com/aol-data/ (Archived by WebCite® at http://www.webcitation.org/5nnpHYBQe)
*   <a id="bel08" name="bel08"></a>Bellegarda, J.R. (2008). _Latent semantic mapping: principles and applications._ San Rafael, CA: Morgan & Claypool Publishers.
*   <a id="bra05" name="bra05"></a>Brants, T. (2005). Test data likelihood for PLSA models. _Information Retrieval_, **8**(2), 181-196.
*   <a id="bra02" name="bra02"></a>Brants, T. & Stolle, R. (2002). Finding similar documents in document collections. In _Proceedings of Third International Conference on Language Resources and Evaluation, Las Palmas, Spain_. Paris: ELRA.
*   <a id="car04" name="car04"></a>Carpineto, C. & Romano, G. (2004). Exploiting the potential of concept lattices for information retrieval with Credo. _Journal of Universal Computer Science_, **10**(8), 985-1013.
*   <a id="che05" name="che05"></a>Chen, L.C. & Luh, C.J. (2005). Web page prediction from MetaSearch results. _Internet Research: Electronic Networking Applications and Policy_, **15**(4), 421-446.
*   <a id="dee90" name="dee90"></a>Deerwester, S., Dumais, S.T., Furnas, G.W., Landauer, T.K. & Harshman, R. (1990). Indexing by latent semantic analysis. _Journal of the American Society for Information Science and Technology_, **41**(6), 391-407.
*   <a id="dem77" name="dem77"></a>Dempster, A.P., Laird, N.M. & Rubin, D.B. (1977). Maximum likelihood from incomplete data using the EM algorithm. _Journal of the Royal Statistical Society_, Series B **39**(1), 1-38.
*   <a id="din05" name="din05"></a>Ding, C.H.Q. (2005). A probabilistic model for latent semantic indexing. _Journal of the American Society for Information Science and Technology_, **56**(6), 597-608.
*   <a id="dog08" name="dog08"></a>Dogpile. (2008). [The project of keyword suggestion: listing of testing keywords](http://www.webcitation.org/5nnp2lF7I). Retrieved 7 November, 2009 from http://cayley.sytes.net/lik_english/listing_all_testing_keywords.php (Archived by WebCite® at http://www.webcitation.org/5nnp2lF7I)
*   <a id="ell06" name="ell06"></a>Elliott, S. (2006). [More agencies investing in marketing with a click](http://www.webcitation.org/5nnpRUwl9). Retrieved November 7, 2009 from http://www.nytimes.com/2006/03/14/business/media/14adco.html?ex=1299992400&en=6fcd30b948dd1312&ei=5088 (Archived by WebCite® at http://www.webcitation.org/5nnpRUwl9)
*   <a id="gib05" name="gib05"></a>Gibson, S., Wills, A. & Ninness, B. (2005). Maximum-likelihood parameter estimation of bilinear systems. _IEEE Transactions on Automatic Control_, **50**(10), 1581-1596.
*   <a id="goo06" name="goo06"></a>Google. (2006). [_Google AdWords: keyword tool_](http://www.webcitation.org/5nnpigkeq). Retrieved 7 November, 2009 from https://adwords.google.com/select/KeywordToolExternal (Archived by WebCite® at http://www.webcitation.org/5nnpigkeq)
*   <a id="goo07" name="goo07"></a>Google. (2007). [2007 year-end zeitgeist](http://www.webcitation.org/5nnpu3kuc). Retrieved 7 November, 2009 from http://www.google.com/intl/en/press/zeitgeist2007/index.html (Archived by WebCite® at http://www.webcitation.org/5nnpu3kuc)
*   <a id="goo08" name="goo08"></a>Google. (2008). [Google investor relations](http://www.webcitation.org/5nnq2hc1N). Retrieved 7 November, 2009 from http://investor.google.com/fin_data.html (Archived by WebCite® at http://www.webcitation.org/5nnq2hc1N)
*   <a id="hof99" name="hof99"></a>Hofmann, T. (1999). [Probabilistic latent semantic indexing](http://www.webcitation.org/5nnq9rduJ). In _Proceedings of the 22th Annual International SIGIR Conference on Research and Development in Information Retrieval_ Berkeley, California, United States. (pp. 50-57). New York, NY: ACM Press. Retrieved November 7, 2009, from http://www.cs.brown.edu/~th/papers/Hofmann-SIGIR99.pdf (Archived by WebCite® at http://www.webcitation.org/5nnq9rduJ).
*   <a id="hof01" name="hof01"></a>Hofmann, T. (2001). Unsupervised learning by probabilistic latent semantic analysis. _Machine Learning_, **42**(1-2), 177-196.
*   <a id="hof04" name="hof04"></a>Hofmann, T. (2004). Latent semantic models for collaborative filtering. _ACM Transactions on Information Systems_, **22**(1), 89-115.
*   <a id="inf08" name="inf08"></a>InfoSpace. (2008). [Dogpile SearchSpy](http://www.webcitation.org/5nnqNINPT). Retrieved 7 November, 2009 from http://www.dogpile.com/dogpile/ws/searchspy/rfcid=4101/rfcp=InternalNavigation/_iceUrlFlag=11?_IceUrl=true (Archived by WebCite® at http://www.webcitation.org/5nnqNINPT)
*   <a id="ino05" name="ino05"></a>Inoue, M. (2005). The remarkable search topic-finding task to share success stories of cross-language information retrieval. In _Proceedings of the Fifth Workshop on Important Unresolved Matters_ (pp. 61-64), Seattle, United States. New York, NY: ACM Press.
*   <a id="ish02" name="ish02"></a>Ishida, K., & Ohta, T. (2002). An approach for organizing knowledge according to terminology and representing it visually. _IEEE Transactions on Systems, Man, and Cybernetics - Part C: Applications and Reviews_, **32**(4), 366-373.
*   <a id="jan08" name="jan08"></a>Jansen, B.J. & Mullen, T. (2008). Sponsored search: an overview of the concept, history, and technology. _International Journal of Electronic Business_, **6**(2), 114-131.
*   <a id="kun08" name="kun08"></a>Kunder, M.D. (2008). [The size of the World Wide Web](http://www.webcitation.org/5nnqVVisf). Retrieved 7 November, 2009 from http://worldwidewebsize.com/ (Archived by WebCite® at http://www.webcitation.org/5nnqVVisf)
*   <a id="lem00" name="lem00"></a>Lempel, R. & Moran, S. (2000). The stochastic approach for link-structure analysis (SALSA) and the TKC effect. _Computer Networks_, **33**(1-6), 387-401.
*   <a id="lik09" name="lik09"></a>LIK. (2009). [LIK's evaluation results](http://www.webcitation.org/5nnqau3jr). Retrieved 7 November, 2009 from http://cayley.sytes.net/questionnaire/spss_output.htm (Archived by WebCite® at http://www.webcitation.org/5nnqau3jr)
*   <a id="lve05" name="lve05"></a>Lves, G. (2005). [Cost-per-click (CPC) - what's your focus?](http://www.webcitation.org/5nnqhNCjd) Retrieved 7 November, 2009 from http://www.searchengineguide.com/senews/004895.html (Archived by WebCite® at http://www.webcitation.org/5nnqhNCjd)
*   <a id="lyc07" name="lyc07"></a>Lycos. (2007). [Top search terms for 2007](http://www.webcitation.org/5nnqnaRaV). Retrieved November 7, 2009 from http://www.lycos.com/ (Archived by WebCite® at http://www.webcitation.org/5nnqnaRaV)
*   <a id="mar00" name="mar00"></a>Markatou, M. (2000). Mixture models, robustness, and the weighted likelihood methodology. _Biometrics_, **56**(2), 483-486.
*   <a id="met07" name="met07"></a>Metaxoglou, K. & Smith, A. (2007). Maximum likelihood estimation of VARMA models using a stage-space EM algorithm. _Journal of Time Series Analysis_, **28**(5), 666-685.
*   <a id="mic06" name="mic06"></a>Microsoft. (2006). [Microsoft adCenter](http://www.webcitation.org/5nnqx1C9z). Retrieved November 7, 2009 from http://adcenter.microsoft.com/ (Archived by WebCite® at http://www.webcitation.org/5nnqx1C9z)
*   <a id="mor07" name="mor07"></a>Mordkovich, B. & Mordkovich, E. (2007). _Pay-per-click search engine marketing handbook: low cost strategies for attracting new customers using Google, MSN, Yahoo & other search engines_. New York, NY: MordComm, Inc.
*   <a id="mor01" name="mor01"></a>Morris, C.G. & Maisto, A.A. (2001). _Psychology: an introduction._ Englewood Cliffs, NJ: Prentice Hall.
*   <a id="ngu07" name="ngu07"></a>Nguyen, V., Gachter, S., Martinelli, A., Tomatis, N. & Siegwart, R. (2007). A comparison of line extraction algorithms using 2D range data for indoor mobile robotics. _Autonomous Robots_, **23**(2), 97-111.
*   <a id="nis05" name="nis05"></a>National Information Standards Organization. (2005). _ANSI/NISO Z39.19-2005 guidelines for the construction, format, and management of monolingual controlled vocabularies._ Baltimore, MD: NISO Press.
*   <a id="osi05" name="osi05"></a>Osinski, S., & Weiss, D. (2005). A concept-driven algorithm for clustering search results. _IEEE Intelligent Systems_, **20**(3), 48-54.
*   <a id="pae00" name="pae00"></a>Paepcke, A., Garcia-Molina, H., Rodriguez-Mula, G. & Cho, J. (2000). Beyond document similarity: understanding value-based search and browsing technologies. _SIGMOD Record_, **29**(1), 80-92.
*   <a id="pet05" name="pet05"></a>Petersen, K.B. & Winther, O. (2005). The EM algorithm in independent component analysis. In _Proceedings of the IEEE International Conference on Acoustics, Speech and Signal Processing 2005_ (pp. 169-172), Philadelphia, United States. New York, NY: IEEE Press.
*   <a id="rad06" name="rad06"></a>Radovanovic M. & Ivanovic M. (2006). _CatS_: a classification-powered meta-search engine. _Advances in Web Intelligence and Data Mining_, **23**(1), 191-200.
*   <a id="ran08" name="ran08"></a>Ranks, N.L. (2008). [Keyword proximity analyser](http://www.webcitation.org/5nnr3Zihz). Retrieved 7 November, 2009 from http://www.ranks.nl/tools/proximity.html (Archived by WebCite® at http://www.webcitation.org/5nnr3Zihz)
*   <a id="ris98" name="ris98"></a>Ristad, E.S. & Yianilos, P.N. (1998). Learning string-edit distance. _IEEE Transactions on Pattern Analysis and Machine Intelligence_, **20**(5), 522-532.
*   <a id="sal89" name="sal89"></a>Salton, G. (1989). _Automatic text processing: the transformation, analysis, and retrieval of information by computer._ Reading, MA: Addison Wesley.
*   <a id="sar07" name="sar07"></a>Saremi, S. (2007). [Top search terms for 2007](http://www.webcitation.org/5nnrBR9DC). Retrieved 7 November, 2009 from http://www.searchviews.com/index.php/archives/2007/12/top-search-terms-for-2007.php (Archived by WebCite® at http://www.webcitation.org/5nnrBR9DC)
*   <a id="seg07" name="seg07"></a>Segev, A., Leshno, M. & Zviran, M. (2007). Context recognition using Internet as a knowledge base. _Journal of Intelligent Information Systems_, **29**(3), 305-327.
*   <a id="she08" name="she08"></a>Sherman, C. (2008). [The state of search engine marketing 2007](http://www.webcitation.org/5nnrGvRFh). Retrieved November 7, 2009 from http://searchengineland.com/the-state-of-search-engine-marketing-2007-13580.php (Archived by WebCite® at http://www.webcitation.org/5nnrGvRFh)
*   <a id="spi01" name="spi01"></a>Spink, A., Wolfram, D., Jansen, M.B.J. & Saracevic, T. (2001). Searching the Web: the public and their queries. _Journal of the American Society for Information Science and Technology_, **52**(3), 226-234.
*   <a id="tso01" name="tso01"></a>Tsoi, A.C. (2001). Structure of the Internet? In _Proceedings of 2001 International Symposium on Intelligent Multimedia, Video and Speech Processing, Hong Kong_. (pp. 449-452) New York, NY: IEEE Press.
*   <a id="wor08" name="wor08"></a>Wordtracker. (2008). [_Free keyword suggestion tool from WordTracker_](http://www.webcitation.org/5nnrMytoJ). Retrieved 7 November, 2009 from http://freekeywords.wordtracker.com/ (Archived by WebCite® at http://www.webcitation.org/5nnrMytoJ)
*   <a id="wu03" name="wu03"></a>Wu, Y.-F., & Chen, X. (2003). Extracting features from Web search returned hits for hierarchical classification. In _Proceedings of the International Conference on Information and Knowledge Engineering_, Las Vegas, Nevada, United States. (pp. 103-108) New York, NY: CSREA Press.
*   <a id="yah06" name="yah06"></a>Yahoo. (2006). [Start advertising with Yahoo! Search Marketing](http://www.webcitation.org/5nnrWYJFo). Retrieved 7 November, 2009 from https://signup13.marketingsolutions.yahoo.com/ (Archived by WebCite® at http://www.webcitation.org/5nnrWYJFo)
*   <a id="zha01" name="zha01"></a>Zhang, Q. & Goldman, S.A. (2001). EM-DD: an improved multiple-instance learning technique. _Neural Information Processing Systems_, **14**(1), 1073-1080.
*   <a id="zha08" name="zha08"></a>Zhang, Z. & Nasraoui, O. (2008). Mining search engine query logs for social filtering-based query recommendation. _Applied Soft Computing_, **8**(4), 1326-1334.

