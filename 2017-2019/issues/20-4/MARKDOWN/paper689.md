#### vol. 20 no. 4, December, 2015

# Searching databases without query-building aids: implications for dyslexic users

#### [Gerd Berget](#author)  
Institute of Information Technology, Faculty of Technology, Art and Design, Oslo and Akershus University College of Applied Sciences, Oslo, Norway  
[Frode Eika Sandnes](#author)  
Faculty of Technology, Westerdals Oslo School of Arts, Communication and Technology. Oslo, Norway

#### Abstract

> **Introduction.** Few studies document the information searching behaviour of users with cognitive impairments. This paper therefore addresses the effect of dyslexia on information searching in a database with no tolerance for spelling errors and no query-building aids. The purpose was to identify effective search interface design guidelines that benefit dyslexic users.  
> **Method.** Twenty dyslexic students and twenty controls solved ten predefined search tasks in the Norwegian library catalogue Bibsys Ask. Screen-recording and eye-tracking were used to observe search behaviour.  
> **Analysis.** The statistical analysis software SPSS was used for quantitative analyses, SMI BeGaze was used for qualitative analysis of the search behaviour.  
> **Results.** Dyslexic students took longer and formulated more queries per task than the controls. Further, they submitted shorter queries, made more misspellings and relied more upon external resources. There were no differences in problem solving approaches across the two groups except that the dyslexic students used external Websites more.  
> **Conclusions.** The results of this study indicate that dyslexia has a negative impact on search performance in systems with no tolerance for errors and no query-building aids. Several guidelines are suggested based on the observed information searching behaviour to accommodate users with dyslexia.

## Introduction

Online databases are important sources for scholarly information. There is a growing reliance among students on search engines such as Google ([Jamali and Asadi, 2010](#jam10)). General search engines often have basic search interfaces as the default option, where the user inputs all the search terms in one search field. Further, these systems often offer full text search, allowing the users to search with natural language. Search engines may also have a high tolerance for spelling errors and offer various query-building aids. Autocomplete is an example of a query-building aid where query-terms are suggested while the user is entering the query. Query-building aids may also return relevant results even if queries are misspelled.

General search engines do not fully accommodate the needs of students and scholars. Additional resources such as library catalogues and article databases are often required to locate articles on reading lists and to find relevant citations for written assignments. Domain specific search systems often contain advanced interfaces with several search fields, which require different content such as author names, titles or keywords. Moreover, these databases do often not offer full text search. Although a database may provide synonym control, there are higher demands on users to input query terms matching the vocabulary of the database. Bibliographic databases often have a low or no tolerance for spelling errors and offer no query-building aids. Such systems require well-developed writing and reading skills, which are typically impaired in dyslexic users. It is suggested that students with impairments such as dyslexia struggle with information seeking ([Hepworth, 2007](#hep07); ["MacFarlane, Al-Wabil, Marshall, Albrair, Jones and Zaphiris, 2010](#mac10); [MacFarlane, Albrair, Marshall, and Buchanan, 2012](#mac12); [Habib _et al._, 2012](#hab12)). Dyslexics may also have difficulties in using physical libraries, and thus rely on extra library support ([Mortimore and Crozier, 2006](#mor06)).

The number of dyslexic students entering higher education is increasing ([Tops, Callens, Lammertyn, Van Hees and Brysbaert, 2012](#top12)). Information literacy is often emphasised as a strategy for lifelong learning ([Association of College and Research Libraries, 2000](#ass00)) and access to scholarly literature is important to this end. Inaccessible search systems may be an obstacle in completing a higher education qualification for dyslexic students. Consequently, there is a need for more accessible search systems, but to date little is known about the information searching behaviour of dyslexic users in order to facilitate these more accessible search systems ([Hepworth, 2007](#hep07); [MacFarlane _et al._, 2012](#mac12)). The novel contribution of this study is to provide new empirical evidence on how dyslexia affects information search. For example, do dyslexic students take longer and formulate more queries per task than the students without dyslexia, do dyslexics submit shorter queries, make more misspellings and rely more on external resources than users without dyslexia. Such empirical knowledge is needed to develop design guidelines which better accommodate search experiences for dyslexic users.

This study involved forty students (twenty with dyslexia and twenty controls) who each solved ten predefined search tasks in the Web-based Norwegian library catalogue [Bibsys Ask](http://ask.bibsys.no/ask/action/resources?lang=en). The null hypothesis herein was that dyslexia would not affect overall search performance. It was expected that several search parameters would be affected by dyslexia, which typically causes spelling and reading difficulties ([Snowling, 2000](#sno00)). It was assumed that spelling skills would affect the time taken to pursue a query, the number of queries needed to solve a task, query lengths and portion of misspellings. Further, reading skills could affect query lengths, since it was assumed that slow readers would formulate queries with a higher precision level to reduce the effort needed to browse result lists. It was also assumed that a broad range of problem-solving approaches would be applied. The following hypotheses were the basis for the study:

> **H1:** Dyslexic users take more time formulating queries than controls.  
> **H2:** Dyslexic users formulate more queries per task than controls.  
> **H3:** Dyslexic users submit shorter queries than controls.  
> **H4:** Dyslexic users produce more misspellings than controls.  
> **H5:** Dyslexic users apply a broader range of problem solving strategies than controls.

## Background

Dyslexia is a learning disorder which affects 3-10% of the general population ([Snowling, 2000](#sno00)). Although the etiology is disputed ([Jones, Branigan and Kelly, 2007](#jon07); [Schuchardt, Maehler and Hasselhorn, 2008](#sch08)), dyslexia is commonly connected to an underlying phonological deficit ([Snowling, 2001](#sno01)). Dyslexia typically affects reading and writing activities however impairments in word retrieval, working memory, concentration and rapid naming skills are also prevailing ([Snowling, 2000](#sno00); [Snowling, 2001](#sno01); [Mortimore and Crozier, 2006](#mor06); [Smith-Spark and Fisk, 2007](#smi07)). Rapid naming skills concern the ability to connect visual and oral information by assigning appropriate names to, for instance, numbers, colours or objects ([Lervåg and Hulme, 2009](#ler09)). Difficulties related to dyslexia persist until adulthood and remain throughout life ([Swanson and Hsieh, 2009](#swa09)).

Information searching involves a variety of cognitive skills. For instance, rapid naming skills and word retrieval are used to formulate effective search queries. Spelling skills are needed to input terms correctly ([MacFarlane, Albrair, Marshall, and Buchanan, 2012](#mac12)). Reading skills and a good working memory are required when browsing result lists and assessing documents. Several of these skills are often impaired in dyslexic users. Consequently, dyslexia may have a negative effect on search performance, especially in systems with no query-building aids and no tolerance for spelling errors.

The field of human computer interaction has become increasingly concerned with user diversity and the importance of accessible interfaces ([Henry, Abou-Zahra and Brewer, 2014](#hen14)). Universal design is included in several national legislations ([Imrie, 2012](#imr12)). The Web Content Accessibility Guidelines (WCAG) is often referred to in this context. However, these guidelines may not meet the needs of users with various disabilities ([Rømen and Svanæs, 2012](#rom12)) or users in cognitive language and learning areas ([W3C, 2008](#w3c08)) such as dyslexia ([Freire, Petrie and Power, 2011](#fre11); [deSantana, Oliveira, Almeida and Baranauskas, 2012](#des12)). Further, existing guidelines typically address general Website design, and not specific issues related to search systems.

More knowledge about user behaviour is needed to develop effective interface guidelines. Dyslexics have received little attention in studies on Web accessibility and search systems ([de Santana, Oliveira, Almeida and Baranauskas, 2012](#des12); [McCarthy & Swierenga, 2010](#mcc10)). Furthermore, most research on dyslexia and Website design address navigation ([Al-Wabil, Zaphiris and Wilson, 2007](#alw07)), font types, font sizes ([Rello and Baeza-Yates, 2013](#rel13a); [Rello, Pielot, Marcos and Carlini, 2013](#rel13b)) and accessible textual content ([Evett and Brown, 2005](#eve05)). Consequently, few documented studies exist about information retrieval and the actual use of search interfaces by dyslexic users.

General user-centred theories and models on information seeking behaviour do generally not address users with impairments. Some studies address blind library users, for instance Craven & Brophy ([2003](#cra03)) and Sahib, Tombros and Stockman ([2012](#sah12)), while cognitive disabilities have received less attention ([MacFarlane, Al-Wabil, Marshall, Albrair, Jones and Zaphiris, 2010](#mac10)). Of the few studies that addressed general cognitive abilities as possible predictors of information searching Kim and Allen ([2002](#kim02)) investigated whether cognitive abilities such as different levels of perceptual speed, spatial scanning and logical reasoning affected the information seeking behaviour of students searching the Web. Other studies discuss how cognitive style or learning style affects the retrieval process, for instance Palmquist and Kim ([2000](#pal00)), Papaeconomou, Zijlema and Ingwersen ([2008](#pap08)) and Al-Maskari and Sanderson ([2011](#alm11)).

Of the few studies that addressed how dyslexia affects information searching behaviour MacFarlane et al. ([2010](#mac10)) compared the search behaviour of 5 dyslexics and 5 controls in the test retrieval system Okapi. The results from this study were that dyslexic users on average exhibited fewer search iterations, took more time on each search and reviewed fewer documents than the controls. The authors found no misspellings and could therefore not explain how such mistakes affect query variables. A later study by MacFarlane et al. ([2012](#mac12)) investigated the search behaviour of 8 dyslexics and 8 controls with a focus on the phonological working memory. The phonological working memory includes spoken and written material and is often impaired in users with dyslexia ([Smith-Spark and Fisk, 2007](#smi07)). Participants in the control group classified more documents as irrelevant than the dyslexia group. Furthermore, the authors found a correlation between working memory and the ratio of documents classified as irrelevant. The conclusion was that there is a need for more knowledge on the information searching behaviour of users with dyslexia.

Berget and Sandnes ([2015](#ber15)) observed the information searching behaviour of 20 dyslexics and 20 controls solving ten predefined search tasks in the general search engine Google with query building aids. Although the dyslexics made more misspellings, there were no significant differences in time usage or number of queries per task compared to controls. The dyslexic students fixated significantly less on the screen and the autocomplete suggestions while entering queries than the controls. Berget and Sandnes ([2015](#ber15)) concluded that a high tolerance for spelling errors may be as useful as autocomplete functions for dyslexic users, because of the extensive focus on the keyboard during text entry. Results from this study also indicate that help functions such as displaying a red line beneath misspelled words in the search field, may be helpful to users.

## Method

### Participants

The study included 40 volunteering students, 20 diagnosed with dyslexia and 20 controls. The participants were recruited through advertisements by the interest association Dyslexia Norway, announcements in classrooms and on Websites. Four of the participants (three dyslexics and one control) were diagnosed with Attention Deficit Hyperactivity Disorder (ADHD) or Attention Deficit Disorder (ADD). ADHD and ADD are typically characterized by short attention span, excessive activity and impulsivity, and comorbidity with dyslexia is well documented ([Germanò, Gagliano, and Curatolo, 2010](#ger10)). Participants in the control group were matched against the dyslexia group according to gender, age, field of study and year of study. Prevalence of dyslexia was the only controlled variable.

The participants included 60% females and 40% males, aged 19-40 years with a mean age of 24.2 years (_SD_=5.2) in the dyslexia group and 23.6 (_SD_=3.8) in the control group. Dyslexia is typically more prevalent among men than women ([Hawke, Olson, Willcut, Wadsworth and DeFries, 2009](#haw09)). Consequently, the portion of male participants should have been higher. However, the skewed gender distribution was caused by recruiting difficulties.

The students were enrolled onto either three-year bachelor-programmes or two-year master-programmes, with mean year of study of 2.4, for both the dyslexia group (_SD_=1.2) and the control group (_SD_=1.0) (value 1-3 used for bachelor students, 4-5 for master students). The participants represented a diversity of disciplines and study programmes, for instance nursing, engineering, social sciences and humanities. Students from library- and information science programmes were excluded because of their extensive training in information searching. None of the dyslexic students regularly relied on assistive technologies. All participants were regarded as high-functioning dyslexics since they successfully have been admitted to higher degree programmes and have demonstrated academic progress. This may be a limitation of the study, since other groups with dyslexia may have less academic training.

Formal training and prior experience with search systems may affect information searching ([Kuhlthau, 1991](#kuh91)). Eight dyslexic participants had received formal training in searching library catalogues compared to nine users in the control group. The controls had slightly more years of experience than the dyslexics, both in using general search engines (_M_=14.4, _SD_=3.2 compared to _M_=13.9, _SD_=3.3) and library catalogues (_M_=4.6, _SD_=3.9 compared to _M_=3.9, _SD_=3.1). The students with dyslexia reported a higher frequency of use of the library catalogues than the control group.

All participants were screened for dyslexia using a word chain test ([Høien & Tønnesen, 2008](#hoi08)). The dyslexic students had previously been diagnosed by psychological or pedagogical professionals. However, the screening test eliminated the need for consulting sensitive medical records to confirm the dyslexia diagnosis and ensured that no controls were dyslexic. The word chain test is a standardised test in Norway which is applied in previous research, for instance Solheim and Uppstad ([2011](#sol11)) and Dahle and Knivsberg ([2014](#dah14)). A low score is considered indicative of dyslexia and diagnostic tests are recommended for adult scores below 43 ([Høien & Tønnesen, 2008](#hoi08)). The dyslexic students scored significantly lower (_M_=39.3, _SD_=10.3) than the controls (_M_=60.2, _SD_=10.0), _t_(38)=6.52, _p_<.001, _d_=2.12.

Visual acuity was measured, since reduced vision can be a source of error. Landolt C charts were used at 4 m for distance and 40 cm for near, in accordance with the European standard ([ISO, 2009](#iso09)). All participants had at least acuity of 0.6 on each eye separately and 0.8 with both eyes open for both tests, which is considered within the limits of normal visual acuity ([Zhang, Bobier, Thompson and Hess, 2011](#zha11)).

### Procedure

The participants were instructed to solve ten predefined search tasks using the library catalogue. Instructions and search tasks were presented orally using pre-recorded speech synthesis files. Oral instructions may prevent misinterpretations of tasks, since dyslexia may affect reading speed and reading comprehension ([Ransby and Swanson, 2003](#ran03)). Moreover, oral instructions prevented the participants from seeing the spelling of terms. The experimental design choice of introducing oral instructions places more cognitive load on the participants since they have to remember the tasks. This could be a challenge since dyslexia is also often associated with reduced working memory. However, the task of reading the instructions was considered more cognitively demanding than memorising the short oral instructions. The assumed discrepancy between reading and listening abilities among individuals with reading disabilities is also supported by the literature ([Badian, 1999](#bad99)).

An image representing the question was displayed while instructions were given (Figure 1). The task number allowed the participants to track the progress of the session.

<figure class="centre">![Figure1: Example stimulus, task ten](p689fig1.jpg)

<figcaption>Figure 1: Example stimulus, task ten</figcaption>

</figure>

At the start of the session the participants were asked about prior experiences with online library catalogues including Bibsys Ask. All ten tasks were completed in one session, and there was no dialogue between the participants and the experimenter besides responses to questions initiated by the participants. The students were allowed to use external online resources as supplementary aids if needed e.g. checking the spelling of a word. They were asked to comment on their search behaviour during debriefing where unusual behaviour had been observed.

### Ethics

The study was ethically screened and approved by the Norwegian Social Science Data Services (project number 29348) and all data was anonymised. Moreover, all participants signed consent forms. None of the students were related to the researchers.

### Apparatus

The experiments were run in the visual stimulus presentation software SMI Experiment Center version 3.2.11 using the background screen recorder. The stimulus was displayed on a 21" Dell LED flat screen with the resolution set to 1680 x 1050 pixels. Windows Internet Explorer version 9 was used for the search tasks, with all functions related to prior use such as browsing history and cookies disabled. All searches were conducted in the basic search mode in Bibsys Ask (Figure 2). Data were analysed using SMI BeGaze version 3.2 and the statistical analysis software IBM SPSS Statistics 22.

<figure class="centre">![Figure2: Simple search mode in Bibsys Ask (http://ask.bibsys.no/ask/action/smpsearch), reproduced with permission. The Norwegian interface was used in the study.](p689fig2.jpg)

<figcaption>Figure 2: Simple search mode in Bibsys Ask ([http://ask.bibsys.no/ask/action/smpsearch](http://ask.bibsys.no/ask/action/smpsearch)), reproduced with permission. The Norwegian interface was used in the study.</figcaption>

</figure>

### Materials

Bibsys Ask is a bibliographic library database used by all the higher education libraries in Norway, in addition to several research libraries and institutions. This database has no tolerance for spelling errors and provides no query-building aids; the system merely instructs the user to check the spelling or modify the query if no results are returned (Figure 3).

<figure class="centre">![Figure 3: Instructions from Bibsys Ask when no results are returned, reproduced with permission](p689fig3.jpg)

<figcaption>Figure 3: Instructions from Bibsys Ask when no results are returned, reproduced with permission</figcaption>

</figure>

The participants were given ten predefined search tasks in Norwegian (see Table 1). Such tasks were used to allow for a direct comparison of search strategies and query formulations between the two groups. Imposed queries may be less motivating to solve than self-generated information needs ([Gross, 1995](#gro95)). It was assumed that the participants were motivated to solve the tasks since they had volunteered for the study. Experimental task orders are often randomized to counterbalance learning effects. In this study, however, the search tasks were presented in a fixed order. The students had prior experience with the search system and it was assumed that the learning-effects would be minimal. The key design consideration was not to make the participants feel uncomfortable or lose courage during the session because of the varying difficulty levels of the tasks and poor self-esteem issues among many dyslexic students ([Caroll and Iles, 2006](#car06)). Consequently, the tasks were presented in increasing order of difficulty.

<table class="center"><caption>  
Table 1: Search tasks and expected query terms  
</caption>

<tbody>

<tr>

<th>Task</th>

<th>Task (originally given in Norwegian)</th>

<th>Expected query terms</th>

<th>Translated query terms</th>

</tr>

<tr>

<td style="text-align:center">1</td>

<td style="text-align:left">Find a document about Vigeland Sculpture Park?</td>

<td style="text-align:left">Vigelandsparken</td>

<td style="text-align:left">Vigeland Sculpture Park</td>

</tr>

<tr>

<td style="text-align:center">2</td>

<td style="text-align:left">In which year was the book "Rock carvings in Hedmark and Oppland" published?</td>

<td style="text-align:lenter">helleristninger  
Hedmark  
Oppland  
</td>

<td style="text-align:left">rock carvings  
Hedmark  
Oppland</td>

</tr>

<tr>

<td style="text-align:center">3</td>

<td style="text-align:left">Find a book written by Sigrid Undset about Kristin?</td>

<td style="text-align:left">Sigrid  
Undset  
Kristin</td>

<td style="text-align:left">Sigrid  
Undset  
Kristin</td>

</tr>

<tr>

<td style="text-align:center">4</td>

<td style="text-align:left">Find a document on stagecraft and lighting?</td>

<td style="text-align:left">sceneteknikk  
lyssetting</td>

<td style="text-align:left">stagecraft  
lightning</td>

</tr>

<tr>

<td style="text-align:center">5</td>

<td style="text-align:left">Find a document on cyberbullying?</td>

<td style="text-align:left">digital  
mobbing</td>

<td style="text-align:left">cyberbullying</td>

</tr>

<tr>

<td style="text-align:center">6</td>

<td style="text-align:left">Who is the author of the books about Albert and Skybert?</td>

<td style="text-align:left">Albert  
Skybert</td>

<td style="text-align:left">Albert  
Skybert</td>

</tr>

<tr>

<td style="text-align:center">7</td>

<td style="text-align:left">Find a document about Norwegian recipients of the Nobel Peace Prize?</td>

<td style="text-align:left">norske  
vinnere  
Nobels  
fredspris</td>

<td style="text-align:left">Norwegian  
recipients  
Nobel  
Peace Prize</td>

</tr>

<tr>

<td style="text-align:center">8</td>

<td style="text-align:left">Find a book on Knut Hamsun and Nazism?</td>

<td style="text-align:left">Knut  
Hamsun  
Nazisme</td>

<td style="text-align:left">Knut  
Hamsun  
Nazism</td>

</tr>

<tr>

<td style="text-align:center">9</td>

<td style="text-align:left">Find a document about women in Algeria?</td>

<td style="text-align:left">kvinner  
Algerie</td>

<td style="text-align:left">women  
Algeria</td>

</tr>

<tr>

<td style="text-align:l">10</td>

<td style="text-align:left">Find a play written by William Shakespeare?</td>

<td style="text-align:left">William  
Shakespeare</td>

<td style="text-align:left">William  
Shakespeare</td>

</tr>

</tbody>

</table>

The search tasks were based on gender-neutral and common topics. They were not related to any particular study programmes, preventing prior knowledge to affect search behaviour. One correct answer was deemed sufficient to solve each task. The tasks were designed to provoke spelling errors allowing for a study of how search behaviour is affected by reduced spelling skills. The tasks included words which dyslexic users frequently misspell, such as compound words: fredspris, double consonants: Oppland, consonant clusters: Undset, silent consonants: Sigrid (d is not pronounced), silent vowels: Algerie (e is not pronounced) and words with irregular orthography, where the spelling and pronunciation differs: Shakespeare ([Helland and Kaasa, 2005](#hel05); [Lyster, 2007](#lys07); [Høien and Lundberg, 2012](#hoi12)). Although the search tasks represent a moderate complexity level, it was assumed that the tasks would be perceived most difficult for dyslexic users.

## Results

The query characteristics are summarised in Table 2\. Dyslexic students took significantly longer to complete each task (_M_=47.8 s, _SD_=14.6 s) compared to controls (_M_=29.0 s, _SD_=8.2), _t_(38)=5.02, _p_<.001, _d_=1.63\. Although the dyslexia group took longer on each query (_M_=19.8 s, _SD_= 5.1) than the control group (_M_=17.0 s, _SD_=3.6), the difference was not significant, _t_(38)=1.95, _p_>.058, _d_=0.63.

<table class="center"><caption>  
Table 2: Query summary, SD denote standard deviations  
</caption>

<tbody>

<tr>

<th> </th>

<th colspan="2">Dyslexia group</th>

<th colspan="2">Control group</th>

<th> </th>

</tr>

<tr>

<td> </td>

<th style="text-align:center">Mean</th>

<th style="text-align:center">SD</th>

<th style="text-align:center">Mean</th>

<th style="text-align:center">SD</th>

<th style="text-align:center">p t-test)</th>

</tr>

<tr>

<td>Search time (s) per task</td>

<td style="text-align:left">47.8</td>

<td style="text-align:left">14.6</td>

<td style="text-align:left">29.0</td>

<td style="text-align:left">8.2</td>

<td style="text-align:left"><.001</td>

</tr>

<tr>

<td>Search time (s) per query</td>

<td style="text-align:left">19.8</td>

<td style="text-align:left">5.1</td>

<td style="text-align:left">17.0</td>

<td style="text-align:left">3.6</td>

<td style="text-align:left">>.058</td>

</tr>

<tr>

<td>Number of queries per task, overall</td>

<td style="text-align:left">2.5</td>

<td style="text-align:left">0.6</td>

<td style="text-align:left">1.7</td>

<td style="text-align:left">0.3</td>

<td style="text-align:left"><.001</td>

</tr>

<tr>

<td>Number of queries per task, Bibsys</td>

<td style="text-align:left">2.1</td>

<td style="text-align:left">0.5</td>

<td style="text-align:left">1.6</td>

<td style="text-align:left">0.3</td>

<td style="text-align:left"><.001</td>

</tr>

<tr>

<td>Number of queries per task, external</td>

<td style="text-align:left">0.4</td>

<td style="text-align:left">0.3</td>

<td style="text-align:left">0.1</td>

<td style="text-align:left">0.1</td>

<td style="text-align:left"><.001</td>

</tr>

<tr>

<td>Portion of misspelled queries, Bibsys</td>

<td style="text-align:left">44%</td>

<td style="text-align:left">10%</td>

<td style="text-align:left">26%</td>

<td style="text-align:left">14%</td>

<td style="text-align:left"><.001</td>

</tr>

</tbody>

</table>

Dyslexic users formulated significantly more queries per task (_M_=2.5, _SD_=0.6) than the controls (_M_=1.7, _SD_=0.3), _t_(38)=5.42, _p_<.001, _d_=1.76\. A higher submission of queries was found both in the library catalogue and external Websites. In Bibsys Ask, users with dyslexia submitted significantly more queries per task (_M_=2.1, _SD_=0.5) than the controls (_M_=1\. 6, _SD_=0.3), _t_(38)=4.52, _p_ <.001, _d_=1.47\. Furthermore, the dyslexic students used external Websites significantly more per task (_M_=0.4, _SD_=0.3) than the control group (_M_=0.1, _SD_=0.1), _t_(38)=4.31\. _p_<.001, _d_=1.40\. All external searches were conducted in Google, except one online dictionary query. No users in the control group relied on external Websites for task five, six and seven.

Dyslexic students misspelled more queries (_M_=0.44, _SD_=0.10) than the controls (_M_=0.26, _SD_=0.14), _t_(38)=4.59, _p_ <.001, _d_=1.49\. The number of spelling errors was higher for all search tasks. None of the controls made spelling errors on task five and six.

Concerning query lengths (see Table 3), dyslexic users included significantly fewer search terms per query (_M_=2.05, _SD_=0.23) than the controls (_M_=2.25, _SD_=0.18), _t_(38)=2.92, _p_<.007, _d_=0.95\. However, when the first query was analysed separately from the remaining queries, both groups submitted similar query lengths, _t_(38)=1.09, _p_>.281, _d_=0.35\. There were no significant differences in lengths in the last query for each task, _t_(38)=1.87, _p_>.069, _d_=0.47\. Consequently, the shorter dyslexic query lengths appeared mainly in the intermediate queries.

<table class="center"><caption>  
Table 3: Query lengths, SD denote standard deviations  
</caption>

<tbody>

<tr>

<th> </th>

<th colspan="2">Dyslexia group</th>

<th colspan="2">Control group</th>

<th> </th>

</tr>

<tr>

<td> </td>

<th style="text-align:center">Mean</th>

<th style="text-align:center">SD</th>

<th style="text-align:center">Mean</th>

<th style="text-align:center">SD</th>

<th style="text-align:center">p t-test)</th>

</tr>

<tr>

<td>Submitted terms per query, overall</td>

<td style="text-align:left">2.05</td>

<td style="text-align:left">0.23</td>

<td style="text-align:left">2.25</td>

<td style="text-align:left">0.18</td>

<td style="text-align:left"><.007</td>

</tr>

<tr>

<td>Submitted terms per first query</td>

<td style="text-align:left">2.07</td>

<td style="text-align:left">0.28</td>

<td style="text-align:left">2.16</td>

<td style="text-align:left">0.27</td>

<td style="text-align:left">>.281</td>

</tr>

<tr>

<td>Submitted terms per last query</td>

<td style="text-align:left">2.18</td>

<td style="text-align:left">0.23</td>

<td style="text-align:left">2.30</td>

<td style="text-align:left">0.21</td>

<td style="text-align:left">>.069</td>

</tr>

<tr>

<td>Minimum number of terms per query</td>

<td style="text-align:left">1.75</td>

<td style="text-align:left">0.33</td>

<td style="text-align:left">2.01</td>

<td style="text-align:left">0.20</td>

<td style="text-align:left"><.006</td>

</tr>

<tr>

<td>Maximum number of terms per query</td>

<td style="text-align:left">2.35</td>

<td style="text-align:left">0.16</td>

<td style="text-align:left">2.33</td>

<td style="text-align:left">0.22</td>

<td style="text-align:left">>.743</td>

</tr>

</tbody>

</table>

The minimum number of terms per query was significantly lower among dyslexic users (_M_=1.75 terms, _SD_=0.33) than the controls (_M_=2.01 terms, _SD_=0.20), _t_(38)=3.02, _p_<.006, _d_=0.98\. There were no significant differences in maximum query lengths, _t_(38)=0.33, _p_>.743, _d_=0.10.

The participants applied different approaches when a query failed to return useful results, for instance using external Websites or query modifications such as altering query lengths, changing the spelling of words or replacing words (see Table 4 and Figure 4).

<table class="center"><caption>  
Table 4: Experimental results, SD denote standard deviations  
</caption>

<tbody>

<tr>

<th> </th>

<th colspan="2">Dyslexia group</th>

<th colspan="2">Control group</th>

<th> </th>

</tr>

<tr>

<td> </td>

<th style="text-align:center">Mean</th>

<th style="text-align:center">SD</th>

<th style="text-align:center">Mean</th>

<th style="text-align:center">SD</th>

<th style="text-align:center">p t-test)</th>

</tr>

<tr>

<td>Portion of queries with changed spelling</td>

<td style="text-align:left">46%</td>

<td style="text-align:left">13%</td>

<td style="text-align:left">40%</td>

<td style="text-align:left">20%</td>

<td style="text-align:left">>.252</td>

</tr>

<tr>

<td>Portion of queries where external web sites are applied</td>

<td style="text-align:left">27%</td>

<td style="text-align:left">11%</td>

<td style="text-align:left">16%</td>

<td style="text-align:left">15%</td>

<td style="text-align:left"><.017</td>

</tr>

<tr>

<td>Portion of queries with increased query lengths</td>

<td style="text-align:left">16%</td>

<td style="text-align:left">8%</td>

<td style="text-align:left">27%</td>

<td style="text-align:left">24%</td>

<td style="text-align:left">>.057</td>

</tr>

<tr>

<td>Portion of queries with decreased query lengths</td>

<td style="text-align:left">11%</td>

<td style="text-align:left">9%</td>

<td style="text-align:left">10%</td>

<td style="text-align:left">12%</td>

<td style="text-align:left">>.774</td>

</tr>

<tr>

<td>Portion of queries with replacement of words</td>

<td style="text-align:left">6%</td>

<td style="text-align:left">9%</td>

<td style="text-align:left">7%</td>

<td style="text-align:left">16%</td>

<td style="text-align:left">>.905</td>

</tr>

</tbody>

</table>

The most frequent approach involved changing the spelling of terms. Dyslexic users changed the spelling in more queries (_M_=0.46, _SD_=0.13) than the controls (_M_=0.40, _SD_=0.20). However, there were no significant differences, _t_(38)=1.16, _p_>.252, _d_=0.38\. Consulting external Websites to identify the correct spelling of terms was the only approach with significant differences. External Websites were used significantly more by dyslexics (_M_=0.27, _SD_=0.11) than controls (_M_=0.16, _SD_=0.15), _t_(38)=2.53, _p_<.017, _d_=0.82\. There were no significant differences in the remaining approaches such as modifying query lengths or replacing terms (see Table 4).

<figure class="centre">![Figure 4: Mean use of query modification approaches per intermediate query](p689fig4.jpg)

<figcaption>Figure 4: Mean use of query modification approaches per intermediate query</figcaption>

</figure>

## Discussion

Dyslexics often exhibit slow or inaccurate reading and writing ([Caroll and Iles, 2006](#car06)). It was therefore expected that the dyslexic users would take more time on each task than controls. This assumption was confirmed and is in accordance with the findings by MacFarlane et al. ([2010](#mac10)). The increased time use could be explained by a higher number of queries and the use of external Websites. It is common that users with dyslexia have difficulties concentrating on a task for a long time ([Mortimore and Crozier, 2006](#mor06)). A fatigue-related effect could therefore have caused increased search times. However, the time use did not increase during the experiment. Consequently, a more accessible interface may reduce search times for all tasks.

Users with dyslexia often have reduced rapid naming skills ([Smith-Spark and Fisk, 2007](#smi07)), smaller vocabularies, are more limited in their choice of words ([Connelly, Campbell, MacLean and Barnes, 2006](#con06)) and display slower writing speeds than is usual for their age ([Hatcher, Snowling and Griffiths, 2002](#hat02)). It was therefore expected that dyslexic users would take longer time per query compared to controls (H1), an assumption which was not confirmed. This result was unexpected. However, some of the search terms, such as author names, were included in the oral instructions, thus reducing the need for good rapid naming skills to quickly identify search terms. Moreover, dyslexic users formulated more short queries compared to the controls. Consequently, dyslexic users may have used more time per query if the query lengths had been similar throughout the experiment. These results imply that help functions which reduce the demands on query content may be helpful.

It was hypothesised that dyslexic users would formulate more queries per task than controls, an assumption which was confirmed. The observations indicate that the higher number of queries among the dyslexics was mainly caused by insufficient or too extensive result lists and misspellings, which led to query modifications and use of external Websites. These findings indicate that dyslexia has a negative effect on search performance in databases with a low tolerance for misspellings and no query-building aids.

Dyslexic users were expected to submit shorter queries than controls (H3). It was assumed that slower writing speed and a high risk of spelling errors would result in shorter queries, thus reducing search times and eliminating misspellings. Dyslexic students did submit significantly shorter queries than the controls. This difference was mainly found in the intermediate queries. There were no significant differences in query lengths when the first or last queries were analysed separately. Consequently, the participants started and ended the search sessions at approximately the same precision levels, which implies that the result lists contained approximately the same number of documents on a similar relevance level for both groups.

Query lengths affect the size and content of result lists. Precision and recall refers to a search engine's ability to retrieve relevant documents. There is a trade-off between these two measurements. Short and general queries result in long imprecise result lists, while longer and more specific queries lead to higher precision. Precision could potentially be an aim for slow readers. Precise queries may facilitate the browsing process by reducing the size of result lists and increasing the relevance of the first documents in the list. The costs of longer queries include a higher risk of misspellings, which may explain the shorter queries in the dyslexia group. Several dyslexic participants used the built-in search-function in the browser rather than scan the result lists. This behaviour suggests an attempt to reduce work load and solve the issues regarding the contradictory relationship between precision and recall. Moreover, these findings imply that there may be a need for alterations in the presentation of result lists to better accommodate users with dyslexia.

There was a significant difference between the groups regarding minimum query lengths, but not maximum lengths. Dyslexic students submitted shorter intermediate queries, possibly to isolate the misspelling, for instance:  
                Q<sub>1-1</sub>: 'knut hamsun nasismen', Q<sub>1-2</sub>: 'knut hamsun', Q<sub>1-3</sub>: 'knut hamsun nazismen'.  
The user removed one word in Q<sub>1-2</sub>, to verify the spelling of the author name, before the subject term was reintroduced with a different spelling. Query Q2 is an example of a similiar approach, but here the user searched with one term at a time before combining them in the last query:  
               Q<sub>2-1</sub>: 'Sigrid Unseth', Q<sub>2-2</sub>: 'Unset', Q<sub>2-3</sub>: 'Kristin', Q<sub>2-4</sub>: 'Kristin Unset'.

Query Q1 and Q2 indicate that a lack of query-building aids or a low tolerance for spelling errors may lead to more queries to solve a task. It would have been useful if the system provided the user with more substantial information when errors occurred, for instance by indicating which terms were not matched in the database: '_no results in the database for the term Unseth_'' as a response to Q<sub>2-1</sub>. This function would have counteracted the need for Q<sub>2-2</sub> and Q<sub>2-3</sub>, and thus cut the number of queries by a half.

It was assumed that the dyslexic students would exhibit more spelling errors than the controls (H4). This hypothesis was supported. The number of misspellings increased according to number of search terms, which was also as expected, since the use of more terms is likely to increase the total probability of spelling errors.

The number of errors was mainly related to query lengths and the inclusion of unfamiliar or difficult words, such as _helleristninger_ and _Algerie_. Previous studies have found that adults with dyslexia may memorise the spelling of familiar words, but have more difficulties with orthographic patterns which results in more errors in unfamiliar words ([Kemp, Parrila and Kirby, 2009](#kem09)). The results from the Bibsys searches are in accordance with these findings. Moreover, these findings also support the position that autocomplete functions could be beneficial when task complexity increases. This is in accordance with the students' comments during the de-briefing interview about the potential problematic features or shortcomings in search systems such as Bibsys Ask. All except one of the students with dyslexia mentioned the lack of spelling aids as the most prominent problem.

Although Bibsys Ask did not offer any query-building aids, the system included an authority file. Such files contain the authorised form of, for instance, author names as well as the addition of different spellings of terms. In these cases, users may retrieve results although a term is not spelled correctly if they have used a spelling which is in accordance with the variations in the file. It was anticipated that there would be many spelling errors in the William Shakespeare task. This task included terms with several challenging linguistic components, such as irregular orthography, double consonants and silent vowels. These complex linguistic components are typically difficult by dyslexic users. The last name of the author may also be regarded as an unfamiliar word. However, the library catalogue actually returned results when the query was formulated without the 'e' at the end of Shakespeare, because of the authority file. The participants also received results when adding a 'd' at the end of Hamsun. If such a mapping had not been included, the number of registered misspellings and query modifications would presumably have been even higher. Further, the use of external Websites was higher for the Shakespeare task, thus reducing the number of misspelled queries.

Several approaches for resolving misspellings were observed. Nevertheless, many errors could have been averted through autocomplete functions or spelling suggestions. However, in many searches a higher tolerance for spelling errors would have been adequate to accommodate dyslexic users. This was particularly evident in the number of Google searches where relevant results were retrieved despite misspelled queries. These results indicate that a high tolerance for spelling errors reduce the negative effect of dyslexia on search performance. Users with dyslexia often make different spelling errors than their peers ([Li, Sbatella and Tedesco, 2013](#li13)). Consequently, spellcheckers which accommodate the misspellings of users with dyslexia should be implemented. Such technology is already available in proprietary software. Participants without dyslexia also made spelling errors during the search sessions which shows that query-building aids would be useful for a wide cohort of users. This finding supports the work of de Santana et al. ([2012](#des12)).

Many dyslexics in the study claimed that they often guessed the spelling of words rather than spending time compiling the correct query. In other cases Google was used as a dictionary. Schoot, Licht, Horsley and Sergeant ([2000](#sch00)) found that guessing while reading is not uncommon for dyslexics. However, results from this Bibsys Ask study may indicate that such guessing behaviour may also be applied during writing.

Users with dyslexia often develop coping strategies to compensate for their impairment ([Borkowski, Estrada, Milstead and Hale, 1989](#bor89)). Consequently, it was hypothesised that dyslexic users would apply a broader range of problem solving strategies than controls (H5). However, using external Websites was the only approach that was significantly undertaken by the dyslexic users.

Google was the only external Website used by participants in the study, except for one direct search in an online dictionary. This was not surprising, since Google is a widely used search engine ([Westerwick, 2013](#wes13)), and it has a high tolerance for spelling errors and includes autocomplete functions. The high tolerance level for misspelled queries was evident in several searches in this study. For instance, a dyslexic student received relevant results on a query despite three misspellings: '_helerystninger i hedemark og oppland_'' (correct query _helleristninger i hedmark og oppland_'').

Using external resources may be an approach based on prior experiences. Such behaviour may also be an example of least possible effort ([Bates, 2002](#bat02)) where students try to avoid the system most difficult to use, since Google demands less effort from the users. A majority of the students found the library catalogues difficult to use compared to general search engines. Consequently, they preferred formulating the query in Google to avoid using the library catalogue.

Several dyslexics usually searched Google first to find the proper spelling before pasting the query into the library catalogue search interface. Such a strategy reduced the effort and mental load required in Bibsys Ask to compile the proper query syntax. This approach was apparent in searches with difficult spellings, where students in both groups searched Google directly on the first query. Several students mentioned that such behaviour was a result of past experiences with faulty queries in Bibsys Ask. If the students had not applied this strategy, the number of queries and misspellings could have been even more prevailing. Several students with dyslexia often used Google instead of actual online dictionaries for spell checking of Norwegian words in addition to Google translate for English terms. This may indicate that users regard Google as more accessible compared to online reference works.

Some participants revealed that they normally used Google more extensively than during this particular study. In the experimental setting they wanted to try to solve the tasks in Bibsys Ask as instructed. Consequently, the use of external resources may be even more common in the participants' usual practices.

Queries submitted to Google were often longer and less formal than those submitted to Bibsys Ask. For instance, one student submitted the query '_nobelsfredspris_'' (correct term _Nobels fredspris_,) in Bibsys Ask, which returned zero results. The student then submitted the following query to Google: '_Norske vinnere av nob_', whereas Google's autocomplete suggested a correct query. This query was copied and pasted into Bibsys Ask. The increased query lengths in Google may be a response to a high tolerance for spelling errors or that the autocomplete function suggests longer queries. In this study, participants uncertain about the spelling of terms typically inputted a few letters in Google's search interface and then selected or looked at the correct spelling in the autocomplete list. For instance, one user inputted '_nob_' on the task on Norwegian Nobel Peace Prize recipients and '_knut_'' on the Knut Hamsun and Nazism task. These findings suggest that autocomplete may be helpful. Moreover, Google offers full text searching. Consequently, it may be more useful to submit longer informal queries than in bibliographic databases such as Bibsys Ask, which may explain also explain increased query lengths.

A total of 19 dyslexic users and 13 controls searched Google after submitting an erroneous query in Bibsys Ask, rather than modifying the query in the library catalogue. However, several participants actually resolved the misspellings themselves through the altered query submitted to Google. Consequently, the students could have solved the task directly in Bibsys Ask without relying on Google. This may imply that users do not want to spend much time troubleshooting, but rather go directly to a more familiar and tolerant search system when errors occur. Such behaviour may also be caused by a lack of confidence, which is often seen in users with dyslexia ([Jordan, McGladdery and Dyer, 2014](#jor14)).

In one case where Google returned results despite misspellings the user was not given feedback of the spelling error. When a relevant result list was presented despite the misspelling, the student did not realise the spelling error and continued searching Bibsys Ask with the erroneous query. Consequently, this user took more than three minutes solving the task. This behaviour indicates that users may rely on feedback of mistakes. This is also in accordance with general principles of human computer interaction design ([Norman, 2013](#nor13)).

Users seem to rely quite uncritically on the suggestions provided by Google. In two searches for Norwegian recipients of the Nobel Peace Prize, the dyslexic users got the suggestion '_norske nobel vinnere_'' by Google, which was pasted into Bibsys Ask. This was not an incorrect suggestion, since these two words do have meaning separately in Norweian. However, in this particular task, the last two words had to be one compound word: '_norske nobelvinnere_' to solve the task. The users did not notice that the query was incorrect and submitted three additional queries each to Bibsys Ask. This finding indicates that Google's query-building tool sometimes is suboptimal.

Changing spelling was the most frequent problem solving approach within both groups. The dyslexic users seemed especially aware of common mistakes such as double consonants and compound words, and rephrased queries accordingly, for instance:  
               Q<sub>3-1</sub>: '_scene teknikk_', Q<sub>3-2</sub>: '_sceneteknikk_'.

Another user tried different ways of spelling, based on double consonants, in addition to the nd- and dt-sound which may also be problematic for users with dyslexia:  
               Q<sub>4-1</sub>: '_Sigrid Undsett_', Q<sub>4-2</sub>: '_Sigrid Unsett_', Q<sub>4-3</sub>: '_Sigrid Unnsett_', Q<sub>4-4</sub>: '_Sigrid Unnsedt_' (...) (correct spelling Sigrid Undset)

These queries indicate that the search performance would have been approved if the system had suggested the correct spelling.

Changing the spelling of a term is a self-evident strategy for modifying a misspelled query. However, other approaches included replacing or excluding difficult words. Such strategies were especially noticeable in the task on the author of the books about Albert and Skybert (in Norwegian the Sk is pronounced sh, making it potentially difficult to spell). On this task, 25% of the dyslexic users searched with '_Albert Åberg_'. This query was based on prior knowledge of this children's book character's last name, which was not included in the instructions, thereby avoiding a difficult term. This strategy was also found in 25% of the searches by the controls. The results from this study indicate that word replacement might be a common strategy for all users, and is not a particular characteristic of dyslexic users.

Replacements were also applied in intermediate queries. For instance, one student with dyslexia used this approach when looking for '_Helleristninger i Hedmark og Oppland_'' and Hedmark was regarded difficult to spell (Q<sub>5-4</sub>):  
               Q<sub>5-1</sub>: '_helleristinger_', Q<sub>5-2</sub>: '_helleristinger hedmark_', Q<sub>5-3</sub>: '_helleristinger hedemark_', Q<sub>5-4</sub>: '_helleristinger i oppland_'

The replacement approach may not always be successful in bibliographic databases such as Bibsys Ask. In a full text database it is plausible that synonyms are applied to vary the writing style. However, in a bibliographic database the query should match the terms included in the metadata, such as names, titles or subject headings. However, tools such as synonym control or thesauri may provide results although the query contains non-preferred terms. In these cases the replacement approach could be productive. Consequently, search systems should support such functions to accommodate users who exhibit this type of query modification.

Finally, several students with dyslexia mentioned asking a librarian as a commonly used problem solving approach. One dyslexic student had given up searching the library catalogue altogether, and always got help from librarians because locating literature by using the database was too time-consuming. This is in accordance with Mortimore and Crozier's ([2006](#mor06)) findings that a majority of the students with dyslexia in higher education used or wanted extra library support. It is also an example of least possible effort ([Bates, 2002](#bat02)). However, such situations should be avoided by providing all users with accessible interfaces and excessive training.

## Conclusion

The results from this study indicate that users with dyslexia struggle when searching databases with a low tolerance for errors and no query-building aids. Dyslexic users took more time, formulated more queries, submitted shorter queries and made more misspellings than controls. Further, they relied more on external Websites to solve tasks. However, if functions that reduce the demands for correct spelling are implemented, the interface may become more accessible and thus reduce the negative effect of dyslexia. For instance, search systems could contain the following functions:

*   feedback on which part of a query where there is no match
*   suggest terms if misspellings occur
*   allow users to replace difficult terms (synonym control)
*   suggest queries while the user is entering queries (autocomplete)
*   tolerance for spelling errors, including errors typically made by dyslexic users

Moreover, the result lists should be more accessible, for instance by including more visual information such as images or icons. Further research is needed to identify more effective result list designs and investigate whether textual or visual content is easiest to browse through for dyslexic users.

Users without reading or writing disorders also make spelling errors, which was evident in this study. Misspellings can occur for variety of reasons, for instance if users are inputting text too fast, using an unfamiliar keyboard, inputting unknown words or if the user is tired or unfocused. Consequently, improving an interface to accommodate dyslexic users will enhance the search experience for all users. This finding is consistent with other studies ([McCarthy and Swierenga, 2010](#mcc10); [Boldyreff, Burd, Donkin and Marshall, 2001](#bol01)).

No significant differences in problem solving approaches were uncovered, except for a more frequent use of external resources among dyslexic users. The widespread use of a system with query-building aids and a high tolerance for errors may indicate that such systems are perceived more accessible. However, this can also be attributable to more experience with Google than the library catalogue.

Query lengths indicated that there were no significant differences in precision levels, which implies that users with and without dyslexia may have similar basic search skills. The differences in search behaviour may be merely caused by impaired reading and writing skills. However, since many search terms were included in the assignments, the study did not reveal if dyslexia affected the selection of proper search terms.

Results from this study seem to strengthen the assumption that search interfaces with a low tolerance for spelling errors and no query-building aids are not accessible for users with dyslexia. More specific guidelines are needed to reduce the need for extra support and strengthen the independence, thus reducing the need for extra library support.

## Acknowledgements

This project has been financially supported by the Norwegian ExtraFoundation for Health and Rehabilitation through EXTRA funds grant 2011/12/0258\. The authors are grateful to the volunteering students and Dyslexia Norway for help recruiting participants.

## About the authors

**Gerd Berget** is a PhD student at Institute of Technology at Oslo and Akershus University College of Applied Sciences. Her research includes universal design, information searching behavior, dyslexia and eye tracking studies. She can be contacted at [gerd.berget@hioa.no.](mailto:gerd.berget@hioa.no.)  
**Frode Eika Sandnes** is a professor at the Institute of Technology at Oslo and Akershus University College of Applied Sciences and at the Faculty of Technology, Westerdals Oslo School of Arts, Communication and Technology. Oslo, Norway. His research interests include human computer interaction, universal design and pattern matching. He can be contacted at [frode-eika.sandnes@hioa.no.](mailto:frode-eika.sandnes@hioa.no)

#### References

*   Al-Maskari, A. & Sanderson, M. (2011). [The effect of user characteristics on search effectiveness in information retrieval](http://www.webcitation.org/6a0gsS7Qf). _Information Processing & Management, 47_(5), 719-729\. Retrieved from http://bit.ly/1RfhLYL. (Archived by WebCite<sup>®</sup> at http://www.webcitation.org/6a0gsS7Qf)
*   Allen, D. K. & Wilson, T. D. (2003). Information overload: context and causes. _New Review of Information Behaviour Research, 4_(1), 31-44
*   Al-Wabil, A., Zaphiris, P. & Wilson, S. (2007). [Web navigation for individuals with dyslexia: an exploratory study](http://www.webcitation.org/6a0h3PBaS). In C. Stephanidis (Ed.), _Universal access in human computer interaction:coping with diversity._ (pp. 593-602). Berlin: Springer. (Lecture Notes in Computer Science Volume 4554). Retrieved from http://openaccess.city.ac.uk/1051/1/1406_final.pdf. (Archived by WebCite<sup>®</sup> at http://www.webcitation.org/6a0h3PBaS)
*   Association of College and Research Libraries (2000). [_Information literacy competency standards for higher education_](http://www.webcitation.org/6a0h8QOzr). Chicago, IL: American Library Association. Retrieved from https://arizona.openrepository.com/arizona/bitstream/10150/105645/1/standards.pdf. (Archived by WebCite<sup>®</sup> at http://www.webcitation.org/6a0h8QOzr)
*   Badian, N. A. (1999). Reading disability defined as a discrepancy between listening and reading comprehension: a longitudinal study of stability, gender differences, and prevalence. _Journal of Learning Disabilitiesm, 32_(2), 138-148.
*   Bates, M. J. (2002). [Toward an integrated model of information seeking and searching](http://www.webcitation.org/6a0jAc9rZ). _New Review of Information Behaviour Research_, **3**, 1-15\. Retrieved from http://ptarpp2.uitm.edu.my/silibus/TOWARDANINTEGRATEDMODEL.pdf. (Archived by WebCite<sup>®</sup> at http://www.webcitation.org/6a0jAc9rZ)
*   Berget, G. & Sandnes, F. E. (in press). Do autocomplete functions reduce the effect of dyslexia on information searching behavior? The case of Google. _Journal of the American Society for Information Science & Technology_, in press.
*   Boldyreff, C., Burd, E., Donkin, J. & Marshall, S. (2001). The case for the use of plain English to increase Web accessibility. In _Proceedings of the 3rd International Workshop on Web Site Evolution, Florence, Italy_. (pp. 42-48). Washington, DC: IEEE.
*   Borkowski, J. G., Estrada, M. T., Milstead, M. & Hale, C. A. (1989). General problem-solving skills: relations between metacognition and strategic processing. _Learning Disability Quarterly, 12_(1), 57-70.
*   Caroll, J. M. & Iles, J. E. (2006). [An assessment of anxiety levels in dyslexic students in higher education](http://www.webcitation.org/6a0jFJdsk). _British Journal of Educational Psychology, 76_(3), 651-662\. Retrieved from http://wrap.warwick.ac.uk/385/1/WRAP_Carroll_anxietyJMC_140305.pdf. (Archived by WebCite<sup>®</sup> at http://www.webcitation.org/6a0jFJdsk)
*   Connelly, V., Campbell, S., MacLean, M. & Barnes, J. (2006). [Contribution of lower order skills to the written composition of college students with and without dyslexia](http://www.webcitation.org/6a0jKkAHz). _Developmental Neuropsychology, 29_(1), 175-196\. Retrieved from http://bit.ly/1GoKBlr. (Archived by WebCite<sup>®</sup> at http://www.webcitation.org/6a0jKkAHz)
*   Craven, J. & Brophy, P. (2003). _Non-visual access to the digital library: the use of digital library interfaces by blind and visually impaired people_. Manchester, UK: Manchester Metropolitan University, Centre for Research in Library and Information Management.
*   Dahle, A. E. & Knivsberg, A.-M. (2014). Internalizing, externalizing and attention problems in dyslexia. _Scandinavian Journal of Disability Research, 16_(2), 179-193.
*   de Santana, V. F., de Oliveira, R., Almeida, L.D.A., & Baranauskas, M. C. C. (2012). [Web accessibility and people with dyslexia: a survey on techniques and guidelines](http://www.webcitation.org/6a0jPMH9d). In M. Vigo, J. Abascal, P. Salomoni and R. Lopes (Eds.), _Proceedings of the International Cross-Disciplinary Conference on Web Accessibility (W4A), Lyon, France, 16-17 April, 2012_. New York, NY: ACM. Retrieved from http://www.ramb.ethz.ch/CDstore/www2012/W4A/01%20-%20Technical%20Papers/santana.pdf. (Archived by WebCite<sup>®</sup> at http://www.webcitation.org/6a0jPMH9d)
*   Evett, L. & Brown, D. (2005). Text formats and web design for visually impaired and dyslexic readers: clear text for all. _Interacting with Computers, 17_(4), 453-472.
*   Freire, A.P., Petrie, H. & Power, C. (2011). [Empirical results from an evaluation of the accessibility of websites by dyslexic users](http://www.webcitation.org/6a0jThrTg). In G. Weber, H. Petrie and J. Darzentas (Eds.), _Proceedings of the Workshop on Accessible Design in the Digital World 2011, CEUR, Lisbon, Portugal, September 5, 2011_, (pp. 41-53). Aachen, Germany: CEUR-WS.Org. Retrieved from https://www.cs.york.ac.uk/hci/publications/002/dyslexia_addw%20v4.pdf. (Archived by WebCite<sup>®</sup> at http://www.webcitation.org/6a0jThrTg)
*   Germano, E., Gagliano, A. & Curatolo, P. (2010). Comorbidity of ADHD and dyslexia. _Developmental Neuropsychology, 35_(5), 475-493.
*   Gross, M. (1995). The imposed query. _Reference & User Services Quarterly, 35_(2), 236-243.
*   Habib, L., Berget, G., Sandnes, F.E., Sanderson, N., Kahn, P., Fagernes, S. & Olcay, A. (2012). Dyslexic students in higher education and virtual learning environments: an exploratory study. _Journal of Computer Assisted Learning, 28_(6), 574-584.
*   Hatcher, J., Snowling, M.J. & Griffiths, Y.M. (2002). Cognitive assessment of dyslexic students in higher education. _British Journal of Educational Psychology, 72_(1), 119-133.
*   Hawke, J.L., Olson, R.K., Willcut, E.G., Wadsworth, S.J. & DeFries, J.C. (2009). Gender ratios for reading difficulties. _Dyslexia, 15_(3), 239-242.
*   Helland, T. & Kaasa, R. (2005). Dyslexia in English as a second language. _Dyslexia, 11_(1), 41-60.
*   Henry, S. L., Abou-Zahra, S. & Brewer, J. (2014). [The role of accessibility in a universal web](http://www.webcitation.org/6a0jYe1o8). In J. P. Bigham, Y. Borodin and Carrino (Eds.), _W4A - 14, April 07 - 09 2014, Seoul, Republic of Korea_, ACM, New York, article no. 17\. Retrieved from http://dspace.mit.edu/openaccess-disseminate/1721.1/88013\. (Archived by WebCite<sup>®</sup> at http://www.webcitation.org/6a0jYe1o8)
*   Hepworth, M. (2007). Knowledge of information behaviour and its relevance to the design of people-centred information products and services. _Journal of Documentation, 63_(1), 33-56.
*   Høien, T. & Lundberg, I. (2012). _Dysleksi: fra teori til praksis_ [Dyslexia: from theory to practise]. Oslo: Gyldendal.
*   Høien, T. & Tønnesen, G. (2008). _Instruksjonshefte til ordkjedetesten: Bryne: Logometrica._
*   Imrie, R. (2012). Universalism, universal design and equitable access to the built environment. _Disability and Rehabilitation, 34_(10), 873-882.
*   ISO. (2009). _ISO 8596 Ophthalmic optics: visual acuity testing - standard optotype and its presentation_. Geneva, Switzerland: International Organization for Standardization.
*   Jamali, H.R., & Asadi, S. (2010). [Google and the scholar: the role of Google in scientists' information-seeking behaviour](http://www.webcitation.org/6a0jdzuBc). _Online Information Review, 34_(2), 282-294\. Retrieved from http://bit.ly/1RvtlLH. (Archived by WebCite<sup>®</sup> at http://www.webcitation.org/6a0jdzuBc)
*   Jones, M.W., Branigan, H.P. & Kelly, M.L. (2007). Visual deficits in developmental dyslexia: relationships between non-linguistic visual tasks and their contribution to components of reading. _Dyslexia, 14_(2), 95-115.
*   Jordan, J-A., McGladdery, G. & Dyer, K. (2014). Dyslexia in higher education: implications for maths anxiety, statistics anxiety and psychological well-being. _Dyslexia, 20_(3), 225-240.
*   Kemp, N., Parrila, R. K. & Kirby, J. R. (2009). [Phonological and orthographic spelling in high-functioning adult dyslexics](http://www.webcitation.org/6a0jiNYK5). _Dyslexia, 15_(2), 105-128\. Retrieved from http://bit.ly/2062ZpM. (Archived by WebCite<sup>®</sup> at http://www.webcitation.org/6a0jiNYK5)
*   Kim, K-S. & Allen, B. (2002). Cognitive and task influences on web searching behaviour. _Journal of the American Society for Information Science & Technology, 53_(2), 109-119.
*   Kuhlthau, C. C. (1991). [Inside the search process: information seeking from the user's perspective](http://www.webcitation.org/6a0jmjiLb). _Journal of the American Society for Information Science, 42_(5), 361-371\. Retrieved from http://ptarpp2.uitm.edu.my/silibus/insidesearch2.pdf. (Archived by WebCite<sup>®</sup> at http://www.webcitation.org/6a0jmjiLb)
*   Lervåg, A., & Hulme, C. (2009). [Rapid automatized naming (RAN) taps a mechanism that places constraints on the development of early reading fluency](http://www.webcitation.org/6a0juy6j9). _Psychological Science, 20_(8), 1040-1048\. Retrieved from http://thinkingskillsclub.com/wp-content/uploads/2014/04/ran_brain_area_2009-2010.pdf. (Archived by WebCite<sup>®</sup> at http://www.webcitation.org/6a0juy6j9)
*   Li, A.Q., Sbatella, L. & Tedesco, R. (2013). PoliSpell: an adaptive spellchecker and predictor for people with dyslexia. In S. Carberry, S. Weibelzahl, A. Micarelli & G. Semeraro (Eds.), _UMAP 2013, The 21<sup>st</sup> Conference on User Modeling, Adaptation and Personalization, Rome, Italy, Springer, Berlin_, pp. 302-309.
*   Lyster, S-A.H. (2007). Reading development and reading disabilities: focus on Norway. In B. G. Cook, M. Tankersley, & T. J. Landrum (Eds.) _Advances in Learning and Behavioral Disabilities, 20_, 21-55.
*   MacFarlane, A., Al-Wabil, A., Marshall, C. R, Albrair, A., Jones, S. A. & Zaphiris, P. (2010). [The effect of dyslexia on information retrieval: a pilot study](http://www.webcitation.org/6a0kC0kHm). _Journal of Documentation, 66_(3), 307-326\. Retrieved from http://openaccess.city.ac.uk/1694/1/dyslexia-paper-JDOC-revised-FINAL.pdf. (Archived by WebCite<sup>®</sup> at http://www.webcitation.org/6a0kC0kHm)
*   MacFarlane, A., Albrair, A., Marshall, C.R. & Buchanan, G. (2012). [Phonological working memory impacts on information searching: an investigation of dyslexia](http://www.webcitation.org/6a0kGrW5k). In _Proceedings of IIiX 2012 the Fourth Information Interaction in Context Symposium, Nijmegen, the Netherlands, August 21-24, 2012_. (pp. 27-34). New York, NY: ACM. Retrieved from http://openaccess.city.ac.uk/4493/1/dyslexia-memory-search-oa.pdf. (Archived by WebCite<sup>®</sup> at http://www.webcitation.org/6a0kGrW5k)
*   McCarthy, J.E. & Swierenga, S.J. (2010). [What we know about dyslexia and web accessibility: a research review](http://www.webcitation.org/6a0kL1HMT). _Universal Access in the Information Society, 9_(2), 147-152\. Retrieved from http://bit.ly/1WccYu4\. (Archived by WebCite<sup>®</sup> at http://www.webcitation.org/6a0kL1HMT)
*   Mortimore, T. & Crozier, W. R. (2006). Dyslexia and difficulties with study skills in higher education. _Studies in Higher Education, 31_(2), 235-251.
*   Norman, D. (2013). _The design of everyday things_. New York, NY: Basis Books.
*   Palmquist, R. A. & Kim, K.-S. (2000). Cognitive style and on-line database search experience as predictors of web search performance. _Journal of the American Society for Information Science & Technology, 51_(6), 558-566.
*   Papaeconomou, C., Zijlema, A. F., & Ingwersen, P. (2008). Searchers' relevance judgments and criteria in evaluating web pages in a learning style perspective. In P. Borlund, J. W. Schneider, M. Lamas, A. Tombros, J. Feather, D. Kelly & A. P. de Vries (Eds.) _Proceedings of the second international symposium on information interaction in context, London, October 14-17_, (pp 123-132). New York, NY: ACM.
*   Ransby, M. J. & Swanson, H. L. (2003). Reading comprehension skills of young adults with childhood diagnoses of dyslexia. _Journal of Learning Disabilities, 36_(6), 538-555.
*   Rello, L. & Baeza-Yates, R. (2013). Good fonts for dyslexia. In _ASSETS -13, The 15<sup>th</sup> International ACM SIGACCESS Conference on Computers and Accessibility, Bellevue, WA, USA, October 21 - 23_. (Article No. 4). New York, NY: ACM
*   Rello, L., Pielot, M., Marcos, M-C. & Carlini, R. (2013). Size matters (spacing not): 18 points for a dyslexic-friendly Wikipedia. In _W4A-13, International Cross-Disciplinary Conference on Web Accessibility, May 13-15, 2013, Rio de Janeiro, Brazil_, (Article no. 17). New York, NY: ACM.
*   Sahib, N. G., Tombros, A. & Stockman, T. (2012). [A comparative analysis of the information-seeking behavior of visually impaired and sighted searchers](http://www.webcitation.org/6a0kpJfZw). _Journal of the American Society for Information Science, 63_(2), 377-391\. Retrieved from http://ejournals.library.ualberta.ca/index.php/EBLIP/article/downloadSuppFile/18556/2757\. (Archived by WebCite<sup>®</sup> at http://www.webcitation.org/6a0kpJfZw)
*   Schoot, M. v d, Licht, R., Horsley, T. M. & Sergeant, J. A. (2000). [Inhibitory deficits in reading disability depend on subtype: guessers not spellers](http://www.webcitation.org/6a0kvAIP2). _Child Neuropsychology, 6_(4), 297-312\. Retrieved from http://dspace.ubvu.vu.nl/bitstream/handle/1871/18439/Schoot_Child%20Neuropsychology_6%284%29_2000_u.pdf?sequence=2\. (Archived by WebCite<sup>®</sup> at http://www.webcitation.org/6a0kvAIP2)
*   Schuchardt, K., Maehler, C. & Hasselhorn, M. (2008). Working memory deficits in children with specific learning disorders. _Journal of Learning Disabilities, 41_(6), 514-523.
*   Smith-Spark, J.H. & Fisk, J.E. (2007). Working memory functioning in developmental dyslexia. _Memory, 15_(1), 34-56.
*   Snowling, M.J. (2000), _Dyslexia_. Malden, MA: Blackwell.
*   Snowling, M.J. (2001). From language to reading and dyslexia. _Dyslexia, 7_(1), 37-46.
*   Solheim, O. J. & Uppstad, P. H. (2011). [Eye-tracking as a tool in process-oriented reading test validation](http://www.webcitation.org/6a0l267NM). _International Electronic Journal of Elementary Education, 4_(1), 153-168\. Retrieved from http://brage.bibsys.no/xmlui/bitstream/handle/11250/185914/Eye-tracking_as_a_tool.pdf?sequence=1\. (Archived by WebCite<sup>®</sup> at http://www.webcitation.org/6a0l267NM)
*   Swanson, H.L., & Hsieh, C-J. (2009). Reading disabilities in adults: a selective meta-analysis of the literature. _Review of Educational Research, 79_(4), 1362-1390.
*   Tops, W., Callens, M., Lammertyn, J., Van Hees, V. & Brysbaert, M. (2012). Identifying students with dyslexia in higher education. _Annals of Dyslexia, 62_(3), 186-203.
*   Westerwick, A. (2013). [Effects of sponsorship, web site design and, and Google ranking on the credibility of online information](http://www.webcitation.org/6a0l9G3j5). _Journal of Computer-Mediated Communication, 18_(2), 194-211\. Retrieved from http://onlinelibrary.wiley.com/doi/10.1111/jcc4.12006/full. (Archived by WebCite<sup>®</sup> at http://www.webcitation.org/6a0l9G3j5)
*   World Wide Web Consortium. (2008). [_Web content accessibility guidelines (WCAG) 2.0_](http://www.w3.org/TR/WCAG20/). Retrieved from http://www.w3.org/TR/WCAG20/. (Archived by WebCite<sup>®</sup> at http://www.webcitation.org/6cXw1tqwt)
*   Zhang, P., Bobier, W., Thompson, B. & Hess, R.F. (2011). Binocular balance in normal vision and its modulation by mean luminance. _Optometry and Vision Science, 88_(9), 1072-1079.