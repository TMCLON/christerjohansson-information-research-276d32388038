#### vol. 16 no. 2, June, 2011

# A comparative study of methods to explore searchers' affective perceptions of images

#### [Jung Won Yoon](#author)  
School of Information, University of South Florida, Tampa, Florida  

#### Abstract

> **Introduction.** Previous search query analysis studies demonstrated that emotional perceptions and needs tend not to be sufficiently reflected in image queries. To provide a better understanding of the emotional attributes of an image, this study explored and compared such attributes obtained from related tasks.  
> **Method.** This study analysed attributes of an image through sorting, describing and searching. A data-set was obtained from Flickr images tagged with one of six basic emotions (love, joy, surprise, anger, sadness and fear); fifty-nine students participated.  
> **Results**. The sorting and describing tasks revealed two categories of emotions, joy and sadness, which people perceive from images. They also revealed some emotional terms which were chosen frequently as labels for sorted images. Comparison of image perceptions obtained from the three tasks performed on an image demonstrated similar perceptions, but there are minor differences resulting from the unique characteristics of each task or research setting.  
> **Conclusions**. The categories of joy and sadness, along with the identified frequently used emotional terms, should receive attention in designing image indexing and retrieval systems. Also, the features of each task and environment setting should be considered when developing a research design exploring emotional aspects of an image.

## Introduction

