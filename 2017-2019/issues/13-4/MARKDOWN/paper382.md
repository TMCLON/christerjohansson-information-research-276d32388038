####  vol. 13 no. 4, December, 2008

# Analysis of the similarity of the responses of Web search engines to user queries: a user perspective

#### J.V. Rodríguez Jr., [F.J. Martínez](mailto:javima@um.es) and [J.V. Rodríguez.](mailto:jovi@um.es)  
Department of Information and Documentation, University of Murcia. Campus of Espinardo - Murcia, Spain

#### Abstract

> **Introduction.** We report an investigation into the similarity of the responses of Web search engines. We discuss the coincidence of documents and their position in the response, in order to develop a measure closest to the user's context by incorporating several aspects and reflections established within this field of study.  
> **Method.** We introduce a method of calculation based in the cosine function, slightly adapted. Initially, calculations were performed manually and to simplify the process we have implemented a meta-searcher.  
> **Analysis.** We applied a first set of thirty questions to these systems during different periods of time. Secondly, we examined the similarity of the documents returned in the top ten, twenty and thirty positions. Subsequently, we conducted another round of searches (with fewer terms in the equations) to verify whether it affected the average values of similarity.  
> **Conclusions.** The estimated similarity is low, between 15% and 18%, and it has not changed significantly over the past five years. The number of terms used in the searches does not affect these averages.



## Introduction

