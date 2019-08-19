vol. 16 no. 4, December 2011

# Seeking information with an information visualization system: a study of cognitive styles

#### [Xiaojun Yuan](#authors)  
College of Computing and Information, University at Albany, State University of New York, 135 Western Avenue, Albany, NY 12222, USA  
[**Xiangman Zhang**](#authors)  
School of Library and Information Science,Wayne State University, Detroit, MI 48202, USA  
[Chaomei Chen](#authors)  
College of Information Science and Technology, Drexel University, 3141 Chestnut Street Philadelphia, PA 19104-2875, USA  
[Joshua M. Avery](#authors)  
College of Computing and Information, University at Albany, State University of New York, 135 Western Avenue, Albany, NY 12222, USA

#### Abstract

> **Introduction.** This study investigated the effect of cognitive styles on users' information- seeking task performance using a knowledge domain information visualization system called CiteSpace.  
> **Method.** Sixteen graduate students participated in a user experiment. Each completed an extended cognitive style analysis wholistic-analytic test (the Extended CSA-WA test) on cognitive style, and then conducted eight tasks in the CiteSpace system.  
> **Analysis.** Users' behaviour and performance data were analysed using statistical techniques to explore the relationships among various measures. The techniques include Pearson Correlation, multivariate analysis of variance, Pearson Chi-squared test and non-parametric tests such as Wilcoxon signed-rank test.  
> **Results.** Results demonstrated that users' cognitive styles did impact their search performance. The wholistic-Analytic ratio obtained from the cognitive test is significantly correlated with result correctness. After dividing the subjects into two groups based on the median wholistic-analytic ratio, analysis showed that subjects with wholistic preference felt significantly more satisfied with results than those with analytic preference. Additionally, subjects with analytic preference found significantly more correct answers than those with wholistic preference.  
> **Conclusions.** These results indicated that cognitive style is an important factor in the study of information science and human-computer interaction. Research in this area provides valuable indication of future information system design.

## Introduction

Scholars have long recognized that user characteristics (e.g., domain knowledge level of users ([Zhang, _et al._ 2005](#ZAY2005))), task (e.g., task stages ([Kuhlthau 1993](#K1993)), task types ([Kim 2006](#K2006))), user situation, goal and context have significant influence on the information-seeking process ([Belkin 1996](#B1996), [2008](#B2008); [Ingwersen and Järvelin 2005](#IJ2005)). Human-computer interaction relies heavily on human cognition and perception ([Card _et al._ 1983](#CMN1983)). Human cognition and perception are processed at a series of levels during information-seeking process. ([Belkin 1980](#B1980); [Ingwersen 1996](#I1996)). Therefore, user characteristics, particularly users' cognitive characteristics are increasingly drawing attention in the field of information science and human computer interaction studies. As one of the cognitive characteristics, cognitive style was found to impact the search performance when using information systems ([Palmquist and Kim 2000](#PK2000); [Park and Black 2007](#PB2007)). Furthermore, the findings that (1) cognitive styles affect users' interaction with information systems on different information tasks ([Gwizdka 2009](#G2009)) and (2) users perceived differently between an information visualization system and a text information retrieval system ([Yuan _et al._ 2010](#YZT2010)) indicate that it is possible to improve the user performance of information (visualization) systems if different cognitive styles of information system users can be taken into account when designing such systems. This paper is part of a larger user experiment that involves thirty-two subjects, with sixteen using the [Web of Science system](http://apps.isiknowledge.com/WOS_GeneralSearch_input.do?product=WOS&search_mode=GeneralSearch) (reported in ([2011](#YL2011))) and sixteen using the [CiteSpace system](http://cluster.ischool.drexel.edu/~cchen/citespace/download.html). For the current study, we were particularly interested in if and how cognitive styles impact the user performance when using the CiteSpace information visualization system ([Chen 2004a](#C2004a)). In the following sections, the related work in the field, CiteSpace System, cognitive style test, research methodology, data analysis, discussion and conclusions are described in sequence.

## Related Work

Cognitive styles are approaches preferred by people for organizing and presenting information ([Riding and Rayner 1998](#RR1998)), and represent personality dimensions which have an impact on people's information collecting, analysing and evaluating ([Harrison and Rainer 1992](#HR1992)). The most widely researched cognitive styles are field dependence versus field independence ([Messick 1994](#M1994); [Chen 2000](#C2000)), which were derived from a series of studies of Witkin and Goodenough ([1981](#WG1981)). Field independent people tend to impose a structure on an unstructured field, while field dependent people perceive a complex field globally. Weller, Repman and Rooze ([1994](#WRR1994)) indicated that there are differences between field-dependent and field-independent cognitive styles in regard to how well people can restructure information by using salient cues and field arrangement.

Field-dependent/independent cognitive styles have been shown to significantly affect users' information seeking behaviour ([Chen and Ford 1998](#CF1998), [Ford and Chen 2000](#FC2000)). More recently, many researchers have investigated the effects of field-dependence/independence on user performance of information tasks. Kim ([2001](#FC2000)) explored the impact of cognitive style difference and online search experience on search performance and users' online navigation patterns. Results showed that cognitive styles had an impact on search time, and online search experience influenced search styles. Kim and Allen ([2002](#KA2002)) conducted two independent experiments to study the effect of differences in users' cognition and search tasks on Web searches. They found strong task effects on search activities, but interactions between cognitive and task variables were found on search activities only. An important finding from this study is that search efficiency depends on how well each searcher fits with the specific task.

Palmquist and Kim ([2000](#PK2000)) explored the effects of cognitive styles and on-line database search experience (novice and experienced) on the World Wide Web search performance of undergraduate students. They found that cognitive styles significantly affected the search performance of novice users, but the impact was greatly decreased for the experienced users. Chen and colleagues ([Chen _et al._ 2005](#CMD2005); [Chen _et al._ 2004](#CMM2004)) created a flexible Web directory (similar to a search engine) that accommodated both field-independent and field-dependent users. Lee and Boling ([2008](#LB2008)) argue that interactions between information representation approaches and learners' cognitive styles may have significant effects on learners' performance. They insist that the performance of a learner, especially with a low level of knowledge, could decline if a representational approach that contradicts their cognitive style is used. Frias-Martinez, Chen and Liu ([2009](#FCL2009)) found cognitive styles have great effects on users' responses to adaptability and adaptivity.

Besides field-dependence/independence, wholistic versus analytic styles also drew attention in the field ([Peterson _et al._ 2005a](#PDA2005a) and [2005b](#PDA2005b)). Riding and Cheema ([1991](#RC1991)) explain the differences between users with a wholistic and analytical cognitive styles by asserting that holists often view a situation as a whole, while analytics see situations as a collection of parts, often stressing only one or two aspects at a time. It is believed that wholistic versus analytic cognitive styles also have an impact on search behaviour and search performance ([Park and Black 2007](#PB2007)), but few studies have been done in this direction. Ford, Wood and Walsh ([1994](#FWW1994)) insist that field-independent students have greater propensities towards analytical cognition. Park and Black ([2007](#PB2007)) conducted a study in which sixty-one graduate students were tasked with finding answers to six open-ended questions on the World Wide Web. Subjects who had an analytical cognitive style used significantly more keywords than did subjects with an intuitive (wholistic) cognitive style. Ford, Miller and Moss ([2005](#FMM2005)) examined holist/analytic and imager/verbalizer cognitive styles as relating to individual differences and their effects on Web search strategy. They found that high levels of Boolean searching were positively correlated with a wholistic cognitive style.

In sum, research has shown that cognitive styles are important factors influencing the interaction between users and systems, as well as affecting information seeking performance. This research contributes to both the field of human-computer interaction and information science in that the findings about the effect of cognitive styles on user performance of the information visualization system, CiteSpace, show that there is relation between users' cognitive styles and their performance with information visualization systems. This further indicates that a good design of information visualization systems should take into account of users' cognitive styles.

The research question of this study is:

_Will cognitive styles affect users' search performance of an information visualization system?_

## The CiteSpace system

The CiteSpace system was chosen in this study because it is a well-known, actively maintained, stable and widely used knowledge domain visualization system. Also, it can be run on multiple computer platforms making it convenient for researchers to evaluate. The CiteSpace system was originally created to identify intellectual turning points ([Chen 2004a](#C2004a); [2004b](#C2004b)). It does so by constructing co-citation networks among highly cited articles and enables users to manipulate the resulting graphical network in a variety of ways such as displaying multiple time periods and setting different thresholds.

The visualization graph of the CiteSpace system is composed of nodes and lines connecting the nodes. There are nine types of nodes in the CiteSpace system (version 2.2.R1), including authors, term, keyword, category, institution, cited reference, cited journal, cited author and country. Correspondingly, nine visualization graphs were designed to represent the patterns in scientific literature. Figure 1 shows the first screen of the CiteSpace system. Users can specify the time period of the literature they want to search, choose nodes and set up thresholds in this screen. Figure 2 displays the resulting visualization graphs which correspond to the node "country." Other resulting graphs are similar to Figure 2.

<div align="center">![Figure 1: The first screen of the CiteSpace system](p499fig1.jpg)</div>

<div align="center">  
**Figure 1: The first screen of the CiteSpace system.**</div>

<div align="center">![Figure 2: Resulting graph showing node type for Country](p499fig2.jpg)</div>

<div align="center">  
**Figure 2: Resulting graph showing node type for Country.**</div>

## Cognitive test: the Extended Cognitive Style Analysis-Wholistic Analytic Test (Extended CSA-WA test)

Riding ([1991](#R1991)) designed the Cognitive Style Analysis test to measure wholistic and analytic cognitive styles by comparing how fast, on average, individuals respond on a verbal task compared to an imagery task, and how fast they respond, on average, on a wholistic task compared to an analytic task. Peterson, Deary, and Austin ([2003a](#PDA2003a); [2003b](#PDA2003b)) demonstrated that Riding's verbal-imagery style preference and wholistic-analytic style preference ratios had poor re-test reliability. Further, they ([2003a](#PDA2003a); [2003b](#PDA2003b)) found that an extended version of the CSA's wholistic-analytic dimension (Extended CSA-WA) improved the tests reliability to a satisfactory level.

The Extended Cognitive Styles Analysis-Wholistic-Analytic test contains forty wholistic questions in which the user is asked to judge whether two shapes are the same or different and forty analytic questions which task the user with determining if a certain shape is embedded within another. Participants are immediately provided with information on the accuracy of their choice and are encouraged, by the system, to respond accurately but at a comfortable pace. A subject's style preference for the Extended CSA-WA is measured by comparing the median reaction times on the wholistic questions with the median reaction times on the analytic questions, so that each participant is given a wholistic-analytic reaction time ratio which identifies their relative position on a wholistic-analytic style continuum ([Peterson and Deary 2006](#PD2006)). In short, the test measures user preferences for wholistic versus analytic ways of structuring information.

We chose this test in our study because it reliably detects individual differences in tasks of a higher order, relative to wholistic and analytic stimuli ([Peterson _et al._ 2005b](#PDA2005b); [Peterson and Deary 2006](#PD2006)).

### Tasks

The subjects in the study were given tasks that required them to use scenario-based topic descriptions to retrieve information from the CiteSpace system. The topics were related to life on Mars. The tasks followed the model of simulated work task situations proposed by Borlund ([2000](#B2000)). Borlund investigated whether the application of simulated work task situations can be recommended to future evaluations of interactive information retrieval systems. In Borlund's ([2000](#B2000)) study, data were collected consisting of twenty-four sets of responses from university students to questionnaires on searcher skills and experiences, 120 protocols of shorter verbal statements (e.g., the post-search interviews), and the 120 corresponding search transaction logs. The study found that in simulated work task situations, users' real information needs can be adequately represented by simulated information needs.

Our tasks were categorized into two groups: aspectual tasks and analytical search tasks. Aspectual tasks required the user to identify as many different aspects as possible for a given topic and save appropriate resources that cover all distinct aspects of that topic ([Over 1997](#O1997)). Analytical search tasks were defined as tasks which need more goal-oriented and systematic analytical strategies ([Marchionini 1995](#M1995)). Table 1 shows the topic or task description, type, and the corresponding node type in CiteSpace for each of these tasks. The CiteSpace node type indicates where the related information can be found on the CiteSpace system for this particular topic. It should be noted that in doing the tasks, the participants can use the function _text search_ on the top of the resulting graph (see Figure 2) to help locate the right answers. This function is available to both tasks.

The following is an example analytical search task.

> Scenario: As a graduate student, you want to write a paper about research on life on Mars. You are interested in how research has been done and what research has played an important role in this area during the past several years.  
>   
> Task: You need to collect some papers for the literature review. You know that some papers published by Edwards HGM would be very helpful. Please find the author who has the most collaboration with Edwards HGM, then put your answer on the answer sheet.

The following is an example aspectual task.

> Scenario: As a graduate student, you want to write a paper about research on life on Mars. You are interested in how research has been done and what research has played an important role in this area during the past several years.  
>   
> Task: You want to identify all the countries which have many publications (>20) and also have collaborated with each other. Please put your answer on the answer sheet.

Table 1 shows the brief description of all the tasks.

<table width="80%" border="1" cellspacing="0" cellpadding="3" align="center" style="border-right: #99f5fb solid; border-top: #99f5fb solid; font-size: smaller; border-left: #99f5fb solid; border-bottom: #99f5fb solid; font-style: normal; font-family: verdana, geneva, arial, helvetica, sans-serif; background-color: #fdffdd"><caption align="bottom">  
**Table 1: Categorized tasks**  
</caption>

<tbody>

<tr>

<th>Task No.</th>

<th>Node Type</th>

<th>Task Type</th>

<th>Task</th>

</tr>

<tr>

<td>1</td>

<td>Institution</td>

<td>Analytical search</td>

<td>Find the name of the university that has collaborated with Caltech in 2009 and published papers.</td>

</tr>

<tr>

<td>2</td>

<td>Author</td>

<td>Analytical search</td>

<td>Find the author who has the most collaboration with Edwards HGM.</td>

</tr>

<tr>

<td>3</td>

<td>Category</td>

<td>Analytical search</td>

<td>List two subject areas/categories that only authors from the USA are involved.</td>

</tr>

<tr>

<td>4</td>

<td>Category</td>

<td>Analytical search</td>

<td>Identify two years that large groups (more than 20 people) have published papers.</td>

</tr>

<tr>

<td>A</td>

<td>Institution</td>

<td>Aspectual</td>

<td>Find all the institutions which collaborated on the topic in 2008.</td>

</tr>

<tr>

<td>B</td>

<td>Country</td>

<td>Aspectual</td>

<td>Identify all the countries which have many publications (>20) and also have collaborated with each other.</td>

</tr>

<tr>

<td>C</td>

<td>Keyword</td>

<td>Aspectual</td>

<td>List all the keywords that appear frequently with the word "life."</td>

</tr>

<tr>

<td>D</td>

<td>Category</td>

<td>Aspectual</td>

<td>Identify all the subject areas/categories that more papers were published in 2008 than in any other year.</td>

</tr>

</tbody>

</table>

## Method

To address our research question, we designed a user-centered experiment, which collected data on cognitive styles by asking subjects to complete the ECSA-WA test first, and then to perform eight tasks shown in Table 1.

### Experimental design

The subjects completed the cognitive test, and then performed eight tasks using the CiteSpace system. Tasks were randomly assigned using a Latin-Square design, which ensured that no subject was given the tasks in the same order.

### Subjects

Sixteen graduate students from different departments in the University at Albany, State University of New York, participated in the experiment. They were recruited through notices posted to several departmental listservs and by in-class announcements.

### Dataset

The dataset was constructed by searching the topic _life on Mars_, language _English_, document type _articles_, and published between the years of _2000-2009_ in the ISI Web of Science. In total, 857 records were retrieved from the Web of Science system. All these documents were saved in a database, which was then uploaded to the CiteSpace sytem.

### Measures

Cognitive style was measured by the Extended CSA-WA as described in the previous section. Subjects' task performance was measured by the following metrics: user satisfaction with the task results, time to task completion (in minutes), result correctness, aspectual recall, and number of mouse clicks during the task.

User satisfaction is one of the most popular performance measures ([Harter and Hert 1997](#HH1997)). As in other studies, user satisfaction was measured by asking each subject in the post-task questionnaire to rate his or her own satisfaction with the search results on a seven-point Likert Scale ranging from _Not at all_ to _Extremely_ (satisfied).

Time to task completion was computed from logs of the software _Morae_. It was measured starting from the time the user opened the visualization window until the user finished typing the answer into the answer sheet.

Result correctness, particularly in a question-answering task environment, has been widely accepted as important measure of retrieval effectiveness ([Belkin _et al_. 2001](#B2001); [Yuan and Belkin 2007](#YB2007), [2010](#YB2010)). In this study, result correctness was measured as the external assessor's judgment of the subject's saved answer(s). Answers were judged on a two-point scale: _Incorrect (0),_ and _Correct (1)_. An external assessor was used to judge the result correctness because we wanted to obtain relatively objective judgments.

Aspectual recall, a measure developed in the TREC Interactive Track ([Dumais and Belkin 2005](#DB2005)), is the ratio of aspects of the search topic identified by the subject to the total number of aspects of the topic.

Number of mouse clicks reflects a subject's actions during performing a task. It was measured by counting the total number of mouse clicks recorded in the logging software. Number of mouse clicks indicates to what extent the subject interacts with the visualization graph in the CiteSpace system.

### Procedure

The subjects read and signed a consent form and filled out an entry questionnaire ([Appendix A](#appa)) about their background, computer experience and previous searching experience. Next, they were given the Extended CSA-WA test. The test administrator launched the introductory, start up screen for the test and then selected Test/New. Users were given brief instructions about the test and were then asked to fill in the required demographic data (name, age, etc.). Once this information was entered into the system, the test began. Then they were given a tutorial of the CiteSpace system. In the tutorial, the subjects were taught how to set up the time slices and to choose the dataset to get the visualization graph. The subjects were then given information about the graph (meaning of nodes, lines, co-citation, etc). After the tutorial, the subjects did two training tasks of each task type. Before each task the subjects filled out a pre-task questionnaire ([Appendix B](#appb)). They were given up to ten minutes to conduct each task. The interaction between the subjects and the system was logged. After completing each task, they filled in a post-task questionnaire ([Appendix C](#appc)). After the subjects finished all the tasks, they were asked to complete an exit questionnaire ([Appendix D](#appd)). Each subject was paid $25 for his or her completion of the experiment. The experiment was conducted in a human-computer interaction lab at the University at Albany, and each subject was tested individually.

_Morae_ 2.1 TechSmith logging software was used to log the interactions between the user and the system.

## Results

### Results of the Extended CSA-WA test

The wholistic-analytic ratio is calculated as the ratio of the median reaction time on the wholistic items to the median reaction time on the analytic items and was automatically shown in an Excel report after each subject completed the test. The minimum of the ratios is 0.96, and the maximum is 3.29\. The median is 1.31\. The mean is 1.42, and the standard deviation is 0.53\. A lower ratio indicates a tendency toward a wholistic preference, and higher ratios indicate a tendency for an analytic preference.

Figure 3 displays the histogram of the wholistic-analytic ratio. The ratio bin of 1.1 to 1.3 has the most participants (5), closely followed by the bin of 1.3 to 1.5 which has 4 participants.

<div align="center">![Figure 3: The histogram of number of participants per ratio bin](p499fig3.jpg)</div>

<div align="center">  
**Figure 3: The histogram of number of participants per ratio bin.**</div>

### Effects of wholistic-analytic ratio on user performance measures

Results of task performance measures are presented in Table 2.

<table width="80%" border="1" cellspacing="0" cellpadding="3" align="center" style="border-right: #99f5fb solid; border-top: #99f5fb solid; font-size: smaller; border-left: #99f5fb solid; border-bottom: #99f5fb solid; font-style: normal; font-family: verdana, geneva, arial, helvetica, sans-serif; background-color: #fdffdd"><caption align="bottom">  
**Table 2: Task performance results**  
</caption>

<tbody>

<tr>

<th>Performance Measure</th>

<th>Minimum</th>

<th>Maximum</th>

<th>Mean</th>

<th>Standard Deviation</th>

</tr>

<tr>

<td>Time (mins)</td>

<td align="center">0.60</td>

<td align="center">9.93</td>

<td align="center">3.71</td>

<td align="center">2.08</td>

</tr>

<tr>

<td>User satisfaction (1-7)</td>

<td align="center">1</td>

<td align="center">7</td>

<td align="center">5.16</td>

<td align="center">1.88</td>

</tr>

<tr>

<td>Result correctness(for analytical search tasks)(0-1)</td>

<td align="center">0</td>

<td align="center">1</td>

<td align="center">0.69</td>

<td align="center">0.47</td>

</tr>

<tr>

<td>Number of mouse clicks</td>

<td align="center">3</td>

<td align="center">146</td>

<td align="center">38.87</td>

<td align="center">24.71</td>

</tr>

<tr>

<td>Aspectual recall (for aspectual tasks)</td>

<td align="center">0</td>

<td align="center">1</td>

<td align="center">0.56</td>

<td align="center">0.37</td>

</tr>

</tbody>

</table>

As demonstrated in Table 2, in general, across all participants, the user satisfaction and the result correctness were relatively high, in comparison to other measures.

### Correlation

One way to investigate the effect of the cognitive styles is to see whether there were significant correlations between the cognitive styles and the performance measures. Pearson Correlation statistical analysis was performed to find the relationship between the cognitive styles and these measures. Results indicated that the wholistic-analytic ratio (mean=1.42, standard deviation =0.52) was significantly correlated with result correctness (mean=0.70, standard deviation=0.46 ), r=0.274, p=0.028\. Figure 4 showed a clear trend that the group of subjects with more correct answers have higher median ratios. We did not find significant correlations between the ratio and other measures.

<div align="center">![Figure 4: The first screen of the CiteSpace system](p499fig4.jpg)</div>

<div align="center">  
**Figure 4: A box plot of the subjects' wholistic-analytic ratio by the total number of correct answers.**</div>

In order to further test the impact of the cognitive styles on task performance, subjects were divided into two groups based on their wholistic-analytic ratio: a higher ratio group (HWA group) and a lower ratio group (LWA group). Their performance measures were then compared between the two groups. The division of the higher ratio and lower ratio was chosen based on the median ratio: those whose ratios were higher than the median ratio were included in the higher ratio group and those whose ratios were lower than the median ratio were included in the lower ratio group.

### Demographics

Subject characteristics are shown in Table 3\. Table 4 displays the computer and searching experience of the subjects. Subjects rated their computer and searching experience on a seven-point Likert Scale, from 1=low to 7=high. Subjects used computers very frequently (mean=7, standard deviation=0). They had high searching experience with the WWW (mean=6.44, standard deviation=0.81). Their computer expertise was relatively high (mean=4.56, standard deviation=0.81), and their searching expertise was also high (mean=4.88, standard deviation=0.96). Their searching experience with information visualization systems was low (mean=1.31, standard deviation=0.6). The average number of years of their searching experience was 8.94 years. Overall, the subjects in this experiment had high search experience, but little experience in searching information visualization systems.

<table width="60%" border="1" cellspacing="0" cellpadding="3" align="center" style="border-right: #99f5fb solid; border-top: #99f5fb solid; font-size: smaller; border-left: #99f5fb solid; border-bottom: #99f5fb solid; font-style: normal; font-family: verdana, geneva, arial, helvetica, sans-serif; background-color: #fdffdd"><caption align="bottom">  
**Table 3: Demographic characteristics of the subjects**  
</caption>

<tbody>

<tr>

<th>Characteristics</th>

<th>Value</th>

<th>LWA group</th>

<th>HWA group</th>

</tr>

<tr>

<td>Age</td>

<td align="center">20-29</td>

<td align="center">4</td>

<td align="center">3</td>

</tr>

<tr>

<td></td>

<td align="center">30-39</td>

<td align="center">3</td>

<td align="center">4</td>

</tr>

<tr>

<td></td>

<td align="center">40-49</td>

<td align="center">1</td>

<td align="center">1</td>

</tr>

<tr>

<td></td>

<td align="center">20-29</td>

<td align="center">4</td>

<td align="center">3</td>

</tr>

<tr>

<td>Sex</td>

<td align="center">Male</td>

<td align="center">3</td>

<td align="center">4</td>

</tr>

<tr>

<td></td>

<td align="center">Female</td>

<td align="center">5</td>

<td align="center">4</td>

</tr>

<tr>

<td>Highest Degree Earned</td>

<td align="center">Bachelor</td>

<td align="center">6</td>

<td align="center">6</td>

</tr>

<tr>

<td></td>

<td align="center">Master</td>

<td align="center">2</td>

<td align="center">2</td>

</tr>

</tbody>

</table>

<table width="60%" border="1" cellspacing="0" cellpadding="3" align="center" style="border-right: #99f5fb solid; border-top: #99f5fb solid; font-size: smaller; border-left: #99f5fb solid; border-bottom: #99f5fb solid; font-style: normal; font-family: verdana, geneva, arial, helvetica, sans-serif; background-color: #fdffdd"><caption align="bottom">  
**Table 4: Computer and searching experience of subjects.**</caption>

<tbody>

<tr>

<th>Computer and Searching Experience</th>

<th>LWA group Mean (standard deviation)</th>

<th>HWA group Mean (standard deviation)</th>

</tr>

<tr>

<td>Computer daily use</td>

<td align="center">7.00 (0.00)</td>

<td align="center">7.00 (0.00)</td>

</tr>

<tr>

<td>Expertise of computer</td>

<td align="center">4.63 (0.74)</td>

<td align="center">4.50 (0.93)</td>

</tr>

<tr>

<td>Searching experience of Catalog</td>

<td align="center">5.38 (1.30)</td>

<td align="center">5.00 (1.07)</td>

</tr>

<tr>

<td>Searching experience of commercial systems</td>

<td align="center">3.00 (1.85)</td>

<td align="center">2.88 (1.73)</td>

</tr>

<tr>

<td>Searching experience of WWW</td>

<td align="center">6.63 (0.52)</td>

<td align="center">6.25 (1.04)</td>

</tr>

<tr>

<td>Searching experience with information visualization systems</td>

<td align="center">1.25 (0.71)</td>

<td align="center">1.38 (0.52)</td>

</tr>

<tr>

<td>Searching experience with Web of Science</td>

<td align="center">1.00 (0.00)</td>

<td align="center">1.00 (0.00)</td>

</tr>

<tr>

<td>Frequency of search</td>

<td align="center">5.75 (1.49)</td>

<td align="center">6.13 (1.13)</td>

</tr>

<tr>

<td>Search information found</td>

<td align="center">5.50 (1.20)</td>

<td align="center">6.25 (0.89)</td>

</tr>

<tr>

<td>Expertise of searching</td>

<td align="center">4.88 (0.99)</td>

<td align="center">4.88 (0.99)</td>

</tr>

<tr>

<td>Number of years of searching experience</td>

<td align="center">7.75 (4.20)</td>

<td align="center">10.13 (3.40)</td>

</tr>

</tbody>

</table>

### Subject group versus performance measures

ANOVA results (see Table 5) did not find any significant differences between these two groups in terms of task completion time and number of mouse clicks.

the Pearson Chi-squared test showed that the HWA group got significantly more correct answers for analytical search tasks (mean=0.81, SD=0.40) than the LWA group (mean=0.56, standard deviation=0.50), ?<sup>2</sup>=4.65, df=1, p=0.03\. The LWA group identified more aspects (mean=0.58, standard deviation=0.37) for aspectual tasks than the HWA group (mean=0.54, standard deviation=0.37), the difference was not significant from the ANOVA test, F(1,62)=0.11, p=0.74.

Wilcoxon signed-rank test results showed that the LWA group felt significantly more satisfied with the results (mean=5.53, SD=1.70) than the HWA group (mean=4.80, SD=1.99), Z=-2.31, p=0.02.

<table width="80%" border="1" cellspacing="0" cellpadding="3" align="center" style="border-right: #99f5fb solid; border-top: #99f5fb solid; font-size: smaller; border-left: #99f5fb solid; border-bottom: #99f5fb solid; font-style: normal; font-family: verdana, geneva, arial, helvetica, sans-serif; background-color: #fdffdd"><caption align="bottom">  
**Table 5: Task performance (* significant at <0.05 level).**</caption>

<tbody>

<tr>

<th> </th>

<th>LWA group</th>

<th>HWA group</th>

</tr>

<tr>

<td>Time (mins)</td>

<td align="center">3.68 (2.01)</td>

<td align="center">3.73 (2.17)</td>

</tr>

<tr>

<td>User satisfaction (1-7)</td>

<td align="center">5.53* (1.70)</td>

<td align="center">4.80 (1.99)</td>

</tr>

<tr>

<td>Result correctness (for analytical search tasks)(0-1)</td>

<td align="center">0.56 (0.50)</td>

<td align="center">0.81* (0.40)</td>

</tr>

<tr>

<td>Number of mouse clicks</td>

<td align="center">41.19 (27.39)</td>

<td align="center">36.55 (21.67)</td>

</tr>

<tr>

<td>Aspectual recall (for aspectual tasks)</td>

<td align="center">0.58 (0.37)</td>

<td align="center">0.54 (0.37)</td>

</tr>

</tbody>

</table>

### Interaction of subject type and task type with time and mouse clicks

As mentioned earlier, the subjects were divided into HWA group and LWA group based on the median of their wholistic-analytic ratio. To further investigate the interaction effect of subject type and task type on such performance measures as time and mouse clicks, we performed MANOVA statistical analysis. A 2x2 MANOVA test was used to test the interaction effect of group type and task type on time and mouse clicks. Results showed that there was no significant effect on either of them.

### Task order

We want to find out whether the order of the tasks had any impact on the task results. The impact of task order on time and mouse clicks was analysed using ANOVA analysis. No significant differences were found for either of them. The interaction effects of task order and wholistic-analytical ratio group on time and mouse clicks were also analysed using MANOVA, no significant differences were found.

## Discussion

Our results indicated that cognitive styles (wholistic versus analytic) had a significant impact on task performance measured by result correctness, but did not significantly affect other performance measures such as time, number of mouse clicks and aspectual recall. Subjects with high wholistic-analytic ratios (analytic preference) had identified significantly more correct answers than subjects of lower wholistic-analytic ratios (wholistic preference). Ford _et al._ ([2002](#FWFES): 733) indicated that serialists preferred '_a more secure and predictable step by step approach_' while holists showed more exploratory behaviour and '_are more likely to be open to indeed seek out such relatively unplanned encounters_'. This may explain the above results. Our inference is that since the HWA group (analytic preference) tended to focus on more details of the resulting graph of the CiteSpace system and be less distracted by items of serendipity than the LWA group (wholistic preference), it is likely that the HWA group (analytic preference ) will find more correct answers.

Statistical difference was also shown that the LWA group with wholistic preference appeared to feel significantly more satisfied with the results than did the HWA group with analytic preference. This explanation can be further confirmed from the results of the post-task questionnaire, which showed that the LWA group (wholistic preference) claimed that they learned more new knowledge from the system than those of the HWA group (analytic preference). It could be that, as the LWA group felt they learned more new knowledge, they were more satisfied with the results. Satisfaction with new knowledge are also found for people with high domain knowledge. Yuan _et al._ ([2010](#YC2010)) found that people who have higher domain knowledge felt that they learned more new knowledge and felt more satisfied with results than those of lower domain knowledge. This may indicate, for information system design, that focusing on a global view of the system will lead to more satisfaction of people with wholistic preference.

Park and Black ([2007](#PB2007)) found out that cognitive styles (analytic versus intuitive) did not affect the searching time and the number of nodes. In our study, the cognitive styles did not have a significant impact on time and mouse clicks, which confirm Park and Black's ([2007](#PB2007)) findings. Some research on the effect of field dependence versus field independence on search performance has shown contradictory results. For example, Kim ([2001](#K2001)) found that cognitive styles had an impact on search time, and Palmquist and Kim ([2000](#PK2000)) found that cognitive style significantly affected the search performance (measured as time and number of nodes) of novice users. This contradiction may be attributed to what has been found out from Kim and Allen ([2002](#KA2002)) that the search efficiency depends on how well each searcher fits with the specific task. Also, Palmquist and Kim ([2000](#PK2000)) identified that search experience is an important factor to consider.

We considered whether the results could have arisen from bias among the subjects with respect to their topic expertise or familiarity. The data on these factors (see Table 6) seem not to support this, as the subjects' mean self-reported expertise and familiarity, measured on a seven-point Likert Scale, are all uniformly low, for all topics, with rather low standard deviation, as well. No subject indicated topic familiarity or topic expertise of six or higher for any topic; these data are insufficient to investigate any possible interaction of familiarity with system.

<table width="80%" border="1" cellspacing="0" cellpadding="3" align="center" style="border-right: #99f5fb solid; border-top: #99f5fb solid; font-size: smaller; border-left: #99f5fb solid; border-bottom: #99f5fb solid; font-style: normal; font-family: verdana, geneva, arial, helvetica, sans-serif; background-color: #fdffdd"><caption align="bottom">  
**Table 6: Topic familiarity and expertise (seven-point low to high Likert Scale).**</caption>

<tbody>

<tr>

<th rowspan="2">Topic No.</th>

<th rowspan="2">Topic</th>

<th colspan="2">LWA group Mean (s.d.)</th>

<th colspan="2">HWA group Mean (s.d.)</th>

</tr>

<tr>

<th>Topic familiarity</th>

<th>Topic expertise</th>

<th>Topic familiarity</th>

<th>Topic expertise</th>

</tr>

<tr>

<td>1</td>

<td align="left">Find the name of the university that has collaborated with Caltech in 2009 and published papers.</td>

<td align="left">1.75 (1.16)</td>

<td align="left">1.50 (0.76)</td>

<td align="left">2.25 (1.83)</td>

<td align="left">2.00 (1.41)</td>

</tr>

<tr>

<td>2</td>

<td align="left">Find the author who has the most collaboration with Edwards HGM.</td>

<td align="left">1.38 (0.52)</td>

<td align="left">1.25 (0.46)</td>

<td align="left">2.25 (1.58)</td>

<td align="left">2.13 (1.36)</td>

</tr>

<tr>

<td>3</td>

<td align="left">List two subject areas/categories that only authors from the USA are involved.</td>

<td align="left">1.25 (0.46)</td>

<td align="left">1.13 (0.35)</td>

<td align="left">1.75 (1.16)</td>

<td align="left">1.63 (1.41)</td>

</tr>

<tr>

<td>4</td>

<td align="left">Identify two years that large groups (more than 20 people) have published papers.</td>

<td align="left">1.25 (0.46)</td>

<td align="left">1.13 (0.35)</td>

<td align="left">1.63 (0.92)</td>

<td align="left">1.13 (0.35)</td>

</tr>

<tr>

<td>A</td>

<td align="left">Find all the institutions which collaborated on the topic in 2008.</td>

<td align="left">1.25 (0.46)</td>

<td align="left">1.13 (0.35)</td>

<td align="left">2.25 (1.58)</td>

<td align="left">1.75 (1.16)</td>

</tr>

<tr>

<td>B</td>

<td align="left">Identify all the countries which have many publications (>20) and also have collaborated with each other.</td>

<td align="left">1.25 (0.46)</td>

<td align="left">1.13 (0.35)</td>

<td align="left">2.38 (1.51)</td>

<td align="left">2.25 (1.28)</td>

</tr>

<tr>

<td>C</td>

<td align="left">List all the keywords that appear frequently with the word "life."</td>

<td align="left">1.63 (1.06)</td>

<td align="left">1.50 (1.07)</td>

<td align="left">2.13 (1.25)</td>

<td align="left">1.50 (1.07)</td>

</tr>

<tr>

<td>D</td>

<td align="left">Identify all the subject areas/categories that more papers were published in 2008 than in any other year.</td>

<td align="left">1.38 (0.74)</td>

<td align="left">1.25 (0.71)</td>

<td align="left">1.50 (0.53)</td>

<td align="left">1.25 (0.46)</td>

</tr>

</tbody>

</table>

In comparison to the studies using text-based systems, we used a visualization system instead. This may explain the difference in findings between this study and some other studies, e,g., Kim ([2001](#K2001)) and Palmquist and Kim ([2000](#PK2000)), in which cognitive style is found having impact on search time. Visualization systems work differently than text-based systems in terms of the interaction between the user and the system. It is possible that the time effect found in a text-based system would not hold for a visualization system. One factor that is worth investigation may be the user's spatial capability and its relationship with search performance using visualization systems. This will be investigated in our future studies.

## Conclusions

In this study, we tested if and how cognitive styles would affect task performance of information visualization systems. Sixteen subjects participated in the experiment and each of them performed eight tasks using the CiteSpace information visualization system. We conclude that the cognitive styles (wholistic versus analytic) appear to have certain impact on users' task performance of information visualization systems:

For the first time, this study gives statistically significant empirical support that the subjects with analytic preference can get significantly more correct answers than subjects with a wholistic preference. The subjects with wholistic preference felt significantly more satisfied with the results than the subjects with analytic preference. It is acknowledged that the study also had limitations. We were constrained by a limited, and to some extent rather homogeneous set of subjects, and a limited number of task topics. The only realistic way to address this issue is to do more studies, which we intend to perform.

Despite the limitations, this study contributes to information science the findings of the impact users' cognitive styles (wholistic vs. analytic) have on their search performance. Information search is a very complex process, involving many cognitive and behavioural factors. It is our hope that with more and more similar studies being conducted, people's information seeking behaviour can be better understood. In the future, we aim to generalize the results of this study to other information visualization systems, for example, testing how can wholistic vs. analytical have an impact on user performance of other information visualization systems, and how wholistic vs. analytical will affect the user performance of textual-based systems. We believe that user performance of visualization systems can be improved by taking into account of different cognitive styles of information retrieval system users.

## Acknowledgements

This project was funded by University at Albany Faculty Research Awards Program (FRAP).

## About the authors

Dr. Xiaojun Yuan is assistant professor in Department of Information Studies, College of Computing and Information, at University at Albany, State University of New York. She holds a Ph.D. degree in information science from Rutgers, The State University of New Jersey. Her research interests include interactive information retrieval, human information behaviour, information visualization, human computer interaction, user interface design and evaluation and usability testing. She can be contacted at [xyuan@albany.edu](mailto:xyuan@albany.edu).

Dr. Xiangmin Zhang is assistant professor in School of Library and Information Science, at Wayne State University. Dr. Zhang graduated from the University of Toronto with a PhD in information science, concentrating on Human-Computer Interaction. His research interests include user modelling, usability testing, user experience, personalization techniques in information retrieval, collaborative information retrieval, and digital libraries. He frequently presents at international conferences and has published in various academic journals and conference proceedings. He can be contacted at [ae9101@wayne.edu](mailto:ae9101@wayne.edu)

Dr. Chaomei Chen is associate professor at Drexel University. He is a Chang Jiang Scholar at Dalian University of Technology, China and was a visiting professor at Brunel University in the United Kingdom (2002-2008). He received his bachelors degree from Nankai University, China, his master's degree from the University of Oxford and his doctorate in computer science from the University of Liverpool. Dr. Chen is the author of Information Visualization: Beyond the Horizon (Springer 2004, 2006) and Mapping Scientific Frontiers: The Quest for Knowledge Visualization (Springer 2003). He is the founder and the Editor-in-Chief of the journal _Information Visualization_ (Palgrave-Macmillan). He can be contacted at [chaomei.chen@cis.drexel.edu](mailto:chaomei.chen@cis.drexel.edu)

Joshua M. Avery graduated from the College of Computing and Information, at University at Albany, State University of New York. Joshua has a B.A. from the University of Cincinnati and an M.A. from Miami University. He is a librarian at the R.G. Flexon Memorial Library at God's Bible School and College in Cincinnati, OH and can be contacted at [javery@gbs.edu](mailto:javery@gbs.edu).

#### References

*   Belkin, N.J. (1980). Anomalous states of knowledge as a basis for information retrieval. _Canadian Journal of Information Science_, **6**(5), 133-143.
*   Belkin, N.J. (1996). [Intelligent information retrieval: whose intelligence?](http://www.webcitation.org/63O0RkZgE) In Jorgen Krause, Matthias Herfurth & Jutta Marx, (Eds.). _Herausforderungen an die Informationswirtschaft: Informationsverdichtung, Informationsbewertung und Datenvisualisierung. Proceedings des 5\. Internationalen Symposiums fur Informationswissenschaft (ISI96), Humboldt Universität zu Berlin, 17-19 Oktober, 1996._ (pp. 25-31). Konstanz, Germany: Universitätsverlag Konstanz. Retrieved 22 November, 2011 from http://epub.uni-regensburg.de/10867/1/Herausforderungen_an_die_Informationswirtschaft.pdf (Archived by 
 at http://www.webcitation.org/63O0RkZgE)
*   Belkin, N.J. (2008). Some(what) grand challenges for information retrieval. _SIGIR Forum,_ **42**(1), 47-54.
*   Belkin, N.J., Cool, C., Kelly, D., Lin, S-J., Park, S.Y., Perez-Carballo., J. & Sikora, C. (2001). Iterative exploration, design and evaluation of support for query reformulation in interactive information retrieval. _Information Processing & Management,_ **37**(3), 403-434.
*   Borlund, P. (2000). Experimental components for the evaluation of interaction information retrieval systems. _Journal of Documentation_,**5**(1), 71-90.
*   Card, S.K., Moran, T.P. & Newell, A. (Eds.). (1983). _The psychology of human-computer interaction_. Hillsdale, NJ: Lawrence Erlbaum.
*   Chen, C. (2000) Individual differences in a spatial-semantic virtual environment. _Journal of the American Society for Information Science_, **51**(6):529-542.
*   Chen, C. (2004a). _Information visualization: beyond the horizon_. (2nd ed.). Berlin: Springer-Verlag.
*   Chen, C. (2004b). Searching for intellectual turning points: progressive lnowledge domain visualization. _Proceedings of the National Academy of Sciences of the United States of America_, **101**(Supplement. 1), 5303-5310.
*   Chen, S.Y. & Ford, N. (1998). Modelling user navigation behaviours in a hypermedia-based learning system: an individual differences approach. _Knowledge Organization_, **25**(3), 67-78.
*   Chen, S.Y., Magoulas, G.D. & Dimakopoulos, D. (2005). A flexible interface design for web directories to accommodate different cognitive styles. _Journal of the American Society for Information Science and Technology,_**56**(1), 70-83.
*   Chen, S.Y., Magoulas, G.D. & Macredie, R.D. (2004). Cognitive styles and users' responses to structured information representation. _International Journal on Digital Libraries,_ **4**(2), 93-107.
*   Dumais, S. & Belkin, N.J. (2005). The TREC interactive tracks: putting the user into search. In E.M. Voorhees & D.K. Harman (Eds.). _TREC: experiment and evaluation in information retrieval_ (pp. 123-152). Cambridge, MA: MIT Press.
*   Ford, N. & Chen, S.Y. (2000) Individual differences, hypermedia navigation and learning: an empirical study. _Journal of Educational Multimedia and Hypermedia,_ **9**(4), 281-312.
*   Ford, N., Miller, D. & Moss, N. (2005). Web search strategies and human individual differences: cognitive and demographic factors, Internet attitudes and approaches. _Journal of the American Society for Information Science and Technology,_ **56**(7), 741-756.
*   Ford, N., Wilson, T.D., Foster, A., Ellis, D. & Spink, A. (2002). Information seeking and mediated searching. Part 4\. Cognitive styles in information seeking. _Journal of the American Society for Information Science and Technology, **53**_(9):728-735.
*   Ford, N., Wood, F. & Walsh, C. (1994). Cognitive styles and searching. _Online and CDROM Review_, **18**(2), 79-86.
*   Frias-Martinez, E., Chen, S. & Liu, X. (2009). Evaluation of a personalized digital library based on cognitive styles: adaptivity vs. adaptability. _International Journal of Information Management,_ **29**(1), 48-56.
*   Gwizdka, J. (2009). [What a difference a tag cloud makes: effects of tasks and cognitive abilities on search results interface use](http://www.webcitation.org/60Ru2Vkv2)_. Information Research,_ **14**(4) paper 414\. Retrieved 25 July, 2011 from http://informationr.net/ir/14-4/paper414.html. (Archived by WebCite<sup>®</sup> at http://www.webcitation.org/60Ru2Vkv2)
*   Harrison, A.W. & Rainer, R.K. (1992). The influence of individual differences on skill in end-user computing. _Journal of Management Information Systems,_ **9**(2), 93-111.
*   Harter, S. & Hert, C. (1997). Evaluation of information retrieval systems: approaches, issues, and methods. _Annual Review of Information Science and Technology_, **32**, 3-94.
*   Ingwersen, P. (1996). Cognitive perspectives of information retrieval interaction: elements of a cognitive IR theory. _Journal of Documentation,_ **52**(1), 3-50.
*   Ingwersen, P. & J?rvelin, K. (2005). _The turn: integration of information seeking and retrieval in context_. Dordrecht, Netherlands: Springer Verlag.
*   Kim, K.S. (2001). Implications of user characteristics in information seeking on the World Wide Web. _International Journal of Human-Computer Interaction,_ **13**(3), 323-340.
*   Kim, K.S. & Allen, B. (2002). Cognitive and task influences on Web searching behavior. _Journal of the American Society for Information Science and Technology,_ **53**(2), 109-119.
*   Kim, J.-Y. (2006). _Task as a predictable indicator for information seeking behavior on the Web_. Unpublised Ph.D. dissertation, Rutgers University, New Burnswick, New Jersey, USA.
*   Kuhlthau C. C. (1993). A principle of uncertainty for information seeking. _Journal of Documentation,_ **49**(4), 339 - 355.
*   Lee, J. & Boling, E. (2008). Information-conveying approaches and cognitive styles of mental modeling in a hypermedia-based learning environment. _Journal of the American Society for Information Science and Technology_, **59**(4), 644-661.
*   Marchionini, G. (1995). _Information seeking in electronic environments._ Cambridge: Cambridge University Press.
*   Messick, S. (1994). The matter of style: manifestations of personality in cognition, learning and teaching. _Educational Psychologist_, **29**(1), 121-136.
*   Over, P. (1997). TREC-5 interactive track report. In D. Harman (Ed.), _TREC-5, proceedings of the fifth text retrieval conference_ (pp. 29-56). Washington, DC: Government Printing Office.
*   Park, Y. & Black, J. (2007). Identifying the impact of domain knowledge and cognitive style on Web-based information search behavior. _Journal of Educational Computing Research,_ **36**(1), 15-37.
*   Palmquist, R.A. & Kim, K.S. (2000). Cognitive style and on-line database search experience as predictors of Web search performance. _Journal of the American Society for Information Science,_ **51**(6), 558-566.
*   Peterson, E.R. & Deary, I.J. (2006) Examining wholistic-analytic style using preferences in early information processing. _Personality and Individual Differences,_ **41**(1), 3-14.
*   Peterson, E.R., Deary, I.J. & Austin, E.J. (2003a). The reliability of Riding's cognitive styles analysis test. _Personality and Individual Differences,_ **34**(5), 881-891.
*   Peterson, E.R., Deary, I.J. & Austin, E.J. (2003b). On the assessment of cognitive style: four red herrings. _Personality and Individual Differences,_ **34**(5), 899-904.
*   Peterson, E.R., Deary, I.J. & Austin, E.J. (2005a). A new measure of verbal-imagery cognitive style: VICS. _Personality and Individual Differences_, **38**(6), 1269-1281
*   Peterson, E.R., Deary, I.J. & Austin, E.J. (2005b). Are intelligence and personality related to verbal-imagery and holistic-analytic cognitive styles? _Personality and Individual Differences_, **39**(1), 201-213.
*   Riding, R. (1991). Cognitive style analysis-CSA administration. Birmingham, UK: Learning and Training and Technology.
*   Riding, R. & Cheema, I. (1991). Cognitive styles - an overview and integration. _Educational Psychology,_ **11**(3-4), 193-215.
*   Riding, R. & Rayner, S. G. (1998). _Cognitive styles and learning strategies_. London: David Fulton.
*   Weller, H.G., Repman, J. & Rooze, G.E. (1994). The relationship of learning, behavior and cognitive styles in hypermedia-based instruction: implications for design of HBI. _Computers in the Schools,_ **10**(3/4), 401-420.
*   Witkin, H.A. & Goodenough, D.R. (1981). _Cognitive styles, essence and origin: field dependence and field independence_. New York, NY: International Universities Press, Inc.
*   Yuan, X.-J. & Belkin, N.J. (2007). Supporting multiple information strategies in a single system framework. In: C.L.A. Clarke, N. Fuhr, N. Kando, W. Kraaij, A.P. de Vries (Eds.) _Proceedings of the 30th annual international ACM SIGIR conference on Research and development in information retrieval_. SIGIR 2007 (pp. 247-254). New York: ACM Press.
*   Yuan, X.-J. & Belkin, N. J. (2010). Investigating information retrieval support techniques for different information-seeking strategies. _Journal of the American Society for Information Science and Technology_, **61**, 1543-1563.
*   Yuan, X.-J. & Liu, J. (2011). _[An exploratory study of the effect of cognitive styles on user performance in an information system](https://docs.google.com/a/kent.edu/viewer?a=v&pid=sites&srcid=ZGVmYXVsdGRvbWFpbnxoY2lyd29ya3Nob3B8Z3g6MzQ5OGI1ZjNjMmFlZDE4OA)_. Paper presented at the 5th Workshop on Human-Computer Interaction and Information Retrieval. Retrieved 22 November, 2011 from https://docs.google.com/a/kent.edu/viewer?a=v&pid=sites&srcid=ZGVmYXVsdGRvbWFpbnxoY2lyd29ya3Nob3B8Z3g6MzQ5OGI1ZjNjMmFlZDE4OA
*   Yuan, X.-J., Chen, C., Zhang, X.-J., Avery, J. & Xu, T. (2010). Interacting with visualized information: an empirical user study on an information visualization system. Under review.
*   Yuan, X.-J., Zhang, X.-M. & Trofimovsky, A. (2010). Testing visualization on the use of information systems. In _IIiX '10 Proceeding of the third symposium on Information interaction in context_, (pp. 365-369). New York, NY: ACM Press.
*   Zhang, X., Anghelescu, H. & Yuan, X. (2005). [Domain knowledge, search behaviour, and search effectiveness of engineering/science students: an exploratory study](http://www.webcitation.org/60Rtn1IBG) . _Information Research_, **10**(2) paper 217\. Retrieved 25 July, 2011 from http://informationr.net/ir/10-2/paper217.html. (Archived by WebCite<sup>®</sup> at http://www.webcitation.org/60Rtn1IBG)

## Appendices

### Appendix A - Entry questionnaire

**Background information**

1\. What undergraduate or graduate degree(s) have you earned or do you expect to earn? Please list as many as applicable and the subject major associated with each degree.

_________________________________________________  
Degree Major  
_________________________________________________  
Degree Major  
_________________________________________________  
Degree Major  
_________________________________________________  
Degree Major

2\. What is your gender?

*   Female
*   Male

3\. What is your occupation?  
__________________________________

4\. What is your age?

*   Over 50 year old
*   40-49
*   30-39
*   20-29
*   Below 20

**Computer and searching experience**

How often do you use computer in your daily life?

<table border="1" cellspacing="0" cellpadding="0" width="649">

<tbody>

<tr>

<td align="center" colspan="3">**_Never_**</td>

<td align="center" colspan="3">**_Monthly_**</td>

<td align="center">**_Daily_**</td>

</tr>

<tr>

<td align="center">_1_</td>

<td align="center">_2_</td>

<td align="center">_3_</td>

<td align="center">_4_</td>

<td align="center">_5_</td>

<td align="center">_6_</td>

<td align="center">_7_</td>

</tr>

</tbody>

</table>

2\. How do you rate your level of expertise with computers?

<table border="1" cellspacing="0" cellpadding="0" width="649">

<tbody>

<tr>

<td>**_Novice_**</td>

<td> </td>

<td> </td>

<td> </td>

<td> </td>

<td> </td>

<td>**_Expert_**</td>

</tr>

<tr>

<td align="center">_1_</td>

<td align="center">_2_</td>

<td align="center">_3_</td>

<td align="center">_4_</td>

<td align="center">_5_</td>

<td align="center">_6_</td>

<td align="center">_7_</td>

</tr>

</tbody>

</table>

3\. Please circle the number that most closely describes your searching experience.

<table border="1" cellspacing="0" cellpadding="0" width="649">

<tbody>

<tr>

<td width="44%">**How much experience have you had searching for information using...**</td>

<td width="8%" align="center">**_None_**</td>

<td width="8%"> </td>

<td width="8%"> </td>

<td width="8%" align="center">**_Some_**</td>

<td width="8%"> </td>

<td width="8%"> </td>

<td width="8%" align="center">**_A great deal_**</td>

</tr>

<tr>

<td>a. computerized library catalogs either locally (e.g., your library) or remotely (e.g., Library of Congress)</td>

<td align="center">_1_</td>

<td align="center">_2_</td>

<td align="center">_3_</td>

<td align="center">_4_</td>

<td align="center">_5_</td>

<td align="center">_6_</td>

<td align="center">_7_</td>

</tr>

<tr>

<td>b. commercial online systems and databases (e.g., Dialog, Lexis-Nexis)</td>

<td align="center">_1_</td>

<td align="center">_2_</td>

<td align="center">_3_</td>

<td align="center">_4_</td>

<td align="center">_5_</td>

<td align="center">_6_</td>

<td align="center">_7_</td>

</tr>

<tr>

<td>c. World Wide Web search engines (e.g., Google, Yahoo!)</td>

<td align="center">_1_</td>

<td align="center">_2_</td>

<td align="center">_3_</td>

<td align="center">_4_</td>

<td align="center">_5_</td>

<td align="center">_6_</td>

<td align="center">_7_</td>

</tr>

<tr>

<td>d. CiteSpace or other systems for visualizing literatures/domains</td>

<td align="center">_1_</td>

<td align="center">_2_</td>

<td align="center">_3_</td>

<td align="center">_4_</td>

<td align="center">_5_</td>

<td align="center">_6_</td>

<td align="center">_7_</td>

</tr>

<tr>

<td>e. ISI Web of Science system</td>

<td align="center">_1_</td>

<td align="center">_2_</td>

<td align="center">_3_</td>

<td align="center">_4_</td>

<td align="center">_5_</td>

<td align="center">_6_</td>

<td align="center">_7_</td>

</tr>

<tr>

<td>f. other systems (please specify):  
_______________________________</td>

<td align="center">_1_</td>

<td align="center">_2_</td>

<td align="center">_3_</td>

<td align="center">_4_</td>

<td align="center">_5_</td>

<td align="center">_6_</td>

<td align="center">_7_</td>

</tr>

</tbody>

</table>

<table border="1" cellspacing="0" cellpadding="0" width="649">

<tbody>

<tr>

<td width="271" rowspan="2" valign="top">g. How often do you conduct a search (on any kind of system)?</td>

<td width="60" valign="bottom">**_Never_**</td>

<td width="48" valign="bottom"> </td>

<td width="48" valign="bottom"> </td>

<td width="72" valign="bottom">**_Monthly_**</td>

<td width="48" valign="bottom"> </td>

<td width="48" valign="bottom"> </td>

<td width="54" valign="bottom">**_Daily_**</td>

</tr>

<tr>

<td align="center">_1_</td>

<td align="center">_2_</td>

<td align="center">_3_</td>

<td align="center">_4_</td>

<td align="center">_5_</td>

<td align="center">_6_</td>

<td align="center">_7_</td>

</tr>

</tbody>

</table>

<table border="1" cellspacing="0" cellpadding="0" width="649">

<tbody>

<tr>

<td width="271" rowspan="2" valign="top">h. When you search for information, you can usually find what you are looking for.</td>

<td width="60" valign="bottom">**_Rarely_**</td>

<td width="48" valign="bottom"> </td>

<td width="48" valign="bottom"> </td>

<td width="72" valign="bottom">**_Sometimes_**</td>

<td width="48" valign="bottom"> </td>

<td width="48" valign="bottom"> </td>

<td width="54" valign="bottom">**_Often_**</td>

</tr>

<tr>

<td align="center">_1_</td>

<td align="center">_2_</td>

<td align="center">_3_</td>

<td align="center">_4_</td>

<td align="center">_5_</td>

<td align="center">_6_</td>

<td align="center">_7_</td>

</tr>

</tbody>

</table>

4\. How do you rate your level of expertise in searching for information?

<table border="1" cellspacing="0" cellpadding="0" width="649">

<tbody>

<tr>

<td width="97" valign="bottom">**_Novice_**</td>

<td> </td>

<td> </td>

<td> </td>

<td> </td>

<td> </td>

<td>**_Expert_**</td>

</tr>

<tr>

<td align="center">_1_</td>

<td align="center">_2_</td>

<td align="center">_3_</td>

<td align="center">_4_</td>

<td align="center">_5_</td>

<td align="center">_6_</td>

<td align="center">_7_</td>

</tr>

</tbody>

</table>

5\. How many years have you been doing online searching? ______ years.

6\. Please list your favorite search engine(s): ________________________.

7\. Please list the operating systems (e.g., Windows) and software packages (e.g., Microsoft Office) you frequently use: __________________________________________________________________________.

### Appendix B - Pre-task Questionnaire

Scenario: As a graduate student, you want to write a paper about research on life on Mars. You are interested in how research has been done and what research has played an important role in this area during the past several years.

Task: You need to collect some papers for the literature review. You know that some papers published by Edwards HGM would be very helpful. Please find the author who has the most collaboration with Edwards HGM, then put your answer on the answer sheet.

1\. Please indicate how familiar you are with the topic of this task:

<table border="1" cellspacing="0" cellpadding="0">

<tbody>

<tr>

<td width="80" valign="top">**_Not at all_**</td>

<td width="80" valign="top"> </td>

<td width="80" valign="top"> </td>

<td width="91" valign="top">**_Somewhat_**</td>

<td width="72" valign="top"> </td>

<td width="84" valign="top"> </td>

<td width="84" valign="top">**_Extremely_**</td>

</tr>

<tr>

<td align="center">_1_</td>

<td align="center">_2_</td>

<td align="center">_3_</td>

<td align="center">_4_</td>

<td align="center">_5_</td>

<td align="center">_6_</td>

<td align="center">_7_</td>

</tr>

</tbody>

</table>

2\. Please indicate your level of expertise with the topic of this task:

<table border="1" cellspacing="0" cellpadding="0">

<tbody>

<tr>

<td width="82" valign="top">**_Novice_**</td>

<td width="82" valign="top"> </td>

<td width="82" valign="top"> </td>

<td width="86" valign="top"> </td>

<td width="72" valign="top"> </td>

<td width="84" valign="top"> </td>

<td width="84" valign="top">**_Extremely_**</td>

</tr>

<tr>

<td align="center">_1_</td>

<td align="center">_2_</td>

<td align="center">_3_</td>

<td align="center">_4_</td>

<td align="center">_5_</td>

<td align="center">_6_</td>

<td align="center">_7_</td>

</tr>

</tbody>

</table>

3\. If you think that you know any authors, please write them in the space below:

If you have answered this question, please circle the number that indicates how certain you are of the answer.

<table border="1" cellspacing="0" cellpadding="0" align="left">

<tbody>

<tr>

<td width="91" valign="top">**_Extremely uncertain_**</td>

<td width="73" valign="top"> </td>

<td width="82" valign="top"> </td>

<td width="82" valign="top">**_Neutral_**</td>

<td width="82" valign="top"> </td>

<td width="82" valign="top"> </td>

<td width="92" valign="top">**_Extremely certain_**</td>

</tr>

<tr>

<td align="center">_1_</td>

<td align="center">_2_</td>

<td align="center">_3_</td>

<td align="center">_4_</td>

<td align="center">_5_</td>

<td align="center">_6_</td>

<td align="center">_7_</td>

</tr>

</tbody>

</table>

### Appendix C - Post-task Questionnaire

Please answer the following questions, as they relate to this specific task.

<table border="1" cellspacing="0" cellpadding="0" width="589">

<tbody>

<tr>

<td width="181" valign="top"> </td>

<td width="55" valign="top">**_Not at all_**</td>

<td width="51" valign="top"> </td>

<td width="50" valign="top"> </td>

<td width="60" valign="top">**_Somewhat_**</td>

<td width="54" valign="top"> </td>

<td width="54" valign="top"> </td>

<td width="84" valign="top">**_Extremely_**</td>

</tr>

<tr>

<td width="181" valign="top">

1\. Was it easy to get started on this task?

</td>

<td align="center">_1_</td>

<td align="center">_2_</td>

<td align="center">_3_</td>

<td align="center">_4_</td>

<td align="center">_5_</td>

<td align="center">_6_</td>

<td align="center">_7_</td>

</tr>

<tr>

<td width="181" valign="top">2\. Was it easy to complete the task?</td>

<td align="center">_1_</td>

<td align="center">_2_</td>

<td align="center">_3_</td>

<td align="center">_4_</td>

<td align="center">_5_</td>

<td align="center">_6_</td>

<td align="center">_7_</td>

</tr>

<tr>

<td width="181" valign="top">3\. Was it easy to understand the system?</td>

<td align="center">_1_</td>

<td align="center">_2_</td>

<td align="center">_3_</td>

<td align="center">_4_</td>

<td align="center">_5_</td>

<td align="center">_6_</td>

<td align="center">_7_</td>

</tr>

<tr>

<td width="181" valign="top">4\. Are you satisfied with your results?</td>

<td align="center">_1_</td>

<td align="center">_2_</td>

<td align="center">_3_</td>

<td align="center">_4_</td>

<td align="center">_5_</td>

<td align="center">_6_</td>

<td align="center">_7_</td>

</tr>

<tr>

<td width="181" valign="top">5\. Did you have enough time to complete the task?</td>

<td align="center">_1_</td>

<td align="center">_2_</td>

<td align="center">_3_</td>

<td align="center">_4_</td>

<td align="center">_5_</td>

<td align="center">_6_</td>

<td align="center">_7_</td>

</tr>

<tr>

<td width="181" valign="top">6\. How confident were you with your results?</td>

<td align="center">_1_</td>

<td align="center">_2_</td>

<td align="center">_3_</td>

<td align="center">_4_</td>

<td align="center">_5_</td>

<td align="center">_6_</td>

<td align="center">_7_</td>

</tr>

</tbody>

</table>

<table border="1" cellspacing="0" cellpadding="0" width="589">

<tbody>

<tr>

<td width="181" valign="top"> </td>

<td width="55">**_None_**</td>

<td width="51"> </td>

<td width="50"> </td>

<td width="60">**_Some_**</td>

<td width="54"> </td>

<td width="54"> </td>

<td width="84">**_A great deal_**</td>

</tr>

<tr>

<td width="181" valign="top">7\. How much information about the topic of this task has been conveyed to you by the system?</td>

<td align="center">_1_</td>

<td align="center">_2_</td>

<td align="center">_3_</td>

<td align="center">_4_</td>

<td align="center">_5_</td>

<td align="center">_6_</td>

<td align="center">_7_</td>

</tr>

<tr>

<td width="181" valign="top">8\. Did your previous knowledge of the topic of this task help you?</td>

<td align="center">_1_</td>

<td align="center">_2_</td>

<td align="center">_3_</td>

<td align="center">_4_</td>

<td align="center">_5_</td>

<td align="center">_6_</td>

<td align="center">_7_</td>

</tr>

<tr>

<td width="181" valign="top">9\. Have you learned anything new about the topic of this task?</td>

<td align="center">_1_</td>

<td align="center">_2_</td>

<td align="center">_3_</td>

<td align="center">_4_</td>

<td align="center">_5_</td>

<td align="center">_6_</td>

<td align="center">_7_</td>

</tr>

<tr>

<td width="181" valign="top">10\. How much effort did you take to fully understand how to do the task?</td>

<td align="center">_1_</td>

<td align="center">_2_</td>

<td align="center">_3_</td>

<td align="center">_4_</td>

<td align="center">_5_</td>

<td align="center">_6_</td>

<td align="center">_7_</td>

</tr>

</tbody>

</table>

### Appendix D - Exit questionnaire

To gain a better understanding of your overall experience, we would like to ask you a few questions about your experience today.

<table border="1" cellspacing="0" cellpadding="0" width="595">

<tbody>

<tr>

<td width="175" valign="top"> </td>

<td width="55" valign="top">**_Not at all_**</td>

<td width="51" valign="top"> </td>

<td width="51" valign="top"> </td>

<td width="60" valign="top">**_Somewhat_**</td>

<td width="60" valign="top"> </td>

<td width="60" valign="top"> </td>

<td width="84" valign="top">**_Extremely_**</td>

</tr>

<tr>

<td width="175" valign="top">1\. How easy was it to LEARN to USE this information system?</td>

<td align="center">_1_</td>

<td align="center">_2_</td>

<td align="center">_3_</td>

<td align="center">_4_</td>

<td align="center">_5_</td>

<td align="center">_6_</td>

<td align="center">_7_</td>

</tr>

<tr>

<td width="175" valign="top">2\. How easy was it to LEARN to USE the resulting graph?</td>

<td align="center">_1_</td>

<td align="center">_2_</td>

<td align="center">_3_</td>

<td align="center">_4_</td>

<td align="center">_5_</td>

<td align="center">_6_</td>

<td align="center">_7_</td>

</tr>

<tr>

<td width="175" valign="top">3\. How easy was it to use this information system in general?</td>

<td align="center">_1_</td>

<td align="center">_2_</td>

<td align="center">_3_</td>

<td align="center">_4_</td>

<td align="center">_5_</td>

<td align="center">_6_</td>

<td align="center">_7_</td>

</tr>

<tr>

<td width="175" valign="top">4\. How easy was it to use the resulting graph?</td>

<td align="center">_1_</td>

<td align="center">_2_</td>

<td align="center">_3_</td>

<td align="center">_4_</td>

<td align="center">_5_</td>

<td align="center">_6_</td>

<td align="center">_7_</td>

</tr>

<tr>

<td width="175" valign="top">5\. How well did you understand this information system?</td>

<td align="center">_1_</td>

<td align="center">_2_</td>

<td align="center">_3_</td>

<td align="center">_4_</td>

<td align="center">_5_</td>

<td align="center">_6_</td>

<td align="center">_7_</td>

</tr>

<tr>

<td width="175" valign="top">6\. How well did you understand the resulting graph?</td>

<td align="center">_1_</td>

<td align="center">_2_</td>

<td align="center">_3_</td>

<td align="center">_4_</td>

<td align="center">_5_</td>

<td align="center">_6_</td>

<td align="center">_7_</td>

</tr>

<tr>

<td width="175" valign="top">7\. How helpful was this system in accomplishing your tasks?</td>

<td align="center">_1_</td>

<td align="center">_2_</td>

<td align="center">_3_</td>

<td align="center">_4_</td>

<td align="center">_5_</td>

<td align="center">_6_</td>

<td align="center">_7_</td>

</tr>

<tr>

<td width="175" valign="top">8\. Did you like the system?</td>

<td align="center">_1_</td>

<td align="center">_2_</td>

<td align="center">_3_</td>

<td align="center">_4_</td>

<td align="center">_5_</td>

<td align="center">_6_</td>

<td align="center">_7_</td>

</tr>

<tr>

<td width="175" valign="top">9\. Did you feel lost when going through the system and performing assigned tasks?</td>

<td align="center">_1_</td>

<td align="center">_2_</td>

<td align="center">_3_</td>

<td align="center">_4_</td>

<td align="center">_5_</td>

<td align="center">_6_</td>

<td align="center">_7_</td>

</tr>

<tr>

<td width="175" valign="top">10\. How did you like the system's resulting graph?</td>

<td align="center">_1_</td>

<td align="center">_2_</td>

<td align="center">_3_</td>

<td align="center">_4_</td>

<td align="center">_5_</td>

<td align="center">_6_</td>

<td align="center">_7_</td>

</tr>

<tr>

<td width="175" valign="top">11\. How appropriate was the resulting graph?</td>

<td align="center">_1_</td>

<td align="center">_2_</td>

<td align="center">_3_</td>

<td align="center">_4_</td>

<td align="center">_5_</td>

<td align="center">_6_</td>

<td align="center">_7_</td>

</tr>

<tr>

<td width="175" valign="top">12\. How well did labels represent the given concept, or tasks?</td>

<td align="center">_1_</td>

<td align="center">_2_</td>

<td align="center">_3_</td>

<td align="center">_4_</td>

<td align="center">_5_</td>

<td align="center">_6_</td>

<td align="center">_7_</td>

</tr>

<tr>

<td width="175" valign="top">13\. How well did the navigational features (e.g., menus, panels, help) support you in completing the tasks?</td>

<td align="center">_1_</td>

<td align="center">_2_</td>

<td align="center">_3_</td>

<td align="center">_4_</td>

<td align="center">_5_</td>

<td align="center">_6_</td>

<td align="center">_7_</td>

</tr>

</tbody>

</table>

<table border="1" cellspacing="0" cellpadding="0" width="589">

<tbody>

<tr>

<td width="181" valign="top"> </td>

<td width="55">**_None_**</td>

<td width="51"> </td>

<td width="50"> </td>

<td width="60">**_Some_**</td>

<td width="54"> </td>

<td width="54"> </td>

<td width="84">**_A great deal_**</td>

</tr>

<tr>

<td width="181" valign="top">14\. How clearly did you perceive the purposes and various functions of the system?</td>

<td align="center">_1_</td>

<td align="center">_2_</td>

<td align="center">_3_</td>

<td align="center">_4_</td>

<td align="center">_5_</td>

<td align="center">_6_</td>

<td align="center">_7_</td>

</tr>

<tr>

<td width="181" valign="top">15\. How satisfied were you with the system, including the navigation features and the resulting graph display?</td>

<td align="center">_1_</td>

<td align="center">_2_</td>

<td align="center">_3_</td>

<td align="center">_4_</td>

<td align="center">_5_</td>

<td align="center">_6_</td>

<td align="center">_7_</td>

</tr>

</tbody>

</table>

<table border="1" cellspacing="0" cellpadding="0" width="589">

<tbody>

<tr>

<td width="181" valign="top"> </td>

<td width="78">**_Strongly Disagree_**</td>

<td width="36"> </td>

<td width="42"> </td>

<td width="72">**_Partly_**</td>

<td width="54"> </td>

<td width="42"> </td>

<td width="84">**_Strongly agree_**</td>

</tr>

<tr>

<td width="181" valign="top">16\. Using this system was a very frustrating experience.</td>

<td align="center">_1_</td>

<td align="center">_2_</td>

<td align="center">_3_</td>

<td align="center">_4_</td>

<td align="center">_5_</td>

<td align="center">_6_</td>

<td align="center">_7_</td>

</tr>

<tr>

<td width="181" valign="top">

17\. I feel that this system allows me to achieve very high productivity.

</td>

<td align="center">_1_</td>

<td align="center">_2_</td>

<td align="center">_3_</td>

<td align="center">_4_</td>

<td align="center">_5_</td>

<td align="center">_6_</td>

<td align="center">_7_</td>

</tr>

<tr>

<td width="181" valign="top">18\. I worry that many of the things I did with this system may have been wrong.</td>

<td align="center">_1_</td>

<td align="center">_2_</td>

<td align="center">_3_</td>

<td align="center">_4_</td>

<td align="center">_5_</td>

<td align="center">_6_</td>

<td align="center">_7_</td>

</tr>

<tr>

<td width="181" valign="top">

19\. This system can do all the things I think I would need.

</td>

<td align="center">_1_</td>

<td align="center">_2_</td>

<td align="center">_3_</td>

<td align="center">_4_</td>

<td align="center">_5_</td>

<td align="center">_6_</td>

<td align="center">_7_</td>

</tr>

<tr>

<td width="181" valign="top">20\. This system is very pleasant to work with.</td>

<td align="center">_1_</td>

<td align="center">_2_</td>

<td align="center">_3_</td>

<td align="center">_4_</td>

<td align="center">_5_</td>

<td align="center">_6_</td>

<td align="center">_7_</td>

</tr>

<tr>

<td width="181" valign="top">21\. I found the system unnecessarily complex.</td>

<td align="center">_1_</td>

<td align="center">_2_</td>

<td align="center">_3_</td>

<td align="center">_4_</td>

<td align="center">_5_</td>

<td align="center">_6_</td>

<td align="center">_7_</td>

</tr>

<tr>

<td width="181" valign="top">22\. I think that I would need the support of a technical person to be able to use this system.</td>

<td align="center">_1_</td>

<td align="center">_2_</td>

<td align="center">_3_</td>

<td align="center">_4_</td>

<td align="center">_5_</td>

<td align="center">_6_</td>

<td align="center">_7_</td>

</tr>

<tr>

<td width="181" valign="top">

23\. I found the various functions in this system well integrated.

</td>

<td align="center">_1_</td>

<td align="center">_2_</td>

<td align="center">_3_</td>

<td align="center">_4_</td>

<td align="center">_5_</td>

<td align="center">_6_</td>

<td align="center">_7_</td>

</tr>

<tr>

<td width="181" valign="top">24\. I will use this system more in the future.</td>

<td align="center">_1_</td>

<td align="center">_2_</td>

<td align="center">_3_</td>

<td align="center">_4_</td>

<td align="center">_5_</td>

<td align="center">_6_</td>

<td align="center">_7_</td>

</tr>

<tr>

<td width="181" valign="top">25\. I will recommend this system to others.</td>

<td align="center">_1_</td>

<td align="center">_2_</td>

<td align="center">_3_</td>

<td align="center">_4_</td>

<td align="center">_5_</td>

<td align="center">_6_</td>

<td align="center">_7_</td>

</tr>

<tr>

<td width="181" valign="top">26\. Overall, the system was effective in helping me complete the tasks.</td>

<td align="center">_1_</td>

<td align="center">_2_</td>

<td align="center">_3_</td>

<td align="center">_4_</td>

<td align="center">_5_</td>

<td align="center">_6_</td>

<td align="center">_7_</td>

</tr>

</tbody>

</table>

27\. What system features did you like most? Why?

28\. What system features did you dislike most? Why?

29\. What other features, that are currently unavailable, would you suggest be added to the system? Why?

30\. Do you have any comments or suggestions about the display of resulting graph? Are there points that should be improved?

31\. Do you have any additional comments or suggestions?