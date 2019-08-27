<header>

#### vol. 20 no. 1, March, 2015

</header>

<article>

# Sources of noise in interactive information search

#### [Ning Sa](#author) and [Xiaojun Yuan](#author)  
College of Computing and Information, University at Albany, The State University of New York

#### Abstract

> During web search, users click and read documents they evaluate as useful or not useful. The results which are not useful may add noises to the implicit feedback which is the unobtrusively obtained user information ([Kelly, 2005](#Kel05)). This paper investigates the sources of the noise and the indicators of the noise. In a lab experiment, each participant performs web search on 4 pre-defined tasks. The reasons why users click and read each document and how they make judgment are asked in the interview after the search. A pilot study was conducted, and some findings were reported.

## Introduction

A typical online web search session consists of multiple query inputs which are used by the information retrieval system to evaluate the relevance of the documents on the internet. Meanwhile, the users evaluate the results returned by the system and refine their search queries. The system evaluation, which is the matching between the query and the documents, has been investigated for decades. However, not all the documents marked as relevant by the information system are useful to the users. Furthermore, the usefulness of documents is highly user dependent even if the two users have submitted the same query. As Carterette, Kanoulas, and Yilmaz ([2012](#Car12)) pointed out that '_no two users interact with a system in exactly the same way_'. Thus, user preference plays an important role in '_making the retrieval evaluation faster, cheaper, and more user centered_' ([Radlinski, Kurup, and Joachims, 2008](#Rad08)).

### Related Work

Researchers have focused on how to use implicit feedback as indicators. Implicit feedback refer to the user information that can be obtained unobtrusively ([Kelly, 2005](#Kel05)), such as click through data, mouse scroll, and reading time. This type of information is promising in reflecting the user preference because the users selectively click results after reasonable judgment ([Joachims, Granka, Pan, Hembrooke, and Gay, 2005](#Joa05)). At the same time it is _noisy_: the users click results which are useful to them as well as those which are not useful. Agichtein and Zheng ([2006](#Agi06)) observed that users tend to click on the top result even though it might not be relevant. Various methods were used in previous studies to determine the usefulness of clicking data. However, findings are controversy. Claypool and coworkers reported the reading time of a page and the amount of scrolling are good indicators of the user preference ([Claypool, Le, Wased, and Brown, 2001](#Cla01)), while Kelly _et al_. found that there isn't statistically significant correlation between reading time and usefulness ([Kelly and Belkin, 2004](#Kel04)).

It can be expected that implicit feedback could be more effective in reflecting user preferences if there is a better understanding in the nature of implicit feedback noise. The controversial findings might be because of the different origins of the noise. However, few researches in literatures explored this issue. In this study, we focus on the following two research questions (RQs):

*   RQ1\. What are the sources of the noises in the implicit feedback data?
*   RQ2\. What are the indicators of these noises?

## Method

The user data in this study will be collected from a controlled lab experiment. The experiment is composed of a sequence of search session and post-search interview session. Thirty university graduate students will participate in the experiment to perform web search on pre-defined tasks. Google is used in this experiment.

### Experimental design

To identify the influence from search topic familiarity, each participant will select two familiar tasks and two unfamiliar tasks from a list of eight search tasks. Then, the participants will perform searches on each task. All user activities, including voice, mouse clicks, web page changes, will be logged by Morae V3.1 usability software (http://www.techsmith.com/morae.html). After each search task, there will be an interview. Firstly, the participant will be asked about whether or not he/she is familiar with the finished task. Then along with the replay of the recorded screen video during search section (Figure 1), participants will be asked how useful each link they clicked is and how they draw the conclusions. The interview will also be recorded for further analysis. At the end of the experiment, the participant will receive $20 Amazon Gift Card as compensation of completing the experiment.

<figure class="centre">![Figure 1\. Screenshot of the video of the search process](isicsp11fig1.jpg)

<figcaption>Figure 1\. Screenshot of the video of the search process</figcaption>

</figure>

### Tasks and topics

Four of the eight tasks were derived from TREC 2012 Session track and the other half were created by our research team. Most of the tasks are aspectual retrieval tasks with some of them as open-ended exploratory tasks. The presentation of the tasks follows the principle of situated work task situation ([Borlund 2003](#Bor03)). An example task is as below:

> **SCENARIO**: _Your nephew is going to apply a college this year. He is interested in accounting and would like to enter a business school. Due to financial reasons, his family prefers public universities, such as SUNY schools. However they do not know much about SUNY. You offered to help them find out the best business school in SUNY_.  
> **TASK**: _find as much information as you can on ranking, reviews, faculty, alumni network, as well as the other factors based on your judgment which could help your nephew's family make the decision_.

## Results and Analysis

Content analysis will be performed on the interview data to figure out the sources of the noise, that is, the reasons why a document is determined as not useful. Then the implicit feedback data will be analyzed quantitatively to find out the indicators of the noise from different sources. We have conducted a pilot experiment with two pilots. We plan to finish the whole experiment in April and May. Here we report some preliminary findings of the pilot experiment.

First of all, it is noticeable that they spent less time on the topics they were familiar with than those they were not familiar with. They visited more webpages on familiar topics than those on unfamiliar topics within the same time period. Also, the reading time on familiar topics was shorter. One participant commented that '_all I need to do is to look at the title_' and he opened the webpage only to make sure that '_it is talking about the topic_'. Secondly, _the user's belief is a factor affecting the searching process_. The prior knowledge mentioned above can introduce some side effect. In searching for the best business school in SUNY system, holding the belief that University A is the best SUNY university, one participant spent extra time on searching the ranking of University A, which led to irrelevant webpages. The other participant also mentioned that she would click the result on top of the list because '_usually the one on the top is the most relevant one_'. This has been reported as a trust bias in Agichtein and Zheng ([2006](#Agi06)). Thirdly, _the participants followed certain searching strategies, though sometimes they might seem off-topic_. As a familiar topic, one participant used "_business school annual conference_" as one query to find the best business school in SUNY, because she had obtained useful information in her research field. The search failed to return useful results but she attributed the unsuccessfulness to unfamiliarity with business field and the limited searching time on the task.

Fourthly, _the participant's interest on the topic_ also played a role. When they were interested in the topic, they read the content of the page. When they just want to collect information, they usually looked for the keywords on the page, which would be faster. One participant also described one of his recent search activities on the flight MH370\. He started with the searching of the missing plane but when he read about the premier's claims, he searched for the current and past premiers in Malaysia. After that, he resumed the search on MH370\. It is difficult to observe this kind of process under experimental environment but this might be a typical searching process in real life. Last but not the least, the fact that the participants did not save a page doesn't mean that the page is not relevant to the topic or the search. The reason could also be that they have already saved a similar page. One participant said he could pick one from two pages if '_content is similar_'.

## Conclusion

Our pilot study generated some interesting discoveries. The reading time is shorter when the user is familiar with the topic than when they are unfamiliar with the topic. If the user is interested in the topic and actually reads the content, the reading time will be longer and the search might go to other branches. As a result, it might be problematic to use reading time as an indicator of the usefulness of the document, which is consistent with Kelly and Belkin ([2004](#Bel04)). Besides, when using explicit feedback, such as saved documents, to evaluate implicit feedback, we cannot decide if the unsaved documents are irrelevant because the user might save one document from two similar ones.

#### References

*   Agichtein, E. & Zheng, Z. (2006). Identifying "best bet" web search results by mining past user behavior. In _Proceedings of the 12th ACM SIGKDD international conference on Knowledge discovery and data mining_ (pp. 902-908). New York, NY, USA: ACM.
*   Carterette, B., Kanoulas, E. & Yilmaz, E. (2012). Incorporating variability in user behavior into systems based evaluation. _In Proceedings of the 21st ACM international conference on Information and knowledge management_ (pp.135-144). New York, NY, USA: ACM.
*   Claypool, M., Le, P., Wased, M. & Brown, D. (2001). Implicit interest indicators. In _Proceedings of the 6th international conference on Intelligent user interfaces_ (pp. 33-40). New York, NY, USA: ACM.
*   Joachims, T., Granka, L., Pan, B., Hembrooke, H. & Gay, G. (2005). Accurately interpreting clickthrough data as implicit feedback. _In Proceedings of the 28th annual international ACM SIGIR conference on Research and development in information retrieval_ (pp. 154-161). New York, NY, USA: ACM.
*   Kelly, D. (2005). Implicit Feedback: Using Behavior to Infer Relevance. In A. Spink & C. Cole (Eds.), _New Directions in Cognitive Information Retrieval_ (Vol. 19, pp. 169-186). Springer Netherlands. Retrieved from http://www.springerlink.com.ezproxy.lib.indiana.edu/content/q301n8n72900w8 m3/
*   Kelly, D. & Belkin, N. J. (2004). Display time as implicit feedback: understanding task effects. In Proceedings of the 27th annual international ACM SIGIR conference on Research and development in information retrieval (pp. 377-384). New York, NY, USA: ACM.
*   Radlinski, F., Kurup, M. & Joachims, T. (2008). How does clickthrough data reflect retrieval quality? In _Proceedings of the 17th ACM conference on Information and knowledge management_ (pp. 43-52). New York, NY, USA: ACM.

</article>