Web information retrieval systems have been evaluated almost from the origin and implementation of the Web. This should not surprise us because the need for evaluation has always accompanied the development of information retrieval systems. A broad set of qualitative and quantitative aspects have been evaluated. We can group them into four fields of interest: (i) performance, usually based in the effectiveness as we can see in Oppenheim ([2000](#Oppenheim)) and Martínez & Rodríguez ([2003](#Martinez2003)), with a supplementary set of works that avoid the use of the precision ratio to measure the effectiveness because it is affected by human subjectivity ([Hersh _et al._ 1995](#Hersh), [Landoni and Bell 2000](#Landoni)); (ii) the proposal of Berners-Lee _et al._ ([2001](#Berners-Lee)) and the World Wide Web Consortium for a semantic Web based upon an extensive use of metadata, which has been evaluated by Zhang and Dimitroff ([2005a](#Zhang2005a)) ([2005b](#Zhang2005b)); (iii) how users search the Web ([Spink _et al._ 1998](#Spink1998)), ([Spink and Jansen 2004](#Spink2004)), ([Jansen and Spink 2006](#Jansen2006)) and (iv) the system-user interaction ([Schlichting and Nilsen 1997](#Schlichting)),([Johnson _et al._ 2001](#Johnson)) and Marchionini ([2004](#Marchionini)).

Leaving aside the nature of these engines, what could be the origin of this interest? We suppose that it may due to questions like '_Dear Professor, what is the best Web retrieval system?_' This question might be answered (by the professor) saying, '_Probably the answer depends on the point of view of the persons who will make the analysis_'. It is logical that, if they rate effectiveness as more important, they will consider measures such as time of response, precision, recall and overlap. To improve precision, they could measure the influence of metadata, a matter not sufficiently resolved today. Perhaps, the researcher will prefer to know the trends of Web usage, then analyse Web queries, the use of Boolean operators, Web query reformulation, the use of relevance feedback and viewing results. Finally, if they consider the interaction between systems and people, they will focus their study the interface design and other usability aspects that could affect information retrieval.

While there is great diversity among these lines of work, we think that it is possible to integrate some of them for adding an user's perspective to the traditional evaluation of performance. More concretely, we propose to incorporate data about the position a document in the search output like a measure of the overlap between the Web retrieval systems, with the goal of transforming a simple measure of coincidence of documents in a response to an extent of the overlap of documents in the useful response for users. It seeks to combine different viewpoints with the idea of bringing added value to the ratios that have so far been used.

It is a fact that the Web retrieval systems index large collections of documents. It is also true that the similarity between these indexes is very small. It has been traditionally assumed that this similarity is approximately 15%. If this is correct (usually this kind of comments is not supported by any study), it would mean an enormous diversity in the composition of these indexes which, in some way, most people would see when performing the same search in different systems (which, incidentally, is becoming less frequent). Nevertheless, another factor intervenes in the diversity of the reply, which is the ranking algorithm the systems use to provide the response. Each system implements a different algorithm; consequently, the level of divergence of the response the users can see is even greater.

Which of the levels of similarity -or divergence- is the most interesting for our analysis? From the point of view of the end user, we would choose that of the given response and, from the point of view of the administrator of a Web retrieval system, it would also be interesting to analyse the composition of the indexes, but for the users of the Web this is less important. We should not forget that it is very difficult to have access to all of these collections in order to analyse them. We can only find data on this concordance in the works of Losjland ([2000a](#Ljosland2000a); [2000b](#Ljosland2000b)) and Martínez ([2002](#Martinez2002)), besides the data on the overlap of Web retrieval systems which Notess ([2002](#Notess)) took into account for the [Search Engine Showdown](http://searchengineshowdown.com/) blog (data not updated) and more recently Jansen and Spink ([2006](#Jansen2006)). So, it is difficult to find more sources of updated information on this subject.

For this reason, we find it interesting to bring about a method enabling us to carry out a periodical analysis of this factor and to use it in the response of the most used Web retrieval systems in the current World Wide Web.

## Our original proposal

Our initial research was included in the field of the performance assessment. The most quoted projects are those related to effectiveness, particularly the work of [Chu and Rosenthal (1996)](#Chu), which analyses more features. We should also mention the contributions of [Leighton and Svristava (1999)](#Leighton), and finally, the work of [Gordon and Pathak (1999)](#Gordon), who analysed more systems than anyone else. One of the first experiments developed in [Martinez (2002)](#Martinez2002) determined the level of similarity in the responses of six Web retrieval systems (Google, Altavista, All the Web, Terra, MSN, and Wisenut). Thirty queries (in Spanish) were carried out in these systems and the level of similarity was analysed among the first ten, twenty and thirty documents of the response. In order to determine this similarity, and inspired by [Lojsland (2000a)](#Ljosland2000a), we used a the 'cosine' similarity function [(Salton & Harman, 1983)](#Salton) with the necessary adjustments to the context of the experiment, since this function was created in order to determine the similarity of two one-dimensional vectors and, in this case, we had bi-dimensional vectors: the Web search engine and its reply to a given question.

Why the limit of thirty documents, which is obviously a very small portion of the possible response?. [Spink and Jansen (2004)](#Spink2004) give us the justification:

> '.from 1996 to 1999, for more than 70 percent of the time, a user only viewed the top ten results. On average, users viewed 2.35 pages of results (where one page equals ten hits). Over half the users did not access results beyond the first page. [Jansen et al.(1998)](#Jansen1998) found that more three in four users did not go beyond viewing two pages. By 2001, only roughly one-thirs of users looked beyond the second page of Web sites retrieved.

We can find similar actions in [Tang and Sun (2003)](#Tang) where the authors, basing their work on that of of [Jansen et al.(1998)](#Jansen1998):

> '.decided to collect only the top 20 links among the thousands retrieved in light of previous studies showing that 80 percent of users view only the first two pages of results'.

[Jansen and Spink (2006)](#Jansen2006) affirm that "the first result page represents the top results that an engine found for a given query and therefore is a barometer for the most relevant results an engine has to offer". It seems clear that thirty is the maximum number that most users are willing to consult. It is the useful response, the rest of the documents are ignored. In practice, it is possible that we are setting too high a value to this limit.

As discussed above, we introduced several changes in the 'cosine' similarity function to approach it to the context of the experiment, since this function was created in order to determine the similarity of two one-dimensional vectors and, in this case, we had bi-dimensional vectors: the Web retrieval system and the reply to a given question. Obviously, it was necessary to resize the results before using this function but it was not the unique change introduced into this calculation. We consider the position of documents in the response, favouring those that appeared in the top positions. Thus, the weight of each resulting document depending on its position in the response vector of the Web retrieval system (known as the 'relevance factor') was taken into account. This idea is based on the '_first 20 full precision_' idea introduced by [Leighton and Srivastava (1999)](#Leighton) which gave an added value to the ability to place relevant documents within the first twenty delivered in response to the user. This function measured at the same time, accuracy and the capacity to show the relevant documents before the irrelevant (something very important for the user). If you regard inactive and duplicate documents as irrelevant, you favour those search engines that are up to date through the refreshment of their indexes. This factor enabled us to assess not only the coincidence of the documents in the response (that is, the overlap), but also in trying to assess the similarity of the useful response (those the user actually reads) taking into account the order these documents in the response.

Before calculating the similarity, we have to resolve an additional question, the type of operators to be used in the query formulation. We used (1) Boolean operators (more concretely, the 'AND' operator) and (2) the 'AND' operator combined with the 'exact phrase'. The obtained results were very similar. Noting further that the use of Boolean operators is growing on the Web [(Spink and Jasen 2004)](#Spink2004), we consider that it is appropriate to experiment only with such operators.

### An example.

To exemplify the method, suppose that a search has been carried out in the Web retrieval system A and in the Web retrieval system B. The results are represented in the following **Table 1** (the coinciding URLs are in bold). The column on the right shows the weight given to each URL (in bold) depending on its position (the relevance factor):

<table width="80%" border="1" cellspacing="0" cellpadding="3" align="center" style="border-right: #99f5fb solid; border-top: #99f5fb solid; font-size: smaller; border-left: #99f5fb solid; border-bottom: #99f5fb solid; font-style: normal; font-family: verdana, geneva, arial, helvetica, sans-serif; background-color: #fdffdd"><caption align="bottom">  
**Table 1:** **Example of calculation of the cosine function adapted to our experiment**</caption>

<tbody>

<tr>

<th height="16" width="251">Web retrieval system A</th>

<th height="16" width="274">Web retrieval system B</th>

<th height="16" width="91">Weight</th>

</tr>

<tr>

<td height="16" width="251">**http://www.first.com**</td>

<td height="16" width="274">**http://www.first.com**</td>

<td align="center" height="16" width="91">1</td>

</tr>

<tr>

<td height="16" width="251">**http://www.second.com**</td>

<td height="16" width="274">http://www.two.com</td>

<td align="center" height="16" width="91">0.99</td>

</tr>

<tr>

<td height="16" width="251">**http://www.third.com**</td>

<td height="16" width="274">http://three.com</td>

<td align="center" height="16" width="91">0.98</td>

</tr>

<tr>

<td height="16" width="251">http://www.fourth.com</td>

<td height="16" width="274">**http://www.second.com**</td>

<td align="center" height="16" width="91">0.97</td>

</tr>

<tr>

<td height="16" width="251">**http://www.fifth.com**</td>

<td height="16" width="274">**http://www.fifth.com**</td>

<td align="center" height="16" width="91">0.96</td>

</tr>

<tr>

<td height="16" width="251">**http://www.sixth.com**</td>

<td height="16" width="274">**http://www.sixth.com**</td>

<td align="center" height="16" width="91">0.95</td>

</tr>

<tr>

<td height="16" width="251">http://www.seventh.com</td>

<td height="16" width="274">**http://www.third.com**</td>

<td align="center" height="16" width="91">0.94</td>

</tr>

<tr>

<td height="16" width="251">http://www.eighth.com</td>

<td height="16" width="274">http://www.eight.com</td>

<td align="center" height="16" width="91">0.93</td>

</tr>

</tbody>

</table>

As previously mentioned, there is a distribution of elements with two characteristics: URL and 'weight' or relevance factor of the objective. In order to determine the similarity it is necessary to reduce the distribution achieved to a common n-dimensional space where 'n' is the number of coinciding URLs for each of the pair of vectors of the results plus the number of the relevant URLs found by each separate search engine. In order to do this, the initial vectors of the results become two individual vectors composed of the values of the relevance factor presented by each URL in the original search engines. This transformation of the vector space leads to **Table 2** which represents the vector of global result and the vectors V (Web retrieval system A) and V (Web retrieval system B):

<table width="80%" border="1" cellspacing="0" cellpadding="3" align="center" style="border-right: #99f5fb solid; border-top: #99f5fb solid; font-size: smaller; border-left: #99f5fb solid; border-bottom: #99f5fb solid; font-style: normal; font-family: verdana, geneva, arial, helvetica, sans-serif; background-color: #fdffdd"><caption align="bottom">  
**Table 2:** **Transformation of the initial vectors of our experiment.**</caption>

<tbody>

<tr>

<th height="16" width="251">Result vector</th>

<th height="16" width="182">V(Web retrieval system A)</th>

<th height="16" width="205">V(Web retrieval system B)</th>

</tr>

<tr>

<td height="16" width="251">**http://www.first.com**</td>

<td height="16" width="182" align="center">1</td>

<td height="16" width="205" align="center">1</td>

</tr>

<tr>

<td height="16" width="251">**http://www.second.com**</td>

<td height="16" width="182" align="center">0.99</td>

<td height="16" width="205" align="center">0.97</td>

</tr>

<tr>

<td height="16" width="251">**http://www.third.com**</td>

<td height="16" width="182" align="center">0.98</td>

<td height="16" width="205" align="center">0.94</td>

</tr>

<tr>

<td height="16" width="251">http://www.fourth.com</td>

<td height="16" width="182" align="center">0.97</td>

<td height="16" width="205" align="center">0</td>

</tr>

<tr>

<td height="16" width="251">**http://www.fifth.com**</td>

<td height="16" width="182" align="center">0.96</td>

<td height="16" width="205" align="center">0.96</td>

</tr>

<tr>

<td height="16" width="251">**http://www.sixth.com**</td>

<td height="16" width="182" align="center">0.95</td>

<td height="16" width="205" align="center">0.95</td>

</tr>

<tr>

<td height="16" width="251">http://www.seventh.com</td>

<td height="16" width="182" align="center">0.94</td>

<td height="16" width="205" align="center">0</td>

</tr>

<tr>

<td height="16" width="251">http://www.eighth.com</td>

<td height="16" width="182" align="center">0.93</td>

<td height="16" width="205" align="center">0</td>

</tr>

<tr>

<td height="16" width="251">http://www.two.com</td>

<td height="16" width="182" align="center">0</td>

<td height="16" width="205" align="center">0.99</td>

</tr>

<tr>

<td height="16" width="251">http://three.com</td>

<td height="16" width="182" align="center">0</td>

<td height="16" width="205" align="center">0.98</td>

</tr>

<tr>

<td height="16" width="251">http://www.eight.com</td>

<td height="16" width="182" align="center">0</td>

<td height="16" width="205" align="center">0.93</td>

</tr>

</tbody>

</table>

Now we can calculate the cosine function with these two new vectors:

<table width="80%" border="1" cellspacing="0" cellpadding="3" align="center" style="border-right: #99f5fb solid; border-top: #99f5fb solid; font-size: smaller; border-left: #99f5fb solid; border-bottom: #99f5fb solid; font-style: normal; font-family: verdana, geneva, arial, helvetica, sans-serif; background-color: #fdffdd"><caption align="bottom">  
**Table 3: Final calculation of the similarity function**</caption>

<tbody>

<tr>

<th height="16" width="251">Result vector</th>

<th height="16" width="182">V(A)=  
V(Web retrieval system A)</th>

<th height="16" width="205">V(B)= V(Web retrieval system B)</th>

<th height="16" width="205">V(A).V(B) (scalar product)</th>

<th height="16" width="205">[V(A)]<sup><font face="Verdana">2</font></sup></th>

<th height="16" width="205">[V(B)]<sup><font face="Verdana">2</font></sup></th>

</tr>

<tr>

<td height="16" width="251">**http://www.first.com**</td>

<td height="16" width="182" align="center">1</td>

<td height="16" width="205" align="center">1</td>

<td height="16" width="205" align="center">1</td>

<td height="16" width="205" align="center">1</td>

<td height="16" width="205" align="center">1</td>

</tr>

<tr>

<td height="16" width="251">**http://www.second.com**</td>

<td height="16" width="182" align="center">0.99</td>

<td height="16" width="205" align="center">0.97</td>

<td height="16" width="205" align="center">0.96</td>

<td height="16" width="205" align="center">0.98</td>

<td height="16" width="205" align="center">0.94</td>

</tr>

<tr>

<td height="16" width="251">**http://www.third.com**</td>

<td height="16" width="182" align="center">0.98</td>

<td height="16" width="205" align="center">0.94</td>

<td height="16" width="205" align="center">0.92</td>

<td height="16" width="205" align="center">0.96</td>

<td height="16" width="205" align="center">0.88</td>

</tr>

<tr>

<td height="16" width="251">http://www.fourth.com</td>

<td height="16" width="182" align="center">0.97</td>

<td height="16" width="205" align="center">0</td>

<td height="16" width="205" align="center">0</td>

<td height="16" width="205" align="center">0.94</td>

<td height="16" width="205" align="center">0</td>

</tr>

<tr>

<td height="16" width="251">**http://www.fifth.com**</td>

<td height="16" width="182" align="center">0.96</td>

<td height="16" width="205" align="center">0.96</td>

<td height="16" width="205" align="center">0.92</td>

<td height="16" width="205" align="center">0.92</td>

<td height="16" width="205" align="center">0.92</td>

</tr>

<tr>

<td height="16" width="251">**http://www.sixth.com**</td>

<td height="16" width="182" align="center">0.95</td>

<td height="16" width="205" align="center">0.95</td>

<td height="16" width="205" align="center">0.90</td>

<td height="16" width="205" align="center">0.90</td>

<td height="16" width="205" align="center">0.90</td>

</tr>

<tr>

<td height="16" width="251">http://www.seventh.com</td>

<td height="16" width="182" align="center">0.94</td>

<td height="16" width="205" align="center">0</td>

<td height="16" width="205" align="center">0</td>

<td height="16" width="205" align="center">0.88</td>

<td height="16" width="205" align="center">0</td>

</tr>

<tr>

<td height="16" width="251">http://www.eighth.com</td>

<td height="16" width="182" align="center">0.93</td>

<td height="16" width="205" align="center">0</td>

<td height="16" width="205" align="center">0</td>

<td height="16" width="205" align="center">0.86</td>

<td height="16" width="205" align="center">0</td>

</tr>

<tr>

<td height="16" width="251">http://www.two.com</td>

<td height="16" width="182" align="center">0</td>

<td height="16" width="205" align="center">0.99</td>

<td height="16" width="205" align="center">0</td>

<td height="16" width="205" align="center">0</td>

<td height="16" width="205" align="center">0.98</td>

</tr>

<tr>

<td height="16" width="251">http://three.com</td>

<td height="16" width="182" align="center">0</td>

<td height="16" width="205" align="center">0.98</td>

<td height="16" width="205" align="center">0</td>

<td height="16" width="205" align="center">0</td>

<td height="16" width="205" align="center">0.96</td>

</tr>

<tr>

<td height="16" width="251">http://www.eight.com</td>

<td height="16" width="182" align="center">0</td>

<td height="16" width="205" align="center">0.93</td>

<td height="16" width="205" align="center">0</td>

<td height="16" width="205" align="center">0</td>

<td height="16" width="205" align="center">0.86</td>

</tr>

<tr>

<td height="16" width="251" colspan="3" align="right">Total   </td>

<td height="16" width="205" align="center">4.7</td>

<td height="16" width="205" align="center">7.44</td>

<td height="16" width="205" align="center">7.44</td>

</tr>

</tbody>

</table>

The result is obtained by dividing 4.70 within a value of 7.44 which gives a value of 0.63\. This means that the systems A and B coincide in 63% for this search.

### Our original results.

Applying this method, the obtained results of our original experiment are shown in Table 4.

<table width="95%" border="0" cellspacing="2" cellpadding="3" align="center" style="border-right: #99f5fb solid; border-top: #99f5fb solid; font-size: smaller; border-left: #99f5fb solid; border-bottom: #99f5fb solid; font-style: normal; font-family: verdana, geneva, arial, helvetica, sans-serif; background-color: #fdffdd"><caption align="bottom">  
**Table 4: Average similarities obtained in our experiment of 2002**</caption>

<tbody>

<tr>

<th>Pos</th>

<th>AW-GO</th>

<th>AW-MS</th>

<th>AW-TE</th>

<th>AW-WI</th>

<th>AV-AW</th>

<th>AV-GO</th>

<th>AV-MS</th>

<th>AV-TE</th>

<th>AV-WI</th>

<th>GO-MS</th>

<th>GO-TE</th>

<th>GO-WI</th>

<th>MS-TE</th>

<th>MS-WI</th>

<th>TE-WI</th>

</tr>

<tr>

<td>1-10</td>

<td align="center">0.21</td>

<td align="center">0.10</td>

<td align="center">0.12</td>

<td align="center">0.16</td>

<td align="center">0.13</td>

<td align="center">0.10</td>

<td align="center">0.05</td>

<td align="center">0.05</td>

<td align="center">0.12</td>

<td align="center">0.15</td>

<td align="center">0.17</td>

<td align="center">0.15</td>

<td align="center">0.3</td>

<td align="center">0.13</td>

<td align="center">0.15</td>

</tr>

<tr>

<td>11-20</td>

<td align="center">0.22</td>

<td align="center">0.10</td>

<td align="center">0.14</td>

<td align="center">0.16</td>

<td align="center">0.14</td>

<td align="center">0.12</td>

<td align="center">0.06</td>

<td align="center">0.06</td>

<td align="center">0.11</td>

<td align="center">0.17</td>

<td align="center">0.17</td>

<td align="center">0.18</td>

<td align="center">0.3</td>

<td align="center">0.15</td>

<td align="center">0.16</td>

</tr>

<tr>

<td>21-30</td>

<td align="center">0.23</td>

<td align="center">0.12</td>

<td align="center">0.15</td>

<td align="center">0.17</td>

<td align="center">0.14</td>

<td align="center">0.13</td>

<td align="center">0.07</td>

<td align="center">0.07</td>

<td align="center">0.12</td>

<td align="center">0.19</td>

<td align="center">0.20</td>

<td align="center">0.20</td>

<td align="center">0.3</td>

<td align="center">0.17</td>

<td align="center">0.16</td>

</tr>

<tr>

<td style="font-weight: bold;" colspan="16">Pos: set of analysed documents. AW: All the Web. GO: Google. MS: Microsoft Network. TE: Terra Networks. WI: Wisenut. AV: Altavista.</td>

</tr>

</tbody>

</table>

The greatest similarities, of about 30%, were obtained by two second level (in terms of number of documents indexed and proportion of Web searchers) Web retrieval systems: Terra and MSN. At this time, these systems shared the same search technology (_Inktomi_), and have a high proportion of indexed documents in common, thus this high level of similarity in comparison to the rest. The average value of the obtained similarity for the first ten and twenty documents was 0.15, and 0.16 for the first thirty documents. These values confirmed the general idea of a coincidence level of 15%.

## What has happened in the World Wide Web in recent years?

So many changes have happened in the Web in the last five years that many people, such as [O'Reilly (2005)](#OReilly), say that we are in the age of _Web 2.0_. In the field of Web retrieval systems, many developments have occurred also which we can summarise as follows:

1.  The overlap of the search engines has been poorly evaluated. The data from the Search Engine Showdown blog ([Nottes 2005](#Notess)), mentioned above, are not updated and we have only the data from Jansen and Spink ([2006](#Jansen2006)). The main analysts, such as [Nielsen/Netratings](#Nielsen), [Comscore](#com) or [searcheenginewatch.com](#searchenginewatch), offer a different kind of information. It is difficult to locate updated data about the similarity of the response of Web retrieval systems.
2.  An important set of new developments has occurred in Web retrieval systems. Through mergers and takeovers, Yahoo! has integrated the Altavista and All the Web technology and it became a search engine in February 2004\. Microsoft has replaced MSN by the portal live.com. These two systems, together with Google, dispute the size of their collection of indexed documents, which already surpasses twenty billion documents.
3.  The users basically use three Web retrieval systems: Google (58%), Yahoo! (18%), live.com (12%) and exceptionally American Online (4.5%) and Ask (3%). The data vary slightly from one source of information to the other (Nielsen/Netratings ([2007](#Nielsen)) and Comscore ([2008](#com)), and it will vary more depending on the part of the planet under analysis (for example, in Europe, Google reaches much higher percentages, around 75% of the searches). The most important fact is that these five systems concentrate 90% of the daily searches of the Web. The degree of importance of the rest is residual.

Bearing this information in mind, we can extrapolate the obtained results in 2002 by allocating the results of MSN to live.com, and the best values of similarity reached by All the Web or Altavista with each engine to Yahoo!, which is the system which, to a degree, has replaced them. Finally, the engines that people do not use will be removed because they represent only ten percent of searches carried out routinely by Web users. As a result, we have the adapted Table 5.

<table width="80%" border="1" cellspacing="0" cellpadding="3" align="center" style="border-right: #99f5fb solid; border-top: #99f5fb solid; font-size: smaller; border-left: #99f5fb solid; border-bottom: #99f5fb solid; font-style: normal; font-family: verdana, geneva, arial, helvetica, sans-serif; background-color: #fdffdd"><caption align="bottom">  
**Table 5: Average similarities obtained in our experiment of 2002**</caption>

<tbody>

<tr>

<th>Pos/Sim</th>

<th>Yahoo! - Google</th>

<th>Yahoo! - live.com</th>

<th>Google - live.com</th>

</tr>

<tr>

<td>1-10</td>

<td align="center">0.21</td>

<td align="center">0.10</td>

<td align="center">0.15</td>

</tr>

<tr>

<td>11-20</td>

<td align="center">0.22</td>

<td align="center">0.10</td>

<td align="center">0.17</td>

</tr>

<tr>

<td>21-30</td>

<td align="center">0.23</td>

<td align="center">0.12</td>

<td align="center">0.19</td>

</tr>

<tr>

<td height="32" width="3234" align="center" colspan="4">**Pos**: set of analysed documents. **Sim**: similarity</td>

</tr>

</tbody>

</table>

## September 2007 (our second experiment).

Since it is necessary to have updated data and it is not possible to continue doing this type of analysis manually, we decided to develop a meta-searcher, which could perform the search equations of the systems that are the objective of our study and, also, which could automatically determine the similarity of the obtained results. Consequently, we simplify this kind of experiment and are able to update the results.

## The implementation of the meta-searcher.

Our development is based on taking the Application Programming Interfaces (API), which each search engine provides and to integrate them within one system. Through the analysis of each of these modules, we confirm that on the way towards supremacy in the market for information retrieval on the Web, the main retrieval systems establish their own rules. Some, such as Google, seriously restrict the number of results obtained (until the beginning of December 2007 it offered eight documents, but now it offers 32 results), or they force the use of proprietary programming languages, as in the case of live.com. Currently, Yahoo! is the search engine which enables the least restricted use of its indexes. As explained previously, the new Google API restricted the number of obtained results for each consultation to eight. This was a constraint in the first phase of our study, carried out in September 2007\. It was only possible to take eight samples of each engine for each query. Nevertheless, we do not think that this factor devalues the results obtained at the end of the study since, in any case, we would have achieved a comparison of almost all of the first page of the results given by each engine. The next step in the process requires the implementation of the necessary codes in order to interrogate each engine and to retrieve the result sets given by each, in order to create a database of samples, which will be studied and analysed.

In view of the diversity of the APIs given by each system, it is necessary, as far as possible, to establish a programming criterion in which to place the core of the meta-searcher and, from this, to lay out the rest of the parts of this tool. The end result will be a tool in which the code is partitioned depending on its functionality. In short, we have the following:

*   Navigation core based in the PHP and Javascript programming languages, and in the HTML code.
*   Search engine. We differentiate the fragments for each search engine. Google: carries out the communication through JavaScript and using AJAX technology. Yahoo!: uses communication through REST queries using PHP code. live.com: has a Web Service which can be accessed through a SOAP client written in PHP.
*   Database interface. It is written in PHP, and it is responsible for the communication with the MySQL database.

<div align="center">![Interface of our implemented  meta-searcher](p382fig1.gif)</div>

<div align="center">  
**Figure 1: The interface of our meta-searcher operating with Google**</div>

The database of our meta-searcher allows the results of each search to be stored. It compiles the URL, title, description, ranking, and query-engine relation of each result. It also has a table for storing the statistics of each query.

### The repetition of the experiment.

In order to test whether the current situation differs from 2002, the experiment was repeated by entering in the meta-searcher the same queries used at that time:

<table width="90%" border="1" cellspacing="0" cellpadding="3" align="center" style="border-right: #99f5fb solid; border-top: #99f5fb solid; font-size: smaller; border-left: #99f5fb solid; border-bottom: #99f5fb solid; font-style: normal; font-family: verdana, geneva, arial, helvetica, sans-serif; background-color: #fdffdd"><caption align="bottom">  
**Table 6: Set of queries used in the experiments**</caption>

<tbody>

<tr>

<td>Turismo rural en la Sierra del Segura</td>

<td>Alquiler de apartamentos en Málaga</td>

</tr>

<tr>

<td>Historia del Camino de Santiago</td>

<td>Curso a distancia de Programación en PHP</td>

</tr>

<tr>

<td>Principio de incertidumbre de Heisenberg</td>

<td>Diseño de sistemas multimedia para el aprendizaje</td>

</tr>

<tr>

<td>Academias de idiomas en Valencia</td>

<td>Discurso del Método de Descartes</td>

</tr>

<tr>

<td>Diseño accesible a páginas Web</td>

<td>Recetas de cocina y dieta mediterránea</td>

</tr>

<tr>

<td>Teoría de la Evolución de Darwin</td>

<td>Semana Santa en Murcia</td>

</tr>

<tr>

<td>Bibliografía de Miguel de Unamuno</td>

<td>Estrategias de Representación del Conocimiento</td>

</tr>

<tr>

<td>Galerías de Arte en Murcia</td>

<td>Empresas de fabricación de calzado en Alicante</td>

</tr>

<tr>

<td>Influencia de la televisión en los niños</td>

<td>Apuntes de Sistemas Digitales</td>

</tr>

<tr>

<td>Apuntes de Estadística Descriptiva</td>

<td>Modelos pedagógicos para la educación a distancia</td>

</tr>

<tr>

<td>Principio de Conservación de la Energía</td>

<td>Librerías de antiguo en España</td>

</tr>

<tr>

<td>Apuntes de Historia del Arte Barroco</td>

<td>Temario de Oposiciones de Matemáticas en Secundaria</td>

</tr>

<tr>

<td>Recopilación de Legislación en Derecho Civil</td>

<td>Historia de la ciudad de Ceuta</td>

</tr>

<tr>

<td>Compra-Venta de automóviles de segunda mano en Madrid</td>

<td>Evaluación de la calidad de la enseñanza universitaria</td>

</tr>

<tr>

<td>Literatura Española en el Siglo de Oro</td>

<td>Plan de Estudios de Licenciado en Comunicación Audiovisual</td>

</tr>

</tbody>

</table>

The similarity results of the first eight documents for each system in this second experiment (September 2007) are shown in Table 7.

<table width="80%" border="1" cellspacing="0" cellpadding="3" align="center" style="border-right: #99f5fb solid; border-top: #99f5fb solid; font-size: smaller; border-left: #99f5fb solid; border-bottom: #99f5fb solid; font-style: normal; font-family: verdana, geneva, arial, helvetica, sans-serif; background-color: #fdffdd"><caption align="bottom">  
**Table 7: Average similarities obtained in our second experiment in 2007**</caption>

<tbody>

<tr>

<th>Pos/Sim</th>

<th>Yahoo! - Google</th>

<th>Yahoo! - live.com</th>

<th>Google - live.com</th>

</tr>

<tr>

<td>1-8</td>

<td align="center">0.17</td>

<td align="center">0.15</td>

<td align="center">0.11</td>

</tr>

<tr>

<th colspan="4">Pos: set of analysed documents. Sim: similarity</th>

</tr>

</tbody>

</table>

Assuming that there may be a slight difference between these results, if we would have been able to determine the similarity of the ten first documents instead of the first eight documents, we can compare these results with those obtained in 2002 and we can see that the average similarity values in the response decrease very little (from 15% to 14%). This means that the similarity between the first results of each system is stable. This is surprising, since the size of the indexes has increased considerably and consequently there are many more documents on any subject, so the coincidence is much more complicated (or so we thought). Even if a dozen of documents is a very small sample in order to evaluate the similarity of the reply, we cannot ignore the large number of Web users who only read the first page of the system output. Within this context, coincidence value gains much more significance and importance.

## The present.

We have previously commented that at the end of 2007, the Google API announced that it had enlarged the maximum number of documents obtained with each query from eight to thirty-two. This obviously helped our experiment and we introduced a set of changes in the meta-searcher. This was not as easy as we expected, because Google presented the results in the form of four pages of eight results. This made the analysis of the response more difficult, since the other APIs give the results in an unique list. Nevertheless, we managed to make the necessary changes. Currently, the meta-searcher can determine the similarity values up to the first thirty-two documents obtained by the three systems under analysis. In this case, the searches were made in two languages, English and Spanish in order to verify whether the similarity is influenced by the language. The following results were obtained by repeating the experiment with the new limit:

<table width="80%" border="1" cellspacing="0" cellpadding="3" align="center" style="border-right: #99f5fb solid; border-top: #99f5fb solid; font-size: smaller; border-left: #99f5fb solid; border-bottom: #99f5fb solid; font-style: normal; font-family: verdana, geneva, arial, helvetica, sans-serif; background-color: #fdffdd"><caption align="bottom">  
**Table 8: Average similarities obtained with the limit of thirty-two documents per reply**</caption>

<tbody>

<tr>

<th>Pos/Sim</th>

<th>Yahoo! - Google</th>

<th>Yahoo! - live.com</th>

<th>Google - live.com</th>

</tr>

<tr>

<td>1-32 (Spanish)</td>

<td align="center">0.19</td>

<td align="center">0.21</td>

<td align="center">0.14</td>

</tr>

<tr>

<td>1-32 (English)</td>

<td align="center">0.15</td>

<td align="center">0.11</td>

<td align="center">0.10</td>

</tr>

<tr>

<th colspan="4">Pos: set of analysed documents. Sim: similarity</th>

</tr>

</tbody>

</table>

In comparison to the results obtained in 2002, there are variations in the similarity engine by engine but not in the average value, which is 0.18 in both cases. This value is slightly higher than when only the first eight documents of the response are analysed. The current experiments seem to indicate that Google and live.com offer the most different responses, although in fact the differences are still small. The behaviour of the questions made in English is very similar although the average values are lower (0.12). We think that it is logical because the space in which to locate documents is broader (in the Web context there are more documents written in English than in Spanish).

### Complementing the experiment with 'short queries'.

One of the more repeated experiments by researchers on information searching is to determine the average length of the searches. Spink and Jansen ([2004](#Spink2004)) give more information about it, noting that the average is small (between one and two words for a search). Our previous searches intended to simulate the behaviour of students interested in some subject ('Heisenberg Principle', 'Einstein Theory of Relativity', 'History of Ceuta', etc.) or the behaviour of a simple person who wishes to pass wonderful holidays in Málaga or to buy a second-hand car. The truth is that as our average search length exceeds the normal ratio, it does not reflect the general user's behaviour.

It would be interesting to verify if the average values of similarity vary with shorter searches. In order to replicate the behaviour of current Web users, we extracted the terms for the new queries from the _2006 Top 10 US Search Ranking_ [(Kopytoff 2007)](#Kopytoff), choosing the ten most commonly used terms in each of the three Web retrieval systems, forming a new group of thirty queries closer to the Web context and their users.

<table width="60%" border="1" cellspacing="0" cellpadding="3" align="center" style="border-right: #99f5fb solid; border-top: #99f5fb solid; font-size: smaller; border-left: #99f5fb solid; border-bottom: #99f5fb solid; font-style: normal; font-family: verdana, geneva, arial, helvetica, sans-serif; background-color: #fdffdd"><caption align="bottom">  
**Table 9: Terms most searched in USA during the year 2006.**</caption>

<tbody>

<tr>

<th>Google</th>

<th>Yahoo!</th>

<th>live.com</th>

</tr>

<tr>

<td>Bebo</td>

<td>Britney Spears</td>

<td>MySpace</td>

</tr>

<tr>

<td>MySpace</td>

<td>WWE</td>

<td>Dictionary</td>

</tr>

<tr>

<td>World Cup</td>

<td>Shakira</td>

<td>Games</td>

</tr>

<tr>

<td>Metacafe</td>

<td>Jessica Simpson</td>

<td>Cars</td>

</tr>

<tr>

<td>Radioblog</td>

<td>Paris Hilton</td>

<td>Food</td>

</tr>

<tr>

<td>Wikipedia</td>

<td>American Idol</td>

<td>Song lirycs</td>

</tr>

<tr>

<td>Video</td>

<td>Beyonce Knowles</td>

<td>Poems</td>

</tr>

<tr>

<td>Rebelde</td>

<td>Chris Brown</td>

<td>New York</td>

</tr>

<tr>

<td>Mininota</td>

<td>Pamela Anderson</td>

<td>Baby names</td>

</tr>

<tr>

<td>Wiki</td>

<td>Lindsay Lohan</td>

<td>Music</td>

</tr>

</tbody>

</table>

In the same direction, we only calculated the similarity of the ten first results of each Web retrieval systems. As we can easily see in the next table, the changes in obtained average values of similarity in this new experiment with respect to the previous ones are barely significant (0.14 against 0.18), although, like novelty, in some particular cases they appear null values of similarity (the query 'American Idol' does not have any common document in the Yahoo! and Windows Live responses, for example), this did not occur frequently in the previous searches, which used longer search formulations.

<table width="70%" border="1" cellspacing="0" cellpadding="3" align="center" style="border-right: #99f5fb solid; border-top: #99f5fb solid; font-size: smaller; border-left: #99f5fb solid; border-bottom: #99f5fb solid; font-style: normal; font-family: verdana, geneva, arial, helvetica, sans-serif; background-color: #fdffdd"><caption align="bottom">  
**Table 10: Average similarities obtained with 'sort queries'**</caption>

<tbody>

<tr>

<th>Query</th>

<th>Yahoo! - Google</th>

<th>Yahoo! - live.com</th>

<th>Google - live.com</th>

</tr>

<tr>

<td>American Idol</td>

<td align="center">0.2590</td>

<td align="center">0.0000</td>

<td align="center">0.2604</td>

</tr>

<tr>

<td>Baby names</td>

<td align="center">0.0000</td>

<td align="center">0.0000</td>

<td align="center">**0.5060**</td>

</tr>

<tr>

<td>Bebo</td>

<td align="center">0.1262</td>

<td align="center">0.3800</td>

<td align="center">0.1328</td>

</tr>

<tr>

<td>Beyonce Knowles</td>

<td align="center">0.2512</td>

<td align="center">0.1315</td>

<td align="center">0.1288</td>

</tr>

<tr>

<td>Britney Spears</td>

<td align="center">0.1315</td>

<td align="center">0.1235</td>

<td align="center">0.3773</td>

</tr>

<tr>

<td>Cars</td>

<td align="center">0.2383</td>

<td align="center">0.0000</td>

<td align="center">0.0000</td>

</tr>

<tr>

<td>Chris Brown</td>

<td align="center">0.0000</td>

<td align="center">0.0000</td>

<td align="center">0.0000</td>

</tr>

<tr>

<td>David Beckham</td>

<td align="center">0.2643</td>

<td align="center">0.3827</td>

<td align="center">0.1328</td>

</tr>

<tr>

<td>Dictionary</td>

<td align="center">0.1249</td>

<td align="center">0.2563</td>

<td align="center">0.1301</td>

</tr>

<tr>

<td>Food</td>

<td align="center">0.1301</td>

<td align="center">0.1173</td>

<td align="center">0.0000</td>

</tr>

<tr>

<td>Games</td>

<td align="center">0.2446</td>

<td align="center">0.0000</td>

<td align="center">0.0000</td>

</tr>

<tr>

<td>Jessica Simpson</td>

<td align="center">0.1315</td>

<td align="center">0.0000</td>

<td align="center">0.2578</td>

</tr>

<tr>

<td>Lindsay Lohan</td>

<td align="center">0.2576</td>

<td align="center">0.1315</td>

<td align="center">0.1315</td>

</tr>

<tr>

<td>Metacafe</td>

<td align="center">0.0000</td>

<td align="center">0.0000</td>

<td align="center">0.2604</td>

</tr>

<tr>

<td>Mininova</td>

<td align="center">0.0000</td>

<td align="center">0.0000</td>

<td align="center">0.1342</td>

</tr>

<tr>

<td>Music</td>

<td align="center">0.0000</td>

<td align="center">0.2434</td>

<td align="center">0.0000</td>

</tr>

<tr>

<td>MySpace</td>

<td align="center">0.1315</td>

<td align="center">0.1315</td>

<td align="center">0.1288</td>

</tr>

<tr>

<td>New York</td>

<td align="center">0.0000</td>

<td align="center">0.0000</td>

<td align="center">0.0000</td>

</tr>

<tr>

<td>Pamela Anderson</td>

<td align="center">0.2525</td>

<td align="center">0.0000</td>

<td align="center">0.1315</td>

</tr>

<tr>

<td>Paris Hilton</td>

<td align="center">0.1342</td>

<td align="center">0.2590</td>

<td align="center">0.2564</td>

</tr>

<tr>

<td>Poems</td>

<td align="center">0.0000</td>

<td align="center">0.0000</td>

<td align="center">0.1211</td>

</tr>

<tr>

<td>Radioblog</td>

<td align="center">0.2510</td>

<td align="center">0.3786</td>

<td align="center">0.0000</td>

</tr>

<tr>

<td>Rebelde</td>

<td align="center">0.3787</td>

<td align="center">0.0000</td>

<td align="center">0.0000</td>

</tr>

<tr>

<td>Shakira</td>

<td align="center">0.3699</td>

<td align="center">0.1211</td>

<td align="center">0.3827</td>

</tr>

<tr>

<td>Song lyrics</td>

<td align="center">0.0000</td>

<td align="center">0.0000</td>

<td align="center">0.2526</td>

</tr>

<tr>

<td>Video</td>

<td align="center">0.0000</td>

<td align="center">0.0000</td>

<td align="center">0.0000</td>

</tr>

<tr>

<td>Wiki</td>

<td align="center">**0.3892**</td>

<td align="center">0.1315</td>

<td align="center">0.2500</td>

</tr>

<tr>

<td>Wikipedia</td>

<td align="center">0.2656</td>

<td align="center">**0.3945**</td>

<td align="center">0.3906</td>

</tr>

<tr>

<td>World Cup</td>

<td align="center">0.1274</td>

<td align="center">0.1342</td>

<td align="center">0.1185</td>

</tr>

<tr>

<td>WWE</td>

<td align="center">0.0000</td>

<td align="center">0.1302</td>

<td align="center">0.2656</td>

</tr>

<tr style="font-weight: bold;">

<td>Averages</td>

<td align="center">0.1486</td>

<td align="center">0.1149</td>

<td align="center">0.1583</td>

</tr>

</tbody>

</table>

## The immediate future

We have conceived two lines of work for the immediate future. The first, more focused on measuring performance effectiveness, intends to overcome the limit of thirty-two documents in each analysed query, reaching a total of 100 documents. The second line is closer to the user's behaviour: we shall try to incorporate a set of parameters related to other emerging patterns in Web search, such as Web query reformulations, the distribution of search terms and the use of relevance feedback. If we are able to incorporate some of these aspects in our work, we will be able to show the real Web context. We can also repeat these experiments using only one language, instead of both Spanish and English as reported here: the results of the two experiments on search query length could be of interest when the two languages are compared.

Another objective is to extend the number of Web retrieval systems studied. Initially we considered incorporating the API of Ask ([Antezeta 2007](#Antezeta)) or of any of its associated systems, although, after a subsequent study, we have opted for a comprehensive redesign of our meta-searcher because we only can use a small number of available APIs and they are very limited by their owners. So, we are working in the initial implementation of a new version of our meta-searcher, more complete and powerful, and more independent of the Web retrieval systems's design.

This extension of the reach of our meta-searcher has another objective: to determine the distance between the reply of an Web retrieval systems to an individual question and the ideal reply for this information need. This reply would be based in the semantics of the reply given by each of the Web retrieval systems and by using the techniques of decomposition of singular values with a similar approach to the automatic allocation of the best article reviewers sent to a scientific magazine proposed by Dumais and Nielsen ([1992](#Dumais)). We would need to make use of a wider and stronger information basis, so that we may increase the number of analysed documents. Increasing the number of sources will also be essential.

## Conclusions

We think it is possible to approach the performance evaluation of the Web retrieval systems from the perspective of information searching, incorporating several aspects of Web users' trends and habits into the design of an evaluation methodology. The indexes of the Web retrieval systems are very different. Each system seems to have indexed different spaces in the Web, with very little overlap, mainly in the first documents of the replies (which is unlikely to lead to user satisfaction). This overlap is is slightly lower with documents written in English with those written in Spanish. Certainly, the different criteria for implementing the ranking algorithms contribute to this. Our study confirms that there is little similarity between the responses of these systems. From the analysed Web retrieval systems, Google and live.com have least overlap and for an exhaustive information search, it is necessary to employ several Web retrieval systems at the same time.

The number of search terms does not introduce significant differences in the similarity of the reply, it is not a decisive factor for search engines. It may be that comparing sets of thirty documents is too small, given the magnitude of the indexes of the Web retrieval systems. These conclusions need to be confirmed by extending the number of documents of the analysed sample. Having more information and a consistent basis for calculation (for the number of documents obtained and the analysed sources of information) can help us to create an _ideal response_ for a given information request. If we involve in the calculation factors that are close to the users, we are calculating the ideal response to a user. Undoubtedly, this would be a significant achievement.

## Acknowledgements

This work and our stay in Vilnius would not have been possible without the invaluable help of Tom Wilson and Elena Maceviciute. Our sincere acknowledgement to them.

## References

*   <a id="Antezeta" name="Antezeta"></a>Antezeta Internet Marketing. (2007). _[Decrypting Ask's Web search API](http://www.webcitation.org/5cy0sz7R2)_. Milan: Antezeta Internet Marketing. Retrieved 9 December, 2007 from http://www.antezeta.com/ask/decrypting-ask-web-search-api.html (Archived by WebCite® at http://www.webcitation.org/5cy0sz7R2)
*   <a id="berners" name="berners"></a>Berners-Lee, T., Hendler, J. & Lassila, O. (2001). [The semantic Web.](http://www.webcitation.org/5cy10NNFR) _Scientific American_, **284**(5), 34-56\. Retrieved 9 December, 2008 from http://www.sciam.com/article.cfm?id=the-semantic-web (Archived by WebCite® at http://www.webcitation.org/5cy10NNFR)
*   <a id="searchenginewatch" name="searchenginewatch"></a>Burns, E. (2007) _[U.S. search engine rankings, September 2007](http://www.webcitation.org/5cy5AWkOw)_. New York, NY: Incisive Media. Retrieved 9 December, 2008 from http://searchenginewatch.com/showPage.html?page=3627654 (Archived by WebCite® at http://www.webcitation.org/5cy5AWkOw)
*   <a id="com" name="com"></a>comScore (2008) _[comScore data center: measuring the digital world](http://www.webcitation.org/5cy1C60y1)_. Reston, VA: comScore. Retrieved 9 December, 2008 from http://www.comscore.com/press/data.asp (Archived by WebCite® at http://www.webcitation.org/5cy1C60y1)
*   <a id="Chu" name="Chu"></a>Chu, H. & Rosenthal, M. (1996). [Search engines for the World Wide Web: a comparative study and evaluation methodology.](http://www.webcitation.org/5cy1i3cuD) In _Global Complexity: Information, Chaos and Control: ASIS 1996 Annual Meeting - October 19 - 24 1996\. Electronic Proceedings._ Silver Spring, MD: American Society for Information Science. Retrieved 9 December, 2008, from http://www.asis.org/annual-96/ElectronicProceedings/chu.html (Archived by WebCite® at http://www.webcitation.org/5cy1i3cuD)
*   <a id="Dumais" name="Dumais"></a>Dumais, S. & Nielsen, J. (1992). Automating the assignment of submitted manuscripts to reviewers. In Nicholas Belkin, Peter Ingwersen & Annelise Mark Pejtersen, (Eds.) _Proceedings of the 15th annual international ACM SIGIR conference on Research and development in information retrieval_. (pp. 233-244). New York, NY: ACM Press.
*   <a id="Hersh" name="Hersh"></a>Hersh, W.R. _et al._ (1995). Towards new measures of Information Retrieval Evaluation. In Edward A. Fox, Peter Ingwersen & Raya Fidel, (Eds.) _Proceedings of the 18th annual international ACM SIGIR conference on Research and development in information retrieval 1995, Seattle, Washington, United States_. (pp. 164-170). New York, NY: ACM Press.
*   <a id="Gordon" name="Gordon"></a>Gordon, M. & Pathak, P. (1999). Finding information on the World Wide Web: the retrieval effectiveness of search engines. _Information Processing and Management_, **35**(2), 141-180.
*   <a id="Jansen1998" name="Jansen1998"></a>Jansen, B.J. Spink, A. Bateman, J. & Saracevic, T. (1998). Real life information retrieval: a study of user queries on the Web. _SIGIR Forum_ **32**(1), 5-17.
*   <a id="Jansen2006" name="Jansen2006"></a>Jansen, B. & Spink, A. (2006). How are we searching the World Wide Web? A comparison of nine search engine transaction logs. _Information Processing and Management_, **42**(1), 248-263.
*   <a id="Johnson" name="Johnson"></a>Johnson, F.C., Griffiths, J.R. & Hartley, R.J. (2001). _[DEVISE: a framework for the evaluation of Internet search engines.](http://www.webcitation.org/5cy2Seqv7)_ Manchester, U.K.: Manchester Metropolitan University, Centre for Research in Library and Information Management. (Library and information commission research report 100) Retrieved April 20, 2008 from http://bit.ly/iD8X (Archived by WebCite® at http://www.webcitation.org/5cy2Seqv7)
*   <a id="Kopytoff" name="Kopytoff"></a>Kopytoff, V. (2006, December 25). [Year's top search terms.](http://www.webcitation.org/5cy2bvkQZ) _San Francisco Chronicle_, Retrieved 9 December, 2008 from http://bit.ly/rjo9 (Archived by WebCite® at http://www.webcitation.org/5cy2bvkQZ)
*   <a id="Landoni" name="Landoni"></a>Landoni, M. & Bell, S. (2000). Information retrieval techniques for evaluating search engines: a critical overview. _Aslib Proceedings_, **52**(3), 124-129.
*   <a id="Leighton" name="Leighton"></a>Leighton, H.V. & Srivastava, J. (1999). First 20 precision among World Wide Web search services (search engines). _Journal of the American Society for Information Science_ **50**(10), 870-881\.
*   <a id="Ljosland2000a" name="Ljosland2000a"></a>Ljosland, M. (2000a). _[Evaluation of Web search engines and the search for better ranking algorithms](http://www.webcitation.org/5cy36Ff3n)_. Paper presented at the SIGIR99 Workshop on Evaluation of Web Retrieval, Aug 19, 1999\. Retrieved 9 December, 2008, from http://www.aitel.hist.no/~mildrid/dring/paper/SIGIR.html (Archived by WebCite® at http://www.webcitation.org/5cy36Ff3n)
*   <a id="Ljosland2000b" name="Ljosland2000b"></a>Ljosland, M. (2000b). _[Evaluation of twenty Web search engines on ten rare words ranking algorithms](http://www.webcitation.org/5cy3Ehu14)_. Retrieved 9 December, 2008, from http://www.aitel.hist.no/~mildrid/dring/paper/Comp20.doc (Archived by WebCite® at http://www.webcitation.org/5cy3Ehu14)
*   <a id="Marchionini" name="Marchionini"></a>Marchionini, G. (2004). [From information retrieval to information interaction.](http://www.webcitation.org/5cy3fQ5xA) In Sharon McDonald & John Tait, (Eds.) _Advances in information retrieval_. (pp. 1-11). New York, NY: Springer-Verlag. Retrieved 9 December, 2008 from http://ils.unc.edu/~march/ECIR.pdf . (Archived by WebCite® at http://www.webcitation.org/5cy3fQ5xA)
*   <a id="Martinez2002" name="Martinez2002"></a>Martínez Méndez, F.J. (2002). _[Propuesta y desarrollo de un modelo para la evaluación de la recuperación de información en Internet](http://www.webcitation.org/5cy3y6WDb)_. Unpublished doctoral dissertation, Universidad de Murcia, Spain. Retrieved 9 December, 2008 from http://www.cervantesvirtual.com/FichaObra.html?Ref=10010&ext=pdf&portal=0 (Archived by WebCite® at http://www.webcitation.org/5cy3y6WDb)
*   <a id="Martinez2003" name="Martinez2003"></a>Martínez Méndez, F. J. & Rodríguez Muñoz, J.V. (2003). [Síntesis y crítica de las evaluaciones de la efectividad de los motores de búsqueda en la Web.](http://www.webcitation.org/5cy4BQPKY) _Information Research_, **8**(2), paper 148\. Retrieved Jan 18, 2008, from http://InformationR.net/ir/8-2/paper148.html (Archived by WebCite® at http://www.webcitation.org/5cy4BQPKY)
*   <a id="Nielsen" name="Nielsen"></a>Nielsen/NetRatings. (2007). _[Nielsen online reports topline U.S. data for November 2007](http://www.webcitation.org/5cy4OCJKd)_. Retrieved Jan 7, 2008, from http://www.nielsen-online.com/pr/pr_071210.pdf (Archived by WebCite® at http://www.webcitation.org/5cy4OCJKd)
*   <a id="Notess" name="Notess"></a>Notess, G.R. (2005) _[Search engine statistics](http://www.webcitation.org/5cy4UWxLZ)_. Retrieved 9 December, 2008 from http://www.searchengineshowdown.com/statistics/ (Archived by WebCite® at http://www.webcitation.org/5cy4UWxLZ)
*   <a id="Oppenheim" name="Oppenheim"></a>Oppenheim, C., Morris, A., McKnight, C. & Lowley, S. (2000). The evaluation of Web search engines. _Journal of Documentation_, **56**(2), 190-211.
*   <a id="OReilly" name="OReilly"></a>O'Reilly (2005) _[What is Web 2.0? Design patterns and business models for the next generation of software](http://www.webcitation.org/5cy4j7tYQ)_. Retrieved Jan 10, 2008, from http://www.oreillynet.com/pub/a/oreilly/tim/news/2005/09/30/what-is-Web-20.html (Archived by WebCite® at http://www.webcitation.org/5cy4j7tYQ)
*   <a id="Salton" name="Salton"></a>Salton, G. & Mc Gill, M.J. (1983) _Introduction to Modern Information Retrieval_. New York, NY: Mc Graw-Hill Computer Series.
*   <a id="Schlichting" name="Schlichting"></a>Schlichting, C. & Nilsen, E. (1997). _[Signal detection analysis of Web search engines](http://www.webcitation.org/5cy4sTIWL)_. Redmond, WA: Microsoft Corporation. Retrieved 9 December, 2008, from http://www.microsoft.com/usability/Webconf/schlichting/schlichting.htm (Archived by WebCite® at http://www.webcitation.org/5cy4sTIWL)
*   <a id="Spink1998" name="Spink1998"></a>Spink, A., Bateman, J. & Jansen, B.J. (1998). [Searching heterogeneous collections on the Web: behaviour of Excite users.](http://www.webcitation.org/5cy5GqqKc) _Information Research_, **4**(2). Retrieved 9 December, 2008, from http://informationr.net/ir/4-2/paper53.html (Archived by WebCite® at http://www.webcitation.org/5cy5GqqKc)
*   <a id="Spink2004" name="Spink2004"></a>Spink, A. & Jansen, B.J. (2004). [A study of Web search trends.](http://www.webcitation.org/5cy5XxXY3) _Webology_, **1**(2). Retrieved 9 December, 2008, from http://www.Webology.ir/2004/v1n2/a4.html (Archived by WebCite® at http://www.webcitation.org/5cy5XxXY3)
*   <a id="Tang" name="Tang"></a>Tang, M. & Sun, Y. (2003) [Evaluation of Web-based search engines using user-effort measures.](http://www.webcitation.org/5cy5dSGI3) _LIBRES_, **13**(2). Retrieved 9 December, 2008, from http://libres.curtin.edu.au/libres13n2/tang.htm (Archived by WebCite® at http://www.webcitation.org/5cy5dSGI3)
*   <a id="Zhang2005a" name="Zhang2005a"></a>Zhang, J. & Dimitroff, A. (2005). The impact of Webpage content characteristics on Webpage visibility in search engine results (Part I). _Information Processing and Management_ **41**(3), 661-690.
*   <a id="Zhang2005b" name="Zhang2005b"></a>Zhang, J. and Dimitroff, A. (2005). The impact of Webpage content characteristics on Webpage visibility in search engine results (Part II). _Information Processing and Management_ **41**(3), 691-715.