The main purpose of information retrieval is to provide search results which can fulfill users' information needs. Therefore, it is critical to reflect users' information needs and their searching patterns in designing an information retrieval/indexing mechanism. Through search queries, users express their information needs and communicate with an information retrieval system. So, examining users' queries has been used as a way of understanding users' needs. In the image retrieval field, there have been several studies which analysed search queries under the same assumption ([Armitage and Enser 1997](#arm97); [Chen 2001](#che01); [Choi and Rasmussen](#cho03) 2003; [Collins 1998](#col98); [Enser and McGregor 1992](#ens92); [Goodrum and Spink 2001](#goo01); [Keister 1994](#kei94)). However, even with the benefits of studying query analysis, there are some issues that cannot be resolved by this method. For instance, search queries may not represent users' needs completely, because users often do not recognize their own needs or have difficulty converting visual needs into verbal expressions. Also, experienced users of an image retrieval system tend to create queries which seem to return their anticipated search results, even if the users know that the queries do not represent their visual needs precisely. Therefore, in addition to query analysis, for understanding image searchers' unexpressed needs and image perceptions, several image related tasks, such as describing, sorting, similarity judgment and others, have been employed in image user studies.

Compared to query analysis study, studies exploring image related tasks consistently emphasized the significance of emotional attributes of an image. For instance, sorting task studies supported that people categorize images using abstract and emotional features of images ([Jørgensen 1995](#jor95); [Rorissa and Hastings 1994](#ror94); [Laine-Hernandez and Westman 2006](#lai06)) and description task studies demonstrated that people tend to use more abstract and emotional terms in the describing tasks than in the search tasks ([Jørgensen 1995](#jor95); [O'Connor, _et al._ 1999](#oco99); [Greisdorf and O'Connor 2002](#gre02); [Hollink, _et al._ 2004](#hol04)). A line of reasoning adopted by these studies explains that, because of the notion that emotional attributes are subject to an individual viewer's interpretation ([Greisdorf and O'Connor 2002](#gre02)), current image retrieval/indexing mechanisms have limitations in supporting access to subjective emotional meanings; therefore, searchers experienced in image retrieval systems are inclined not to use emotional terms in their queries ([Jørgensen 2003](#jor03); [Eakins, _et al._ 2004](#eak04)).

In short, it has been demonstrated that emotional meanings offer significant messages, in which image users are interested. Therefore, in order to improve image retrieval effectiveness through emotional attributes, it would be necessary to examine those attributes of an image comprehensively. However, those previous studies explored emotional attributes only as a part of their studies; as a result, there was no overarching study comparing different research designs. We assume that by exploring and comparing emotional attributes obtained from different image related tasks, it will be possible to provide a better understanding of the emotional attributes of an image. Furthermore, comparing emotional features obtained from different tasks could affect how researchers design studies of emotional perceptions of images. As a more practical benefit, results of this study will suggest how emotional features can be integrated into image indexing and retrieval systems.

This study has the following two specific research questions:

1.  How is an emotion-space (i.e., hierarical representation of emotions) represented through sorting and describing tasks? Are there differences in an emotion-spaces represented through sorting and describing tasks?
2.  Are there differences in emotional perception for an individual image (i.e. emotions apprehended from each individual image) between searching, describing and sorting tasks?

## Literature review

### Image related tasks

If we could observe how people perceive, recognize and interpret visual materials, how they represent their needs for visual materials and how they operate their search processes, we would have a solid foundation for designing an image retrieval system or image organization scheme. However, since direct observation is not possible, researchers have attempted to understand human visual perception and searching activities by using several image related tasks. In this section, studies that examined image related tasks with the purpose of improving image retrieval perforamce are reviewed by focusing on key findings as well as research design. One image related task which is often incorporated in studies is _describing_.This task asks participants to describe what they notice in an image. Studies adopting _describing_ were conducted on the basis of a relatively simple assumption; that is, attributes that are described while viewing an image reveal perceived or pertinent attributes of the image ([Jørgensen 1995](#jor95)). However, since verbal description, which is not an inherent element of visual materials, has limitations in representing perceived or pertinent attributes, different settings have been adopted for exploring image perception from different perspectives. For example, Jørgensen ([1995](#jor95)) used different types of descriptive tasks; O'Connor, _et al._ ([1999](#oco99)) emphasized reactive description; Greisdorf and O'Connor ([2002](#gre02)) used pre-defined queries; Laine-Hernandez and Westman ([2006](#lai06)) compared keyword and free description. Comparison and implications of different approaches will be discussed later.

Another method to elicit perceived image attributes is sorting or categorization. Categorization has been a key topic in psychology, because it is how people process and make manageable an infinite number of different stimuli. In other words, people perceive the world and environment by categorization which treats non-identical stimuli as equivalent ([Rosch 1977](#ros77)). Categorization is applied to information retrieval as a way to '_reduce search space and, thus, search time, because there are fewer categories than the total number of individual numbers_' ([O'Connor, _et al._ 1999](#): 681). Importantly, categorization can be used to facilitate browsing, which is useful when searchers have no idea what they are looking for or have difficulties in expressing their needs ([Rorissa and Hastings 2004](#ror04)). Jørgensen ([1995](#jor95)) assumed that categorization can reveal image attributes that are not extracted from describing tasks, because people sort non-identical images with a notion of similarity in which individual, cultural and contextual backgrounds are embedded. In addition, she suggested that the describing tasks in which participants focused on each individual image, closely mirrored known-item searching, whereas the sorting task in which participants looked at the whole set of images mirrored browsing. As will be discussed later, several studies demonstrated different distributions of image attributes between describing and sorting.

Collocating similar information objects (or documents) is a fundamental function of information organization; therefore, a good indexing mechanism should be able to collocate similar documents and differentiate dissimilar documents. In the field of image retrieval, researchers have attempted to evaluate their indexing mechanism by comparing it with similarity judgment tasks conducted by people ([Rogowitz, _et al._ 1998](#rog98); [Rorissa 2005](#ror05)). Since the sorting task is also based on a notion of similarity, sorting and similarity judgment tasks have common features. However, whereas a sorting task usually involves participants sorting a set of images, similarity judgment tasks ask participants to compare a pair of images. Rogowitz, _et al._ ([1998](#rog98)) found these two tasks demonstrated consistent results.

### Related studies

Table 1 summarizes previous studies in terms of study purpose, image collection, participants, and procedure. There are a couple of studies which analysed different types of user descriptions. O'Connor, _et al._ ([1999](#oco99)), who recognized the potential of users' reactions to images as access points, collected three types of users' reactions: caption, subject description and reactions (words or phrases describing how images makes users feel). The authors found the prevalent occurrences of narrative (conversational) and adjectival descriptors. Greisdorf and O'Connor ([2002](#gre02)) investigated how users assign predetermined query terms to images and suggested the importance of affective and emotional query terms in image retrieval.

Several studies compared _describing_ tasks with other image related tasks, such as search, sorting and similarity judgment. With the purpose of identifying typical image attributes which are revealed in image related tasks, Jørgensen ([1995](#jor95)) conducted a set of describing tasks including descriptive viewing, descriptive searching and descriptive memory tasks, a sorting task and a concept search task. Content analysis on the set of describing tasks showed forty-seven attribute categories and twelve broad classes which can be characterized as either _perceptual_ or _interpretive_ attributes. When analysed by twelve classes, four perceptual classes, _objects_, _people_, _colour_ and _spatial location_, were generally identified across all describing tasks, whereas _emotion_ and _abstract_ attributes appeared in the top half of the viewing task, they dropped to the midpoint for the descriptive search task. Jørgensen interpreted this result as the tendency for people who are formulating their search statements to do so with the realization that it will be processed by an image retrieval system.

Compared to describing tasks, the sorting task demonstrated a lower occurrence of the _object_, _colour_, _spatial location_ and _visual element_ classes and a higher occurrence of the _abstract_ attribute. Also, a strong effect of sorting, based on whether or not a human was in a picture, was detected in the sorting task. The research concluded that compared to the describing tasks, the sorting task relied more on an _interpretative_ attribute. Laine-Hernandez and Westman ([2006](#lai06)) conducted a description (keywording and free description) and categorization study (hereafter, the categorization task is named sorting task, for consistent naming with other studies) to examine whether a particular image genre, journalistic photographs, influenced image indexing schemes. Location, people and descriptive terms were more often used in the free description task, whereas abstract concepts, themes, settings and emotions were more frequently used in the keywording tasks. Laine-Hernandez and Westman ([2006](#lai06)) suggested that participants use more summarizing terms for the keywording tasks, because they had a limit of five terms. Overall, interpretational semantics were dominant in the describing tasks. In the sorting task, abstract and emotional themes and the presence of people were the main criteria in judging image similarity.

Hollink, _et al._ ([2004](#hol04)) proposed and tested a framework for the classification of image attributes which were developed, based on related literatures. Participants were asked to illustrate three given texts using free description and query. This setting was designed to investigate a '_category search behavior_' which was defined as '_the user has no specific image in mind but is able to specify requirements or conditions for the resulting image. The result will be the class of images that satisfy the conditions_'. ([Hollink, _et al._ 2004](#): 614). By comparing semantically richer, free descriptions and limited search queries, the authors found that terms in the general attribute were the most frequently used in both tasks; however, in the query tasks, more specific terms and less abstract and perceptual terms were found.

Rorissa ([2005](#ror05)) investigated the relationships between common and distinctive features of images and their similarity as perceived by human judges. Common and distinctive features of images, which were derived by analysing participants' description tasks, were compared with similarity judgment and confirmed the relationships between common and distinctive features and image similarity; particularly, common features had more weight than distinctive features.

Studies have also employed a sorting task. Börner ([2000](#bor00)) conducted a usability study comparing a latent semantic analysis algorithm applied to the information visualizer and human free-sorting task. Data analysis results showed a similarity between human sorting patterns and features derived from textual descriptions through the algorithm. Rorissa and Hastings posited that although categorization had been recognized as a way of facilitating browsing, there is no answer as to which attributes should be used to categorize images. By investigating human sorting tasks, the authors concluded that 'interpretive attributes are better candidates than perceptual attributes for indexing categories/groupings of images'. ([Rorissa and Hastings 2004](#ror04): 360).

Rogowitz _et al._ (1998) conducted two experiments to investigate how humans judge image similarity, the table scale and the computer scale and image similarity results were compared with two algorithmic image similarity metrics: a colour-histogram and a multi-resolution framework of colour, contraction and orientation-selective attributes. Results demonstrated that different approaches used in the two experiments produced similar patterns. Also, the colour of the images was significantly related to human similarity judgment. Although the authors named table scale and computer scale as similarity tasks, the setting of the table scale task has been commonly used for the sorting task. Therefore, the study results can be interpreted to mean that sorting and similarity judgment tasks show similar results.

<table style="border: medium solid rgb(153, 245, 251); font-size: smaller; font-style: normal; font-family: verdana,geneva,arial,helvetica,sans-serif; background-color: rgb(253, 255, 221);" width="95%" align="center" border="1" cellpadding="3" cellspacing="0"><caption align="bottom">  
**Table 1: Studies adopting image related tasks**</caption>

<tbody>

<tr>

<th>Study</th>

<th> </th>

<th>Research design</th>

</tr>

<tr>

<td rowspan="5">O'Connor, O'Connor & Abbas ([1999](#oco99))</td>

<td>Task</td>

<td>Describing</td>

</tr>

<tr>

<td>Purpose</td>

<td>To demonstrate potential of users' reactions as access points</td>

</tr>

<tr>

<td>Collection</td>

<td>a set of 300 images drawn from the collection of O'Connor</td>

</tr>

<tr>

<td>Participants</td>

<td>120 Master of Library Science students</td>

</tr>

<tr>

<td>Procedure</td>

<td>Participants were asked to generate three types of descriptions (caption, subject description and response) from any 100 images of their choosing.</td>

</tr>

<tr>

<td rowspan="5">Greisdorf & O'Connor ([2002](#gre02))</td>

<td>Task</td>

<td>Describing</td>

</tr>

<tr>

<td>Purpose</td>

<td>To investigate post-retrieval processing of images</td>

</tr>

<tr>

<td>Collection</td>

<td>Ten grayscale images selected from the National Oceanic and Atmospheric Administration</td>

</tr>

<tr>

<td>Participants</td>

<td>19</td>

</tr>

<tr>

<td>Procedure</td>

<td>Participants were given a list of twenty-six terms which correspond to one of seven image attributes (colour, shape, texture, object, action, location and affect) and assigned terms to the images if the term would be used as a query term for retrieving the image.</td>

</tr>

<tr>

<td rowspan="5">Jørgensen ([1995](#jor95))</td>

<td>Task</td>

<td>Describing; Sorting; Searching</td>

</tr>

<tr>

<td>Purpose</td>

<td>o demonstrate typical image attributes revealed in several image related tasks</td>

</tr>

<tr>

<td>Collection</td>

<td>Images selected from the _Twenty-Fifth Illustrators Annual_</td>

</tr>

<tr>

<td>Participants</td>

<td>A total of 167 individual participants from all levels of an academic setting in a variety of disciplines</td>

</tr>

<tr>

<td>Procedure</td>

<td>Descriptive viewing task: participants described six images which were projected for two minutes;  
Descriptive search task: participants described the six images to a librarian or an ideal image retrieval system accepting natural language;  
Descriptive memory task: participants described the images five weeks later;  
Sorting task: Participants sorted seventy-seven images into groups which would be used later for finding images;  
Concept search task: participants selected images which expressed two given abstract concepts, 'mysterious' and 'transformation'.</td>

</tr>

<tr>

<td rowspan="5">Laine-Hernandez & Westman ([2006](#lai06))</td>

<td>Task</td>

<td>Describing; Sorting</td>

</tr>

<tr>

<td>Purpose</td>

<td>To evaluate current image indexing framework for reportage photographs and to find the effect of different tasks on image description and image sorting</td>

</tr>

<tr>

<td>Collection</td>

<td>Forty reportage-type photographs from two online image collections by image journalists and amateur photographers were selected based on several criteria, such as a variety of colourfulness, lightness, viewing distance and topical and emotional content.</td>

</tr>

<tr>

<td>Participants</td>

<td>Twenty native Finnish speakers (students of technology and university employees)</td>

</tr>

<tr>

<td>Procedure</td>

<td>Keywording task: participants wrote down five words for each photograph without time limitations.  
Free description task: participants described each photograph as they would describe its contents to another person, without time limitations.  
Categorization task: participants organized printed photographs.</td>

</tr>

<tr>

<td rowspan="5">Hollink, Schreiber, Wielinga & Worring ([2004](#hol04))</td>

<td>Task</td>

<td>Describing; Search</td>

</tr>

<tr>

<td>Purpose</td>

<td>To understand how people perceive images and to develop a framework for the classification of image attributes</td>

</tr>

<tr>

<td>Collection</td>

<td>n/a</td>

</tr>

<tr>

<td>Participants</td>

<td>Thirty participants (students of the University of Amsterdam and their family and friends)</td>

</tr>

<tr>

<td>Procedure</td>

<td>Participants were given three texts providing different search contexts (a paragraph from a children's book, a few lines from a historical novel and a paragraph from a newspaper) and asked to form an image in their minds illustrating each text, to write down a free text description of the images and to search for the images using a maximum of five queries.</td>

</tr>

<tr>

<td rowspan="5">Rorissa ([2005](#ror05))</td>

<td>Task</td>

<td>Describing; Similarity judgment</td>

</tr>

<tr>

<td>Purpose</td>

<td>To investigate the relationships between common and distinctive features of images and their similarity judged by human observers</td>

</tr>

<tr>

<td>Collection</td>

<td>A set of 30 colour images obtained from a book by O'Connor and Wyatt ([2004](#oco04))</td>

</tr>

<tr>

<td>Participants</td>

<td>150 students of the School of Library and Information Science (seventy-five participants were assigned to each of two tasks)</td>

</tr>

<tr>

<td>Procedure</td>

<td>Description task: participants describe features of each image for ninety seconds.  
Similarity judgment task: using magnitude estimation, participants conducted the similarity judgment task twice with 435 pairs of the thirty images (the set used for the second time was obtained by reversing the order of image pairs used for the first time).</td>

</tr>

<tr>

<td rowspan="5">Börner ([2000](#bor))</td>

<td>Task</td>

<td>Sorting</td>

</tr>

<tr>

<td>Purpose</td>

<td>To conduct a usability study of the data analysis algorithm applied in the Digital Library Visualizer. Sorting task results and the Latent Semantic Analysis results from the textual image descriptions were compared.</td>

</tr>

<tr>

<td>Collection</td>

<td>Four image data sets obtained from the Dido image data bank (a digital library at the Indiana University Department of the History of Art) using the following four search queries, Bosch, African and two Chinese. The sets contained twelve, seventeen, thirty-one and thirty-two images, respectively.</td>

</tr>

<tr>

<td>Participants</td>

<td>Twenty graduate students</td>

</tr>

<tr>

<td>Procedure</td>

<td>Each participant sorted two image sets, labelled the groups and described the sorting criteria they used.</td>

</tr>

<tr>

<td rowspan="5">Rorissa & Hastings ([2004](#ror04))</td>

<td>Task</td>

<td>Sorting</td>

</tr>

<tr>

<td>Purpose</td>

<td>To investigate how natural categorization behaviour can be applied to image indexing and classification systems</td>

</tr>

<tr>

<td>Collection</td>

<td>A set of fifty colour images selected from the _Hemera Photo Object Volume 1_.</td>

</tr>

<tr>

<td>Participants</td>

<td>Thirty graduate students at a major southwestern United States university</td>

</tr>

<tr>

<td>Procedure</td>

<td>Participants sorted a set of printed images without any constraints on the time or the number of categories.</td>

</tr>

<tr>

<td rowspan="5">Rogowitz, Frese, Smith, Bouman, & Kalin ([1998](#rog98))</td>

<td>Task</td>

<td>Sorting; Similarity judgment</td>

</tr>

<tr>

<td>Purpose</td>

<td>To investigate how humans judge image similarity</td>

</tr>

<tr>

<td>Collection</td>

<td>Ninety-seven photographs representing various semantic categories, viewing distances and colours</td>

</tr>

<tr>

<td>Participants</td>

<td>Fifteen volunteer observers from the T.J. Watson Research Center, Hawthorne Laboratory</td>

</tr>

<tr>

<td>Procedure</td>

<td>Table scaling: participants arranged a set of printed images based on their similarities - similar images would be close to each other.  
Computer scaling: participants were presented with a reference image and eight randomly-chosen images on a computer screen and of the eight images they were asked to select the image most similar to the reference image.</td>

</tr>

</tbody>

</table>

In addition to these studies, there are studies of the extraction of emotional features through low-level features of an image (see Wang and He's ([2008](#wan08)) survey paper). Recently, Schmidt and Stock ([2009](#sch09)) demonstrated that scroll bars adapted to collect users' basic emotional judgments on images can be used in emotion indexing of images.

## Research design

This study explored emotional perception of an image through sorting, describing and searching, which were adopted for understanding general image perceptions. In order to explore emotional perception, an emotion-space should be defined. However, in addition to a variety of emotional terms, definitions and boundaries of emotional terms are fuzzy and vague; therefore, in this study _basic emotions_ are used in selecting images. This idea is based on _basic theory_, which asserted and demonstrated that there are basic level categories which include most frequently and commonly used concepts or terms ([Rosch 1977](#ros77)). Many theorists agree there is a set of basic emotions, but there is little consensus on the number of basic emotions and what basic emotions are ([Ortony and Turner 1990](#ort90)). The current study adopted the emotional terms and their hierarchical structures which were proposed by Shaver, _et al._ ([1987](#sha87)). Shaver _et al._ collected candidate emotional terms (nouns) from related literatures and asked participants to rate whether each term was an emotional term or not. Then, the final selected 135 emotional words were categorized by participants in order to reveal hierarchical clusters. The hierarchy included three levels of emotions: the first level consisted of two emotional categories, positive and negative emotions which were represented by Joy and Sadness, the second level consisted of six emotional categories and the third level consisted of twenty-five emotional categories (Table 2). They found that the second level was consistent with other studies which demonstrated features of basic level emotions. The six basic emotional terms employed by Shaver _et al._ were used in selecting images and analysing collected data. A set of images was selected from Flickr, in which ordinary users' casual photos are uploaded, rather than using a standard dataset (such as a data set from the International Affective Picture System), which includes strong stimuli for inducing intensive affective reactions. Thirty creative commons licensed Flickr images tagged with one of the six basic emotions were selected. Then, by conducting a pilot study with eleven graduate student participants, twelve photos (two photos for each basic emotion) were chosen. These photos were consistently given basic emotional terms in the pilot study.

<table style="border: medium solid rgb(153, 245, 251); font-size: smaller; font-style: normal; font-family: verdana,geneva,arial,helvetica,sans-serif; background-color: rgb(253, 255, 221);" width="80%" align="center" border="1" cellpadding="3" cellspacing="0"><caption align="bottom">  
**Table 2: Three levels of emotional categories**</caption>

<tbody>

<tr>

<th>Level 1</th>

<th>Level 2</th>

<th>Level 3</th>

</tr>

<tr>

<td rowspan="3">Positive (joy)</td>

<td>Love</td>

<td>Affection, lust, longing</td>

</tr>

<tr>

<td>Joy</td>

<td>Cheerfulness, zest, contentment, pride, optimism, enthrallment, relief</td>

</tr>

<tr>

<td>(Surprise)</td>

<td>(Surprise)</td>

</tr>

<tr>

<td rowspan="3">Negative (sadness)</td>

<td>Anger</td>

<td>Irritation, exasperation, rage, disgust, envy, torment</td>

</tr>

<tr>

<td>Sadness</td>

<td>Suffering, sadness, disappointment, shame, neglect, sympathy</td>

</tr>

<tr>

<td>Fear</td>

<td>Horror, nervousness</td>

</tr>

</tbody>

</table>

Three image related tasks, sorting, describing and searching, were assigned to participants. Although this study used twelve images, for the sorting task participants were asked to sort the thirty images (4" x 6" photographs), which were used in the pilot study, into two to twenty-five groups according to emotional impressions and to give a label to each group using 135 emotional names. The sorting task used thirty images because twelve images might lead participants to generate a small number of groups. For the describing task, each of the twelve images was projected on to a large screen. Participants were asked to choose descriptors from the list of 135 emotional names for each image and then select one emotional name that described the image most appropriately. For the searching task, six searching situations were given to participants. For example, the researcher asked participants 'Let's assume that you send a query "Love" to the image search engine. Which photos are appropriate for this query?' Then, participants were asked to pick two appropriate photographs and then select the most appropriate from those two. The six basic emotions were used in the searching situations. The survey questionnaire was administered to fifty-nine students at the University of South Florida. The majority of participants were female (70.7%), undergraduate students (94.6%), between eighteen and twenty-five years old (77.6%). Their majors varied and included mass communication, world language, English, social work, criminology, biology, nursing, biomedical science and engineering.

## Findings

### Representation of emotion-space from the sorting and describing tasks

Of the three tasks explored in the current study, the searching task simulated a real searching situation, although it had limitations in revealing subtle and hidden information needs and their contexts, whereas the sorting and describing tasks did not directly reflect searching behaviour, although they attempted to examine an emotion-space and perceptions obtained from images. In this section, an emotion-space is examined and compared with reference to the sorting and describing tasks.

#### Sorting task

For the sorting task, the average number of groups generated by a participant was 6.88 and the maximum and minimum numbers of groups were 15 and 3, respectively. Approximately 40% of participants created 5 or 6 groups, and 30% of participants generated 8 or 10 groups (Table 3).

<table style="border: medium solid rgb(153, 245, 251); font-size: smaller; font-style: normal; font-family: verdana,geneva,arial,helvetica,sans-serif; background-color: rgb(253, 255, 221);" width="60%" align="center" border="1" cellpadding="3" cellspacing="0"><caption align="bottom">  
**Table 3: Number of categories generated in sorting**</caption>

<tbody>

<tr>

<th>No. of categories</th>

<th>Frequency</th>

<th>Percent</th>

</tr>

<tr>

<td align="center">3</td>

<td align="center">3</td>

<td align="center">5.3</td>

</tr>

<tr>

<td align="center">4</td>

<td align="center">4</td>

<td align="center">7.0</td>

</tr>

<tr>

<td align="center">5</td>

<td align="center">13</td>

<td align="center">22.8</td>

</tr>

<tr>

<td align="center">6</td>

<td align="center">10</td>

<td align="center">17.5</td>

</tr>

<tr>

<td align="center">7</td>

<td align="center">5</td>

<td align="center">8.8</td>

</tr>

<tr>

<td align="center">8</td>

<td align="center">8</td>

<td align="center">14.0</td>

</tr>

<tr>

<td align="center">9</td>

<td align="center">3</td>

<td align="center">5.3</td>

</tr>

<tr>

<td align="center">10</td>

<td align="center">9</td>

<td align="center">15.8</td>

</tr>

<tr>

<td align="center">11</td>

<td align="center">1</td>

<td align="center">1.8</td>

</tr>

<tr>

<td align="center">15</td>

<td align="center">1</td>

<td align="center">1.8</td>

</tr>

<tr>

<td align="center">Total</td>

<td align="center">57</td>

<td align="center">100.0</td>

</tr>

</tbody>

</table>

A notable finding is that although the thirty images were grouped into six sets of five images, each tagged with one of six basic emotions, the six emotions were not evenly represented through the sorting tasks. For example, as shown in Table 4, in the case that three groups were made from thirty images, those groups were not from three different basic emotions but from two basic emotions: in other words, two groups belonged to one basic emotion (two groups belonged to _joy_ and the other group belonged to _sadness_). When five groups were made, these five groups were from three or four different basic emotions rather than five different basic emotional groups. Overall, when six or fewer groups were made, three or four basic emotions were mainly adopted and when more than six groups were made, five basic emotions were primarily adopted.

<table style="border: medium solid rgb(153, 245, 251); font-size: smaller; font-style: normal; font-family: verdana,geneva,arial,helvetica,sans-serif; background-color: rgb(253, 255, 221);" width="60%" align="center" border="1" cellpadding="3" cellspacing="0"><caption align="bottom">  
**Table 4: Relations between the number of groups and basic emotions**</caption>

<tbody>

<tr>

<th rowspan="2">No. of groups</th>

<th colspan="5">No. of basic emotions</th>

</tr>

<tr>

<th align="center">2</th>

<th align="center">3</th>

<th align="center">4</th>

<th align="center">5</th>

<th align="center">6</th>

</tr>

<tr>

<td align="center">3</td>

<td align="center">2</td>

<td align="center"> </td>

<td align="center"> </td>

<td align="center"> </td>

<td align="center"> </td>

</tr>

<tr>

<td align="center">4</td>

<td align="center">1</td>

<td align="center"> </td>

<td align="center">3</td>

<td align="center"> </td>

<td align="center"> </td>

</tr>

<tr>

<td align="center">5</td>

<td align="center"> </td>

<td align="center">4</td>

<td align="center">7</td>

<td align="center"> </td>

<td align="center"> </td>

</tr>

<tr>

<td align="center">6</td>

<td align="center"> </td>

<td align="center">1</td>

<td align="center">5</td>

<td align="center">3</td>

<td align="center"> </td>

</tr>

<tr>

<td align="center">7</td>

<td align="center"> </td>

<td align="center"> </td>

<td align="center"> </td>

<td align="center">3</td>

<td align="center"> </td>

</tr>

<tr>

<td align="center">8</td>

<td align="center"> </td>

<td align="center">1</td>

<td align="center">2</td>

<td align="center">3</td>

<td align="center"> </td>

</tr>

<tr>

<td align="center">9</td>

<td align="center"> </td>

<td align="center"> </td>

<td align="center">3</td>

<td align="center"> </td>

<td align="center"> </td>

</tr>

<tr>

<td align="center">10</td>

<td align="center"> </td>

<td align="center">1</td>

<td align="center">1</td>

<td align="center">4</td>

<td align="center">1</td>

</tr>

<tr>

<td align="center">15</td>

<td align="center"> </td>

<td align="center"> </td>

<td align="center">1</td>

<td align="center"> </td>

<td align="center"> </td>

</tr>

<tr>

<td align="center">Total</td>

<td align="center">3</td>

<td align="center">7</td>

<td align="center">22</td>

<td align="center">12</td>

<td align="center">1</td>

</tr>

</tbody>

</table>

Table 5 presents the categories of basic emotional terms that were frequently used in the sorting task. When two categories of basic emotions appeared, regardless of the number of groups, _joy_ and _sadness_ were the categories adopted during the sorting task. Then, as another basic emotional category is added, one additional basic emotion was obviously noticed, such as _love_, _joy_ and _sadness_ (four out of six occurrences of three basic emotional categories), _love_, _joy_, _sadness_ and _fear_ or _love_, _joy_, _sadness_ and _anger_ (ten and five out of twenty-one occurrences of four basic emotional categories) and _love_, _joy_, _sadness_, _anger_ and _fear_ (nine out of twelve occurrences of five emotional categories). As addressed above, when groups were made, the six basic emotions were not evenly adopted; some basic emotional categories rarely appear but other categories tend to be further divided. For instance, analysing the sorting tasks that generated six groups demonstrated that most participants created one group from the _love_ category, two groups from _joy_, two from _sadness_ and one from _fear_.

<table style="border: medium solid rgb(153, 245, 251); font-size: smaller; font-style: normal; font-family: verdana,geneva,arial,helvetica,sans-serif; background-color: rgb(253, 255, 221);" width="80%" align="center" border="1" cellpadding="3" cellspacing="0"><caption align="bottom">  
**Table 5: Distribution of categories of basic emotional terms**</caption>

<tbody>

<tr>

<th>No. of basic emotions</th>

<th>Love</th>

<th>Joy</th>

<th>Surprise</th>

<th>Anger</th>

<th>Sadness</th>

<th>Fear</th>

<th>Frequency</th>

</tr>

<tr>

<td align="center">2</td>

<td align="center"></td>

<td align="center">X</td>

<td align="center"> </td>

<td align="center"> </td>

<td align="center">X</td>

<td align="center"> </td>

<td align="center">3</td>

</tr>

<tr>

<td align="center">3</td>

<td align="center">X</td>

<td align="center">X</td>

<td align="center"> </td>

<td align="center"> </td>

<td align="center">X</td>

<td align="center"> </td>

<td align="center">4</td>

</tr>

<tr>

<td align="center"> </td>

<td align="center"> </td>

<td align="center">X</td>

<td align="center"> </td>

<td align="center"> </td>

<td align="center">X</td>

<td align="center">X</td>

<td align="center">1</td>

</tr>

<tr>

<td align="center"> </td>

<td align="center"> </td>

<td align="center">X</td>

<td align="center">X</td>

<td align="center"> </td>

<td align="center"> </td>

<td align="center">X</td>

<td align="center">1</td>

</tr>

<tr>

<td align="center">4</td>

<td align="center">X</td>

<td align="center">X</td>

<td align="center"> </td>

<td align="center"> </td>

<td align="center">X</td>

<td align="center">X</td>

<td align="center">10</td>

</tr>

<tr>

<td align="center"> </td>

<td align="center">X</td>

<td align="center">X</td>

<td align="center"> </td>

<td align="center">X</td>

<td align="center">X</td>

<td align="center"> </td>

<td align="center">5</td>

</tr>

<tr>

<td align="center"> </td>

<td align="center"> </td>

<td align="center">X</td>

<td align="center"> </td>

<td align="center">X</td>

<td align="center">X</td>

<td align="center">X</td>

<td align="center">2</td>

</tr>

<tr>

<td align="center"> </td>

<td align="center">X</td>

<td align="center">X</td>

<td align="center">X</td>

<td align="center"> </td>

<td align="center"> </td>

<td align="center">X</td>

<td align="center">1</td>

</tr>

<tr>

<td align="center"> </td>

<td align="center">X</td>

<td align="center">X</td>

<td align="center">X</td>

<td align="center"> </td>

<td align="center">X</td>

<td align="center"> </td>

<td align="center">1</td>

</tr>

<tr>

<td align="center"> </td>

<td align="center"> </td>

<td align="center">X</td>

<td align="center">X</td>

<td align="center"> </td>

<td align="center">X</td>

<td align="center">X</td>

<td align="center">1</td>

</tr>

<tr>

<td align="center"> </td>

<td align="center">X</td>

<td align="center">X</td>

<td align="center"> </td>

<td align="center"> </td>

<td align="center">X</td>

<td align="center">X</td>

<td align="center">1</td>

</tr>

<tr>

<td align="center">5</td>

<td align="center">X</td>

<td align="center">X</td>

<td align="center"> </td>

<td align="center">X</td>

<td align="center">X</td>

<td align="center">X</td>

<td align="center">9</td>

</tr>

<tr>

<td align="center"> </td>

<td align="center">X</td>

<td align="center">X</td>

<td align="center">X</td>

<td align="center"> </td>

<td align="center">X</td>

<td align="center">X</td>

<td align="center">2</td>

</tr>

<tr>

<td align="center"> </td>

<td align="center">X</td>

<td align="center">X</td>

<td align="center">X</td>

<td align="center">X</td>

<td align="center">X</td>

<td align="center"> </td>

<td align="center">1</td>

</tr>

<tr>

<td align="center">6</td>

<td align="center">X</td>

<td align="center">X</td>

<td align="center">X</td>

<td align="center">X</td>

<td align="center">X</td>

<td align="center">X</td>

<td align="center">1</td>

</tr>

<tr>

<td colspan="8">**Frequency** refers to the number of persons choosing the indicated emotion set.</td>

</tr>

</tbody>

</table>

The frequency of occurrence of emotional terms was analysed. Of 135 emotional terms from the list given by Shaver _et al._ ([1987](#sha87)), 99 were used for labelling sorted categories. Of these 99 terms, 18 terms which occurred seven or more times accounted for 50 % of the total occurrences of labelling terms (Table 6). Further analysis is explained below by comparing with the describing task.

<table style="border: medium solid rgb(153, 245, 251); font-size: smaller; font-style: normal; font-family: verdana,geneva,arial,helvetica,sans-serif; background-color: rgb(253, 255, 221);" width="80%" align="center" border="1" cellpadding="3" cellspacing="0"><caption align="bottom">  
**Table 6: Frequency of emotional terms used in the sorting task**</caption>

<tbody>

<tr>

<th>Emotional term</th>

<th>Frequency</th>

<th>%</th>

<th>Cumulative %</th>

<th>Basic category</th>

</tr>

<tr>

<td>Happiness</td>

<td align="center">20</td>

<td align="center">5.1</td>

<td align="center">5.1</td>

<td align="center">Joy</td>

</tr>

<tr>

<td>Excitement</td>

<td align="center">18</td>

<td align="center">4.6</td>

<td align="center">9.7</td>

<td align="center">Joy</td>

</tr>

<tr>

<td>Sadness</td>

<td align="center">16</td>

<td align="center">4.1</td>

<td align="center">13.8</td>

<td align="center">Sadness</td>

</tr>

<tr>

<td>Loneliness</td>

<td align="center">16</td>

<td align="center">4.1</td>

<td align="center">17.9</td>

<td align="center">Sadness</td>

</tr>

<tr>

<td>Love</td>

<td align="center">15</td>

<td align="center">3.8</td>

<td align="center">21.7</td>

<td align="center">Love</td>

</tr>

<tr>

<td>Contentment</td>

<td align="center">13</td>

<td align="center">3.3</td>

<td align="center">25.0</td>

<td align="center">Joy</td>

</tr>

<tr>

<td>Thrill</td>

<td align="center">12</td>

<td align="center">3.1</td>

<td align="center">28.1</td>

<td align="center">Joy</td>

</tr>

<tr>

<td>Tenseness</td>

<td align="center">10</td>

<td align="center">2.6</td>

<td align="center">30.7</td>

<td align="center">Fear</td>

</tr>

<tr>

<td>Affection</td>

<td align="center">9</td>

<td align="center">2.3</td>

<td align="center">33.0</td>

<td align="center">Love</td>

</tr>

<tr>

<td>Enjoyment</td>

<td align="center">8</td>

<td align="center">2.0</td>

<td align="center">35.0</td>

<td align="center">Joy</td>

</tr>

<tr>

<td>Exhilaration</td>

<td align="center">8</td>

<td align="center">2.0</td>

<td align="center">37.0</td>

<td align="center">Joy</td>

</tr>

<tr>

<td>Isolation</td>

<td align="center">8</td>

<td align="center">2.0</td>

<td align="center">39.0</td>

<td align="center">Sadness</td>

</tr>

<tr>

<td>Fear</td>

<td align="center">8</td>

<td align="center">2.0</td>

<td align="center">41.0</td>

<td align="center">Fear</td>

</tr>

<tr>

<td>Caring</td>

<td align="center">7</td>

<td align="center">1.8</td>

<td align="center">42.8</td>

<td align="center">Love</td>

</tr>

<tr>

<td>Amusement</td>

<td align="center">7</td>

<td align="center">1.8</td>

<td align="center">44.6</td>

<td align="center">Joy</td>

</tr>

<tr>

<td>Bliss</td>

<td align="center">7</td>

<td align="center">1.8</td>

<td align="center">46.4</td>

<td align="center">Joy</td>

</tr>

<tr>

<td>Amazement</td>

<td align="center">7</td>

<td align="center">1.8</td>

<td align="center">48.2</td>

<td align="center">Surprise</td>

</tr>

<tr>

<td>Uneasiness</td>

<td align="center">7</td>

<td align="center">1.8</td>

<td align="center">50.0</td>

<td align="center">Fear</td>

</tr>

</tbody>

</table>

#### Describing task

For the describing task, participants were asked to provide as many emotional terms from the list as they wanted to (task D1) and to select the most appropriate emotional term (task D2). When participants were allowed to assign as many terms as they wanted, on average they provided 3.52 terms per image and the maximum and minimum number of terms were 9 and 1, respectively. Although it is beyond the scope of the research objectives, factors related to research design were examined. First, to determine whether the order of descriptors in D1 is related to selecting the most appropriate emotional term. From 633 describing task results, 31.12% (197 describing tasks) selected the first descriptors for the D2 task, 32.39% (205 describing tasks) used any of descriptors in the middle and 26.07% (165 describing tasks) used the last descriptor. 4.90% of participants (31 describing tasks) provided only one descriptor during the D1 task and 5.53% (35 describing tasks) did not follow the instructions given and provided a new term in D2\. This result shows that the order of descriptors given by users is not related to the significance of descriptors. Secondly, to determine whether the order of describing tasks affects the number of descriptors. As shown in Figure 1, except for the last image, which has remarkably few descriptors, the order of projected images seems to have no relation to the number of descriptors.

<div align="center">![Average number of descriptors in terms of the order of projected images](p475fig1.jpg)</div>

<div align="center">  
**Figure 1: Average number of descriptors in terms of the order of projected images**</div>

Tasks D1 and D2 were analysed to determine whether they produced different patterns of emotional descriptors. Of 135 emotional terms, 134 terms were used in D1 and 115 terms in D2\. In the case of D1, of 135 terms, 27 terms accounted for approximately 50% of the total occurrences of descriptors. In the case of D2, of 115 terms, 23 terms accounted for 51% of the total occurrence of descriptors (Table 7). When comparing emotional terms between D1 and D2, those having high frequencies appear in both tasks. However, when comparing terms used in the sorting and describing tasks, frequently used descriptors, such as _surprise_, _tenseness_, _joy_, _delight_, and so on, were not used in the sorting task; whereas terms like Exhilaration, Isolation, Bliss and amazement, were frequently used as a label but not frequently used as descriptors.

<table style="border: medium solid rgb(153, 245, 251); font-size: smaller; font-style: normal; font-family: verdana,geneva,arial,helvetica,sans-serif; background-color: rgb(253, 255, 221);" width="90%" align="center" border="1" cellpadding="3" cellspacing="0"><caption align="bottom">  
**Table 7: Frequency of emotional terms used in the describing task**</caption>

<tbody>

<tr>

<th colspan="5">Task D1</th>

<th colspan="5">Task D2</th>

</tr>

<tr>

<th>Emotional term</th>

<th>Frequency</th>

<th>%</th>

<th>Cumulative %</th>

<th>Basic category</th>

<th>Emotional term</th>

<th>Frequency</th>

<th>%</th>

<th>Cumulative %</th>

<th>Basic category</th>

</tr>

<tr>

<td>Joy</td>

<td align="center">76</td>

<td align="center">3.4</td>

<td align="center">3.4</td>

<td>Joy</td>

<td>Enjoyment</td>

<td align="center">27</td>

<td align="center">4.3</td>

<td align="center">4.3</td>

<td>Joy</td>

</tr>

<tr>

<td>Happiness</td>

<td align="center">73</td>

<td align="center">3.3</td>

<td align="center">6.7</td>

<td>Joy</td>

<td>Happiness</td>

<td align="center">27</td>

<td align="center">4.3</td>

<td align="center">8.6</td>

<td>Joy</td>

</tr>

<tr>

<td>Enjoyment</td>

<td align="center">68</td>

<td align="center">3.1</td>

<td align="center">9.7</td>

<td>Joy</td>

<td>Affection</td>

<td align="center">26</td>

<td align="center">4.1</td>

<td align="center">12.7</td>

<td>Love</td>

</tr>

<tr>

<td>Amusement</td>

<td align="center">59</td>

<td align="center">2.6</td>

<td align="center">12.4</td>

<td>Joy</td>

<td>Surprise</td>

<td align="center">21</td>

<td align="center">3.3</td>

<td align="center">16.0</td>

<td>Surprise</td>

</tr>

<tr>

<td>Love</td>

<td align="center">55</td>

<td align="center">2.5</td>

<td align="center">14.8</td>

<td>Love</td>

<td>Amusement</td>

<td align="center">18</td>

<td align="center">2.9</td>

<td align="center">18.9</td>

<td>Joy</td>

</tr>

<tr>

<td>Delight</td>

<td align="center">52</td>

<td align="center">2.3</td>

<td align="center">17.2</td>

<td>Joy</td>

<td>Caring</td>

<td align="center">16</td>

<td align="center">2.5</td>

<td align="center">21.4</td>

<td>Love</td>

</tr>

<tr>

<td>Caring</td>

<td align="center">51</td>

<td align="center">2.3</td>

<td align="center">19.5</td>

<td>Love</td>

<td>Tenseness</td>

<td align="center">15</td>

<td align="center">2.4</td>

<td align="center">23.8</td>

<td>Fear</td>

</tr>

<tr>

<td>Affection</td>

<td align="center">50</td>

<td align="center">2.2</td>

<td align="center">21.7</td>

<td>Love</td>

<td>Joy</td>

<td align="center">14</td>

<td align="center">2.2</td>

<td align="center">26.0</td>

<td>Joy</td>

</tr>

<tr>

<td>Excitement</td>

<td align="center">49</td>

<td align="center">2.2</td>

<td align="center">23.9</td>

<td>Joy</td>

<td>Fear</td>

<td align="center">14</td>

<td align="center">2.2</td>

<td align="center">28.3</td>

<td>Fear</td>

</tr>

<tr>

<td>Thrill</td>

<td align="center">41</td>

<td align="center">1.8</td>

<td align="center">25.8</td>

<td>Joy</td>

<td>Love</td>

<td align="center">13</td>

<td align="center">2.1</td>

<td align="center">30.3</td>

<td>Love</td>

</tr>

<tr>

<td>Surprise</td>

<td align="center">41</td>

<td align="center">1.8</td>

<td align="center">27.6</td>

<td>Surprise</td>

<td>Gloom</td>

<td align="center">13</td>

<td align="center">2.1</td>

<td align="center">32.4</td>

<td>Sadness</td>

</tr>

<tr>

<td>Sadness</td>

<td align="center">40</td>

<td align="center">1.8</td>

<td align="center">29.4</td>

<td>Sadness</td>

<td>Loneliness</td>

<td align="center">13</td>

<td align="center">2.1</td>

<td align="center">34.4</td>

<td>Sadness</td>

</tr>

<tr>

<td>Loneliness</td>

<td align="center">38</td>

<td align="center">1.7</td>

<td align="center">31.1</td>

<td>Sadness</td>

<td>Tenderness</td>

<td align="center">11</td>

<td align="center">1.7</td>

<td align="center">36.2</td>

<td>Love</td>

</tr>

<tr>

<td>Cheerfulness</td>

<td align="center">37</td>

<td align="center">1.7</td>

<td align="center">32.8</td>

<td>Joy</td>

<td>Delight</td>

<td align="center">11</td>

<td align="center">1.7</td>

<td align="center">37.9</td>

<td>Joy</td>

</tr>

<tr>

<td>Tenseness</td>

<td align="center">35</td>

<td align="center">1.6</td>

<td align="center">34.3</td>

<td>Fear</td>

<td>Excitement</td>

<td align="center">11</td>

<td align="center">1.7</td>

<td align="center">39.7</td>

<td>Joy</td>

</tr>

<tr>

<td>Fear</td>

<td align="center">34</td>

<td align="center">1.5</td>

<td align="center">35.8</td>

<td>Fear</td>

<td>Contentment</td>

<td align="center">11</td>

<td align="center">1.7</td>

<td align="center">41.4</td>

<td>Joy</td>

</tr>

<tr>

<td>Tenderness</td>

<td align="center">32</td>

<td align="center">1.4</td>

<td align="center">37.3</td>

<td>Love</td>

<td>Cheerfulness</td>

<td align="center">9</td>

<td align="center">1.4</td>

<td align="center">42.9</td>

<td>Joy</td>

</tr>

<tr>

<td>Contentment</td>

<td align="center">32</td>

<td align="center">1.4</td>

<td align="center">38.7</td>

<td>Joy</td>

<td>Thrill</td>

<td align="center">9</td>

<td align="center">1.4</td>

<td align="center">44.3</td>

<td>Joy</td>

</tr>

<tr>

<td>Worry*</td>

<td align="center">32</td>

<td align="center">1.4</td>

<td align="center">40.2</td>

<td>Fear</td>

<td>Sadness</td>

<td align="center">9</td>

<td align="center">1.4</td>

<td align="center">45.7</td>

<td>Sadness</td>

</tr>

<tr>

<td>Adoration*</td>

<td align="center">29</td>

<td align="center">1.3</td>

<td align="center">41.5</td>

<td>Love</td>

<td>Uneasiness</td>

<td align="center">9</td>

<td align="center">1.4</td>

<td align="center">47.1</td>

<td>Fear</td>

</tr>

<tr>

<td>Fondness*</td>

<td align="center">29</td>

<td align="center">1.3</td>

<td align="center">42.8</td>

<td>Love</td>

<td>Glee</td>

<td align="center">8</td>

<td align="center">1.3</td>

<td align="center">48.4</td>

<td>Joy</td>

</tr>

<tr>

<td>Gloom</td>

<td align="center">29</td>

<td align="center">1.3</td>

<td align="center">44.1</td>

<td>Sadness</td>

<td>Shame*</td>

<td align="center">8</td>

<td align="center">1.3</td>

<td align="center">49.7</td>

<td>Sadness</td>

</tr>

<tr>

<td>Pleasure*</td>

<td align="center">28</td>

<td align="center">1.3</td>

<td align="center">45.3</td>

<td>Joy</td>

<td>Panic*</td>

<td align="center">8</td>

<td align="center">1.3</td>

<td align="center">51.0</td>

<td>Fear</td>

</tr>

<tr>

<td>Uneasiness</td>

<td align="center">28</td>

<td align="center">1.3</td>

<td align="center">46.6</td>

<td>Fear</td>

<td> </td>

<td> </td>

<td> </td>

<td> </td>

<td> </td>

</tr>

<tr>

<td>Glee</td>

<td align="center">27</td>

<td align="center">1.2</td>

<td align="center">47.8</td>

<td>Joy</td>

<td> </td>

<td> </td>

<td> </td>

<td> </td>

<td> </td>

</tr>

<tr>

<td>Shock*</td>

<td align="center">27</td>

<td align="center">1.2</td>

<td align="center">49.0</td>

<td>Fear</td>

<td> </td>

<td> </td>

<td> </td>

<td> </td>

<td> </td>

</tr>

<tr>

<td>Anxiety*</td>

<td align="center">27</td>

<td align="center">1.2</td>

<td align="center">50.2</td>

<td>Fear</td>

<td> </td>

<td> </td>

<td> </td>

<td> </td>

<td> </td>

</tr>

<tr>

<td colspan="10">* Terms appear in D1 but not in D2 or vice versa.</td>

</tr>

</tbody>

</table>

Distributions of basic emotional categories which appeared in the sorting and two describing tasks were compared. As shown in Table 8, overall distributions were similar over three tasks; emotional terms which belong to the _joy_ category were most dominant followed by terms in the _sadness_, _love_, _fear_, _anger_ and _surprise_ categories.

<table style="border: medium solid rgb(153, 245, 251); font-size: smaller; font-style: normal; font-family: verdana,geneva,arial,helvetica,sans-serif; background-color: rgb(253, 255, 221);" width="80%" align="center" border="1" cellpadding="3" cellspacing="0"><caption align="bottom">  
**Table 8: Categorical distribution of emotional terms used in the sorting and describing tasks**</caption>

<tbody>

<tr>

<th rowspan="2"> </th>

<th colspan="2">Sorting</th>

<th colspan="2">D1</th>

<th colspan="2">D2</th>

</tr>

<tr>

<th>Freq.</th>

<th>%</th>

<th>Freq.</th>

<th>%</th>

<th>Freq.</th>

<th>%</th>

</tr>

<tr>

<td>Love</td>

<td align="center">56</td>

<td align="center">15.1</td>

<td align="center">343</td>

<td align="center">16.0</td>

<td align="center">106</td>

<td align="center">17.3</td>

</tr>

<tr>

<td>Joy</td>

<td align="center">143</td>

<td align="center">38.4</td>

<td align="center">763</td>

<td align="center">35.7</td>

<td align="center">202</td>

<td align="center">33.1</td>

</tr>

<tr>

<td>Surprise</td>

<td align="center">13</td>

<td align="center">3.5</td>

<td align="center">63</td>

<td align="center">2.9</td>

<td align="center">30</td>

<td align="center">4.9</td>

</tr>

<tr>

<td>Anger</td>

<td align="center">27</td>

<td align="center">7.3</td>

<td align="center">175</td>

<td align="center">8.2</td>

<td align="center">44</td>

<td align="center">7.2</td>

</tr>

<tr>

<td>Sadness</td>

<td align="center">82</td>

<td align="center">22.0</td>

<td align="center">463</td>

<td align="center">21.6</td>

<td align="center">136</td>

<td align="center">22.3</td>

</tr>

<tr>

<td>Fear</td>

<td align="center">51</td>

<td align="center">13.7</td>

<td align="center">332</td>

<td align="center">15.5</td>

<td align="center">93</td>

<td align="center">15.2</td>

</tr>

<tr>

<td>Total</td>

<td align="center">372</td>

<td align="center">100.0</td>

<td align="center">2139</td>

<td align="center">100.0</td>

<td align="center">611</td>

<td align="center">100.0</td>

</tr>

</tbody>

</table>

The participants were instructed to select the terms from the given list of 135 emotional terms, but some participants used their own terms in the sorting and describing tasks. They said that they could not find appropriate terms from the list and they had a better term in mind. Terms that appeared twice or more were: relaxed (relaxing), beautiful, cold, fun, calm, wet, tired, scared, dull, boring, indifference and serenity. Since this study was designed to use 135 emotional terms, it was not the scope of this study to investigate these unlisted terms. However, they would demonstrate users' understanding of emotional scope, so further discussion is provided in the next section.

#### Comparison of individual image perceptions across three tasks

This section examines whether the three tasks (sorting, describing, and searching) represent emotional perception of an image differently. As presented in Table 9, of twelve images, six (L1, J1, J2, A2, Sa2 and F2) showed consistent distributions across three tasks and four (L2, Su1, Su2 and Sa1) were perceived differently in the searching task than the other two tasks. Two images (A1 and F1) were perceived differently in each of the three tasks. The first notable finding is that half of the twelve images demonstrated different distribution between the searching and sorting or describing tasks. A possible explanation is that the searching task adopted in this study forced participants to make relative judgments among images, whereas the other two tasks asked them to describe and sort images freely. For instance, although an image (L2) conveys an impression of love as well as joy, if the image is perceived as the most joyful among the other images, the image has a high rating for _joy_ in the searching task. However, the same image can be sorted and described mainly as an image expressing _love_, because participants perceived that the image itself expressed _love_ rather than _joy_. Also, the images (Su1 and Su2) which were tagged with _surprise_ were rarely described or sorted as a surprise emotion, but when participants were asked to select images expressing surprise, these two images were chosen. Furthermore, ten out of twelve images demonstrated similar distributions between the sorting and describing tasks, in general. However, a closer observation revealed that task D2 tends to present a more dominant emotional perception of an image than the D1 or sorting tasks and the sorting task presented more diverse emotional perceptions related to an image.

<table style="border: medium solid rgb(153, 245, 251); font-size: smaller; font-style: normal; font-family: verdana,geneva,arial,helvetica,sans-serif; background-color: rgb(253, 255, 221);" width="80%" align="center" border="1" cellpadding="3" cellspacing="0"><caption align="bottom">  
**Table 9: Overall differences across three tasks**</caption>

<tbody>

<tr>

<th rowspan="2"> </th>

<th colspan="4">L1*</th>

<th colspan="4">L2</th>

<th colspan="4">J1</th>

<th colspan="4">J2</th>

</tr>

<tr>

<th>F</th>

<th>S</th>

<th>D1</th>

<th>D2</th>

<th>F</th>

<th>S</th>

<th>D1</th>

<th>D2</th>

<th>F</th>

<th>S</th>

<th>D1</th>

<th>D2</th>

<th>F</th>

<th>S</th>

<th>D1</th>

<th>D2</th>

</tr>

<tr>

<td>Love</td>

<td align="center">100.0</td>

<td align="center">57.9</td>

<td align="center">74.7</td>

<td align="center">86.8</td>

<td align="center">16.7</td>

<td align="center">56.1</td>

<td align="center">59.3</td>

<td align="center">77.4</td>

<td align="center">15.4</td>

<td align="center">14.0</td>

<td align="center">3.2</td>

<td align="center">1.9</td>

<td align="center">7.7</td>

<td align="center">22.9</td>

<td align="center">16.2</td>

<td align="center">13.2</td>

</tr>

<tr>

<td>Joy</td>

<td align="center">0.0</td>

<td align="center">33.4</td>

<td align="center">20.7</td>

<td align="center">13.2</td>

<td align="center">50.0</td>

<td align="center">35.2</td>

<td align="center">34.3</td>

<td align="center">22.7</td>

<td align="center">84.6</td>

<td align="center">80.7</td>

<td align="center">90.9</td>

<td align="center">90.6</td>

<td align="center">92.3</td>

<td align="center">70.3</td>

<td align="center">80.3</td>

<td align="center">84.9</td>

</tr>

<tr>

<td>Surprise</td>

<td align="center">0.0</td>

<td align="center">0.0</td>

<td align="center">0.0</td>

<td align="center">0.0</td>

<td align="center">16.7</td>

<td align="center">0.0</td>

<td align="center">0.0</td>

<td align="center">0.0</td>

<td align="center">0.0</td>

<td align="center">0.0</td>

<td align="center">0.0</td>

<td align="center">0.0</td>

<td align="center">0.0</td>

<td align="center">1.8</td>

<td align="center">2.0</td>

<td align="center">0.0</td>

</tr>

<tr>

<td>Anger</td>

<td align="center">0.0</td>

<td align="center">0.0</td>

<td align="center">0.0</td>

<td align="center">0.0</td>

<td align="center">0.0</td>

<td align="center">0.0</td>

<td align="center">1.2</td>

<td align="center">0.0</td>

<td align="center">0.0</td>

<td align="center">1.8</td>

<td align="center">1.0</td>

<td align="center">1.9</td>

<td align="center">0.0</td>

<td align="center">1.8</td>

<td align="center">1.0</td>

<td align="center">1.9</td>

</tr>

<tr>

<td>Sadness</td>

<td align="center">0.0</td>

<td align="center">3.6</td>

<td align="center">0.5</td>

<td align="center">0.0</td>

<td align="center">0.0</td>

<td align="center">1.8</td>

<td align="center">1.7</td>

<td align="center">0.0</td>

<td align="center">0.0</td>

<td align="center">0.0</td>

<td align="center">0.5</td>

<td align="center">0.0</td>

<td align="center">0.0</td>

<td align="center">0.0</td>

<td align="center">0.0</td>

<td align="center">0.0</td>

</tr>

<tr>

<td>Fear</td>

<td align="center">0.0</td>

<td align="center">0.0</td>

<td align="center">1.0</td>

<td align="center">0.0</td>

<td align="center">16.7</td>

<td align="center">1.8</td>

<td align="center">0.0</td>

<td align="center">0.0</td>

<td align="center">0.0</td>

<td align="center">1.8</td>

<td align="center">0.0</td>

<td align="center">0.0</td>

<td align="center">0.0</td>

<td align="center">1.8</td>

<td align="center">0.0</td>

<td align="center">0.0</td>

</tr>

<tr>

<td colspan="17" style="line-height: 5px; background-color: #E7FC6D;"> </td>

</tr>

<tr>

<th rowspan="2"> </th>

<th colspan="4">Su1</th>

<th colspan="4">Su2</th>

<th colspan="4">A1</th>

<th colspan="4">A2</th>

</tr>

<tr>

<th>F</th>

<th>S</th>

<th>D1</th>

<th>D2</th>

<th>F</th>

<th>S</th>

<th>D1</th>

<th>D2</th>

<th>F</th>

<th>S</th>

<th>D1</th>

<th>D2</th>

<th>F</th>

<th>S</th>

<th>D1</th>

<th>D2</th>

</tr>

<tr>

<td>Love</td>

<td align="center">0.0</td>

<td align="center">5.3</td>

<td align="center">2.0</td>

<td align="center">0.0</td>

<td align="center">0.0</td>

<td align="center">7.1</td>

<td align="center">3.8</td>

<td align="center">3.8</td>

<td align="center">0.0</td>

<td align="center">3.5</td>

<td align="center">0.0</td>

<td align="center">0.0</td>

<td align="center">4.0</td>

<td align="center">1.8</td>

<td align="center">0.9</td>

<td align="center">2.1</td>

</tr>

<tr>

<td>Joy</td>

<td align="center">5.0</td>

<td align="center">70.2</td>

<td align="center">57.9</td>

<td align="center">50.9</td>

<td align="center">7.7</td>

<td align="center">63.2</td>

<td align="center">66.7</td>

<td align="center">63.3</td>

<td align="center">0.0</td>

<td align="center">24.6</td>

<td align="center">18.6</td>

<td align="center">17.1</td>

<td align="center">4.0</td>

<td align="center">15.9</td>

<td align="center">10.0</td>

<td align="center">12.5</td>

</tr>

<tr>

<td>Surprise</td>

<td align="center">95.0</td>

<td align="center">7.1</td>

<td align="center">13.8</td>

<td align="center">28.3</td>

<td align="center">84.6</td>

<td align="center">10.5</td>

<td align="center">9.2</td>

<td align="center">15.4</td>

<td align="center">0.0</td>

<td align="center">0.0</td>

<td align="center">2.4</td>

<td align="center">1.9</td>

<td align="center">0.0</td>

<td align="center">0.0</td>

<td align="center">1.8</td>

<td align="center">2.1</td>

</tr>

<tr>

<td>Anger</td>

<td align="center">0.0</td>

<td align="center">0.0</td>

<td align="center">5.1</td>

<td align="center">3.8</td>

<td align="center">0.0</td>

<td align="center">0.0</td>

<td align="center">2.5</td>

<td align="center">5.7</td>

<td align="center">8.3</td>

<td align="center">22.9</td>

<td align="center">51.5</td>

<td align="center">41.6</td>

<td align="center">8.0</td>

<td align="center">19.6</td>

<td align="center">21.0</td>

<td align="center">12.6</td>

</tr>

<tr>

<td>Sadness</td>

<td align="center">0.0</td>

<td align="center">1.8</td>

<td align="center">2.0</td>

<td align="center">3.8</td>

<td align="center">0.0</td>

<td align="center">3.6</td>

<td align="center">4.6</td>

<td align="center">3.8</td>

<td align="center">91.7</td>

<td align="center">19.4</td>

<td align="center">10.0</td>

<td align="center">13.3</td>

<td align="center">68.0</td>

<td align="center">24.6</td>

<td align="center">40.1</td>

<td align="center">42.0</td>

</tr>

<tr>

<td>Fear</td>

<td align="center">0.0</td>

<td align="center">10.5</td>

<td align="center">13.3</td>

<td align="center">11.3</td>

<td align="center">7.7</td>

<td align="center">7.0</td>

<td align="center">9.8</td>

<td align="center">7.6</td>

<td align="center">0.0</td>

<td align="center">22.8</td>

<td align="center">15.2</td>

<td align="center">24.6</td>

<td align="center">16.0</td>

<td align="center">19.3</td>

<td align="center">13.7</td>

<td align="center">18.9</td>

</tr>

<tr>

<td colspan="17" style="line-height: 5px; background-color: #E7FC6D;"> </td>

</tr>

<tr>

<th rowspan="2"> </th>

<th colspan="4">Sa1</th>

<th colspan="4">Sa2</th>

<th colspan="4">F1</th>

<th colspan="4">F2</th>

</tr>

<tr>

<th>F</th>

<th>S</th>

<th>D1</th>

<th>D2</th>

<th>F</th>

<th>S</th>

<th>D1</th>

<th>D2</th>

<th>F</th>

<th>S</th>

<th>D1</th>

<th>D2</th>

<th>F</th>

<th>S</th>

<th>D1</th>

<th>D2</th>

</tr>

<tr>

<td>Love</td>

<td align="center">7.1</td>

<td align="center">0.0</td>

<td align="center">3.3</td>

<td align="center">3.8</td>

<td align="center">0.0</td>

<td align="center">5.3</td>

<td align="center">4.7</td>

<td align="center">7.6</td>

<td align="center">0.0</td>

<td align="center">7.1</td>

<td align="center">3.0</td>

<td align="center">3.8</td>

<td align="center">0.0</td>

<td align="center">1.8</td>

<td align="center">1.5</td>

<td align="center">0.0</td>

</tr>

<tr>

<td>Joy</td>

<td align="center">0.0</td>

<td align="center">1.8</td>

<td align="center">2.5</td>

<td align="center">1.9</td>

<td align="center">0.0</td>

<td align="center">3.6</td>

<td align="center">2.6</td>

<td align="center">0.0</td>

<td align="center">0.0</td>

<td align="center">31.6</td>

<td align="center">13.7</td>

<td align="center">19.0</td>

<td align="center">0.0</td>

<td align="center">22.8</td>

<td align="center">7.2</td>

<td align="center">7.6</td>

</tr>

<tr>

<td>Surprise</td>

<td align="center">2.4</td>

<td align="center">0.0</td>

<td align="center">0.0</td>

<td align="center">0.0</td>

<td align="center">0.0</td>

<td align="center">0.0</td>

<td align="center">0.5</td>

<td align="center">1.9</td>

<td align="center">0.0</td>

<td align="center">7.0</td>

<td align="center">1.2</td>

<td align="center">1.9</td>

<td align="center">7.0</td>

<td align="center">5.3</td>

<td align="center">2.7</td>

<td align="center">5.7</td>

</tr>

<tr>

<td>Anger</td>

<td align="center">85.7</td>

<td align="center">3.6</td>

<td align="center">3.4</td>

<td align="center">3.8</td>

<td align="center">50.0</td>

<td align="center">3.6</td>

<td align="center">2.1</td>

<td align="center">1.9</td>

<td align="center">45.0</td>

<td align="center">3.6</td>

<td align="center">8.4</td>

<td align="center">7.6</td>

<td align="center">4.7</td>

<td align="center">0.0</td>

<td align="center">8.1</td>

<td align="center">3.8</td>

</tr>

<tr>

<td>Sadness</td>

<td align="center">0.0</td>

<td align="center">87.9</td>

<td align="center">83.6</td>

<td align="center">86.8</td>

<td align="center">50.0</td>

<td align="center">71.9</td>

<td align="center">79.1</td>

<td align="center">79.4</td>

<td align="center">15.0</td>

<td align="center">21.1</td>

<td align="center">30.9</td>

<td align="center">30.2</td>

<td align="center">0.0</td>

<td align="center">14.1</td>

<td align="center">1.5</td>

<td align="center">1.9</td>

</tr>

<tr>

<td>Fear</td>

<td align="center">4.8</td>

<td align="center">5.3</td>

<td align="center">4.4</td>

<td align="center">1.9</td>

<td align="center">0.0</td>

<td align="center">10.5</td>

<td align="center">6.8</td>

<td align="center">3.8</td>

<td align="center">40.0</td>

<td align="center">24.6</td>

<td align="center">34.5</td>

<td align="center">28.4</td>

<td align="center">88.4</td>

<td align="center">52.6</td>

<td align="center">76.5</td>

<td align="center">81.1</td>

</tr>

<tr>

<td colspan="17" style="line-height: 5px; background-color: #E7FC6D;"> </td>

</tr>

<tr>

<td colspan="17">* Image IDs are based on the tag on the images; L (Love), J (Joy), Su (Surprise), A (Anger), Sa (Sadness), F (Fear)  
The tasks are identified as: F for searching (finding the one most appropriate image for each basic emotion); S for sorting; and >D1 and D2 for describing.</td>

</tr>

</tbody>

</table>

## Discussion

Based on previous studies which demonstrated that emotional perceptions of images are well presented through image related tasks rather than search queries ([Jørgensen 1996](#); [O'Connor _et al._ 1999](#); [Greisdorf and O'Connor 2002](#); [Laine-Hernandez and Westman 2006](#)), the current study examined how emotional perceptions of images are represented through sorting, describing and searching tasks. First, it was found that joy and sadness were dominantly perceived through the sorting and describing tasks. During the sorting task, image viewers tended to distinguish images based on whether images are joyful or sad and then subdivide joyful or sad emotions rather than adopt other basic emotions. In contrast to joy and sadness, surprise was rarely recognized during these two tasks. These results are in accordance with the study by Shaver _et al_. ([1987](#sha87)) which identified two fundamental emotions, positive and negative (or joyful and sad) and had reservations concerning the surprise emotion. Wild, Erb and Bartels ([2001](#wil01)) also demonstrated that happiness, which belongs to the joy category in the study by Shaver _et al_. and sadness are significantly evoked by facial expression. This finding proposes a potential that an emotion-space, which other disciplines (such as psychology, cognitive science and so on) have explored within general environments or using other stimuli, may be applied to an image retrieval environment. Therefore, it would be worthwhile effort to revisit and apply those theories on emotions, with the purpose of improving image retrieval effectiveness.

Although the current study provided participants with a list of comprehensive emotional terms, 20.75% of describing task participants and 17.54% of sorting task participants used terms not listed in the given list. As Ortony and Turner (1990) addressed, there is no entire agreement on the definition and scope of emotions. Therefore, some emotions which are included in one researcher's list are not included in others. For example, Averill (1975) included 558 words in his list, but Shaver _et al_. (1987) included only 135 terms, even though they considered Averill's list. Of the terms not included by Shaver _et al._ but which were selected twice or more by participants (relaxed (relaxing), beautiful, cold, fun, calm, wet, tired, scared, dull, boring, indifference and serenity), it is debatable whether some are emotions (for example, boring and serenity are in Davitz's (1969) list but not in Shaver's list). While terms describing cognitive status are arguable, terms describing objects' status or atmosphere (beautiful, cold and wet) are obviously non-emotional terms.

However, even though theoretically the terms describing objects' status or atmosphere are not included in the list of emotions, if they can be used for providing emotional access they should be considered in image indexing and retrieval systems. Another finding which should be considered in image indexing is that 15% of emotional terms (approximately 20 out of 135) accounted for 50% of the total occurrences of descriptions and labels during the describing and sorting tasks. If it is practically impossible to index a number of subjective and versatile emotional terms during the representation process, terms which are frequently and popularly adopted by users should receive priority. Once images are indexed with popular emotional (and emotion-like) terms, browsing functions which guide users to navigate an emotion-space would help users find images satisfying more specialized and detailed emotional needs.

Further research is needed to decide which emotional terms can be entry points and how those entry points can be expanded or explored while searching. For example, a controlled vocabulary system which includes keyemotional terms and their related emotional terms can be developed and evaluated in terms of image retrieval effectiveness.

Finally, characteristics of the sorting, describing and searching tasks were analysed based on differences of individual image perceptions. Whereas the sorting and describing tasks demonstrated relatively high accordance in emotional perception of an image, the searching task showed different patterns. The author explained the result by the research setting: whereas the sorting and describing tasks asked participants to freely describe and sort images, the searching task forced participants to make relative judgments among images. Since the searching task depends on a relatively small number of data sets, this task may not represent major emotional perceptions of an individual image precisely, even when a participant perceived a strong joyful impression from an image, if the image was the most appropriate for love from twelve images, the participant had to select the image for the searching task looking for love.

However, if a searching task employs an image retrieval system with a reasonably large number of images, the author assumes that the degree of relativity may decrease, which may result in more precise emotional perceptions of images. Based on this finding, it is suggested that when developing a research design it should be taken into account that perceptions of an image can be different depending on the research constraints and whether the image is viewed by itself or compared with other images.

Another finding is that the sorting task demonstrated more diverse emotional perceptions of one image. Jørgensen ([1996](#jof96)) explained the difference between the describing task, in which participants focus on individual images and the sorting task, in which participants see a whole set of images. This could be one explanation for that finding. Another reason that may be infered is that more personal background, preference and intellectual processing are included during the sorting task than in the describing task and this might result in a more diverse interpretation of an image. Therefore, the sorting task seems more appropriate than other tasks to explore the multi-faceted aspects of emotional meanings .

## Conclusion

This study explored emotional perceptions of image documents through three image related tasks: sorting, describing and searching. The sorting and describing tasks demonstrated that joy and sadness are two major categories of emotions which people perceive from images. It was also found there is only a relatively small number of emotional terms frequently chosen as descriptors or labels. It was suggested, therefore, that by assigning emotional index terms using a small number of popular emotional terms, image retrieval effectiveness can be improved with minimum indexing efforts. When comparing image perceptions of an individual image across three tasks, overall similar perceptions were discovered across the sorting, describing and searching tasks.

However, it was noticed that minor differences are caused by the unique characteristics of each task. Therefore, features of each task should be considered in any research design which explores image perceptions. Since a limitation of this study is that image related tasks were conducted with the small number of images by undergraduate students, further research is needed to test these results with a large data set and a more diverse population. Differences of emotional perceptions in terms of demographic features, such as sex, age and ethnicity, might be a topic of future research. In addition, although the current study focused on affective perception of an image, a similar approach could be applied to overall semantic perceptions of images.

## Acknowledgements

This work was supported, in part, by University of South Florida Internal Awards Program under Grant No. R061581\. The author thanks to Ms. Jyoti Deo, a master's student at the University of South Florida, for her assistance in data collection and analysis. The author also thanks to copy-editors of the journal and Ms. Vickie Toranzo Zacker, a master's student at the University of South Florida, for their assistance in enabling the author to satisfy the style requirements of the journal.

## <a name="author" id="author">About the author</a>

JungWon Yoon is an Assistant Professor in the School of Information, University of South Florida. She received her Bachelor's degree in Library and Information Science and Master of Library and Information Science from Ewha Womans University, Seoul, Korea and her PhD from the University of North Texas. She can be contacted at: jyoon@usf.edu.  

#### References

*   Armitage, L.H. & Enser, P.G.B. (1997). Analysis of user need in image archives. _Journal of Information Science_, **23**(4), 287-299.
*   Averill, J. R. (1975). A semantic atlas of emotional concepts. <span style="font-style: italic;">JSAS: Catalog of Selected Documents in Psychology</span>, **5**, 330\. (Ms. No. 421).
*   Börner, K. (2000). Searching for the perfect match: a comparison of free sorting results for images by human subjects and by Latent Semantic Analysis techniques. <span style="font-style: italic;">Proceedings of Fourth International Conference on Information Visualization</span> (pp. 192-197). Washington, DC: IEEE Computer Society.
*   Chen, H. (2001). An analysis of image retrieval tasks in the field of art history. _Information Processing & Management_, **37**(5), 701-720.
*   Choi, Y. & Rasmussen, E. M. (2003). Searching for images: the analysis of users' queries for image retrieval in American history. _Journal of the American Society for Information Science and Technology_, **54**(6), 498-511.
*   Collins, K. (1998). Providing subject access to images: a study of user queries. _The American Archivist_, **61**(1), 36-55.
*   Davitz, J. (1969). <span style="font-style: italic;">The language of emotion</span>. New York, NY: Academic Press.
*   Eakins, J. P., Briggs, P. & Burford, B. (2004). Image retrieval interface: a user perspective. In P. Enser, Y. Kompatsiaris, N.E. O'Connor, A.F. Smeaton & Smeulders, A.W.M. (Eds.), <span style="font-style: italic;">Proceedings, International Conference on Image and Video Retrieval (CIVR 2004)</span>, (pp. 628-637). Berlin: Springer-Verlag. (Lecture Notes on Computer Science: Vol 3115).
*   Enser, P.G.B. & McGregor, C. G. (1992). _Analysis of visual information retrieval queries._ London: The British Library. (British Library Research and Development Report, no. 6104).
*   Goodrum, A. & Spink, A. (2001). Image searching on the Excite Web search engine. _Information Processing and Management_, **37**(2), 295-311.
*   Greisdorf, H. & O'Connor, B. (2002). Modeling what users see when they look at images: a cognitive view point. <span style="font-style: italic;">Journal of Documentation</span>, _58_(1), 6-29.
*   Hollink, L., Schreiber, A.T., Wielinga, B.J. & Worring, M. (2004). Classification of user image descriptions. <span style="font-style: italic;">International Journal of Human-Computer Studies</span>, _61_(5), 601-626.
*   Jørgensen, C. (1995). <span style="font-style: italic;">Image attributes: an investigation</span>. Unpublished dissertation, Syracuse University, Syracuse, New York, United States.
*   Jørgensen, C. (2003). <span style="font-style: italic;">Image retrieval: theory and research</span>. Lanham, MD: Scarecrow Press.
*   Keister, L. (1994). User types and queries: impact on image access systems. In R. Fidel (Ed.), _Challenges in indexing electronic text and images_, (pp. 7-19). Medford, NJ: Learned Information, Inc.
*   Laine-Hernandez, M. & Westman, S. (2006). Image semantics in the description and categorization of journalistic photographs. <span style="font-style: italic;">Proceedings of the 69th Annual Meeting of the American Society for Information Science and Technology</span>, _43_, 1-25.
*   O'Connor, B., O'Connor, M. & Abbas, J. (1999). User reactions as access mechanism: an exploration based on captions for images. <span style="font-style: italic;">Journal of the American Society for Information Science</span>, **50**(8), 681-697.
*   Ortony, A. & Turner, T. (1990). What's basic about basic emotions? <span style="font-style: italic;">Psychological Review</span>, <span style="font-weight: bold;">97</span>(3), 315-331.
*   Rogowitz, B.E., Frese, T., Smith, J.R., Bouman, C.A. & Kalin, E. (1998). Perceptual image similarity experiments. <span style="font-style: italic;">Proceedings of the SPIE conference on Human Vision and Electronic Imaging III</span> (pp. 576-590). Bellingham, WA: SPIE.
*   Rorissa, A. (2005). <span style="font-style: italic;">Perceived features and similarity of images: an investigation into their relationships and a test of Tversky's contrast model.</span> Unpublished dissertation, University of North Texas, Denton, Texas, United States.
*   Rorissa, A. & Hastings, S. (2004). Free sorting of images: attributes used for categorization. <span style="font-style: italic;">Proceedings of the 67th Annual Meeting of the American Society for Information Science and Technology,</span> **41**, 360-366.
*   Rosch, E. (1977). Human categorization. In Neil Warren (Ed.), <span style="font-style: italic;">Advances in cross cultural psychology</span>, **1**, 1-72\. London: Academic Press.
*   Schmidt, S. & Stock, W. (2009). Collective indexing of emotions in images. <span style="font-style: italic;">Journal of the American Society for Information Science and Technology</span>, <span style="font-weight: bold;">_60_</span>(5), 863-876.
*   Shatford-Layne, S. (1994). Some issues in the indexing of images. <span style="font-style: italic;">Journal of the American Society for Information Science</span>, _45_(8), 583-588.
*   Shaver, P., Schwartz, J., Kirson, D. & O'Connor, D. (1987). Emotion knowledge: further exploration of a prototype approach. <span style="font-style: italic;">Journal of Personality and Social Psychology</span>, **52**(6), 1061-1086.
*   Wang, W. & He, Q. (2008). A survey on emotional semantic image retrieval. <span style="font-style: italic;">Proceedings of the 15th IEEEInternational Conference on Image Processing</span> (pp.117-120). Washington, DC: IEEE press.
*   Wild, B., Erb, M. & Bartels, M. (2001). Are emotions contagious? Evoked emotions while viewing emotionally expressive faces: quality, quantity, time course and gender differences. <span style="font-style: italic;">Psychiatry Research</span>, **102**(2), 109-124.

## Appendix

<div align="center">![Appendix](p475fig2.jpg)</div>

Reproduced from Yoon, J. (2010). Utilizing quantitative users' reactions to represent affective meanings of an image. _Journal of the American Society for Information Science and Technology_, **61** (7), 1345-1359.