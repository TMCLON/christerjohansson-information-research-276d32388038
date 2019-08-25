# vol. 16 no. 3, September, 2011


# The effects of discipline on the application of learning object metadata in UK higher education: the case of the Jorum repository

#### [Panos Balatsoukas](#author)  
Department of Computer and Information Sciences, University of Strathclyde, 26 Richmond Street, G1 1XH, Glasgow, UK

#### [Ann O'Brien and Anne Morris](#author)  
Department of Information Science, Loughborough University, Leics, LE11 3TU, UK

#### Abstract

> **Introduction.** This paper reports on the findings of a study investigating the potential effects of discipline (sciences and engineering versus humanities and social sciences) on the application of the Istitute of Electrical and Electronic Engineers learning object metadata elements for the description of learning objects in the Jorum learning object repository.  
> **Method.** A survey was conducted that examined a stratified sample of 470 metadata records and surrogates used for the description of learning objects in the Jorum repository.  
> **Analysis.** A quantitative data analysis was performed based on the sample. This included descriptive statistics as well as a set of Chi squared tests for the identification of differences in the application of learning object metadata elements between disciplines.  
> **Results.** The results of this study showed that some metadata elements tended to be more frequently applied for the description of learning objects in the humanities and social sciences than in sciences and engineering. These were: interactivity type, difficulty, aggregation level, coverage, structure and semantic density.  
> **Conclusions.** The findings of this study could have implications for the design of metadata editors and annotation tools, as well as the development of metadata training programmes.

## Introduction

Metadata can support multiple roles in the provision of e-learning, including the description, management, retrieval and re-usability of learning objects and learning designs, as well as the delivery of on-demand and personalised learning experiences to users. For this purpose, a variety of educational or learning object metadata standards and schemas have been developed, including the Dublin Core Education (DCEd) ([Mason and Sutton 2000](#Mas00)), the IEEE learning object metadata standard ([IEEE... 2002](#Iee02)) (hereafter, 'the IEEE standard'), and the ARIADNE metadata schema ([Najjar _et al._ 2003](#Naj03)). These standards and schemas cover many of the educational, technical and content-related characteristics of learning objects or learning content in general. Apart from an interest in standardisation and metadata schema development, researchers have also investigated the interoperability and technical issues associated with the implementation of learning object metadata in learning object repositories and virtual learning environments ([Sampson _et al._ 2002](#Sam02)) as well as the user aspects that should underpin metadata presentation in the search result interface of these systems ([Balatsoukas _et al._ 2007](#Bal07); [Liddy _et al._ 2003](#Lid03)).

In the United Kingdom, the use of learning object metadata, such as the IEEE's standard, is an important basis for the successful implementation of e-learning systems in higher and further education. For example, the [e-learning programme](http://www.elearning.ac.uk/) of the Joint Information Systems Committee has funded several UK projects on e-learning, some of which have investigated the creation and metadata annotation of learning objects in higher and further education, such as the [RELOAD project](http://www.reload.ac.uk/), the creation of auto-generated learning object metadata, such as the [RepoMMan project](http://www.hull.ac.uk/esig/repomman/), and the establishment of learning object metadata creation workflows, such as the [Jorum project](http://www.jorum.ac.uk/). Research, however, is still in progress on the development of a cross-institutional and UK-wide metadata standard based on the IEEE standard (for example, the UK learning object metadata core is under development by the [Special Interest Group on Metadata and Repositories](http://zope.cetis.ac.uk/profiles/uklomcore/wip/) at the Centre for Educational Technology and Interoperability Standards.

Although the IEEE standard has been an important component of all these efforts, little is known about the level of its uptake and use in UK higher education. For example, there are no studies investigating the level of application of metadata elements of the standard for the description of learning objects in different disciplines. It is anticipated that the investigation of differences in the application of the standard could enhance our understanding about the use of this type of metadata and stimulate further research about the reasons for these differences. Therefore, the aim of this study was to examine the effects, if any, of discipline (sciences and engineering versus humanities and social sciences) on the application of the metadata elements for the description of learning objects in the UK's Jorum learning object repository.

The paper is structured as follows. In the next section, a literature review is presented that elaborates on a definition of the concept of learning object metadata, reviews the IEEE standard and focuses on previous studies that investigated the level of application and uptake of this standard at both a national and international level. The methods developed to address the aim of this study are then presented, followed by the results of this study and the final two sections provide a discussion and some conclusions about the application of learning object metadata.

## Literature review

### Defining learning object metadata

There is no formal definition of learning object metadata or metadata for learning objects. Some authors, including Karampiperis and Sampson ([2003](#Kar03)), argue that metadata for learning objects should support the retrieval of learning objects '_in an educationally efficient and effective way_'. Based on Sicilia's ([2005](#Sic05)) concept of the dual role of metadata as referential and purposeful, it can be assumed that educational efficiency should guide the referential function of learning object metadata (for example, efficiency in terms of cost, time, human resources and technical infrastructure employed for the description (or referencing) of learning objects), while educational effectiveness should guide the purposeful and functional role of metadata (for example, for searching, evaluating, accessing, preserving and using learning objects). By associating this assumption with the general definition of metadata used by Greenberg ([2005](#Gre05)) as '_structured data about an object that supports functions associated with the designated object_', a new definition for learning object metadata can be declared as:

> Structured metadata used for the efficient description of learning objects and the effective support of educational functions related to the described learning objects.

In the context of this paper the term _learning object_ is used to denote an electronic resource created from smaller components (such as data and information objects) and supporting one or more learning objectives ([Balatsoukas _et al._ 2008](#Bal08)). A learning object can be re-used in multiple educational contexts as part of larger modules and courses ([Wiley 2000](#Wil00); [Polsani 2003](#Pol03)).

### The IEEE learning object metadata standard and application profiles

#### The learning object metadata standard

The draft IEEE standard (IEEE 1484.12.1-2002) proposes the structure and semantics of metadata elements used for the description of learning objects. The IEEE Learning Technology Standards Committee has adopted a broad definition of the kind of learning objects that the LOM standard tends to describe, as: '_any entity, digital or non-digital, that may be used for learning education and training_' ([IEEE Learning Technology Standards Committee 2002: 6](#Iee02)). The standard describes various characteristics of a learning object by defining approximately eighty metadata elements, grouped under nine general categories. Table 1 presents a description of the nine categories. For example, the _General_ metadata category includes component elements, such as _Identifier_, _Title_, _Language_, _Description_, _Keywords_, _Coverage_, _Structure_ and _Aggregation Level_ metadata. Some of these elements may also include further sub-component metadata elements. For example, the component element _Identifier_ of the _General_ metadata category, includes the _Catalog_ and _Entry_ sub-components. Data elements that include component data elements are named as aggregate data elements, while leaf data elements are named as simple data elements ([IEEE Learning Technology Standards Committee 2002: 7](#Iee02)). For some data elements vocabularies are defined by the standard, which are useful for assigning values to the metadata elements. All elements are optional, thus a basic core set of metadata elements is not specified. Furthermore, the standard does not provide any recommendations regarding the metadata creation process or the storage and retrieval of metadata within learning object repositories.

The syntax of metadata elements is based on the W3C XML Schema. Some of the benefits related to the use of this particular technology include:

*   interoperability and exchangeability of records across heterogeneous systems and platforms,
*   use of XML namespaces that support the extensibility of learning object metadata with new elements, and
*   better representation and encoding of the hierarchical structure of elements.

<table width="80%" border="1" cellspacing="0" cellpadding="3" align="center" style="border-right: #99f5fb solid; border-top: #99f5fb solid; font-size: smaller; border-left: #99f5fb solid; border-bottom: #99f5fb solid; font-style: normal; font-family: verdana, geneva, arial, helvetica, sans-serif; background-color: #fdffdd"><caption align="bottom">  
**Table 1: The nine metadata categories**  
</caption>

<tbody>

<tr>

<th valign="middle">Metadata category</th>

<th colspan="1">Description of contents</th>

</tr>

<tr>

<td>1\. General</td>

<td align="left">Descriptive information of the learning object as a whole, such as: identifier, title, language, description, keyword, coverage, structure, aggregation level.</td>

</tr>

<tr>

<td>2\. Life-cycle</td>

<td align="left">Elements related to the creation or revision history of the learning object as well as information about those who have contributed to the development, creation, revision of the learning object.</td>

</tr>

<tr>

<td>3\. Meta-metadata</td>

<td align="left">Information regarding the creation of the metadata record.</td>

</tr>

<tr>

<td>4\. Technical</td>

<td align="left">The category consists of elements that describe the technical characteristics of the learning object such as the format, size, location and technical requirements.</td>

</tr>

<tr>

<td>5\. Educational</td>

<td align="left">The educational category aggregates elements regarding pedagogical and educational information about the use of a learning object. Such elements include: Interactivity type, Learning resource type, Interactivity level, Semantic density, Audience or Intended end user role, Context, Typical age range, Difficulty, Typical learning time, Description, Language.</td>

</tr>

<tr>

<td>6\. Rights</td>

<td align="left">The rights category includes information regarding the intellectual property rights and conditions of use of the learning object.</td>

</tr>

<tr>

<td>7\. Relation</td>

<td align="left">The relation category presents information about the relationship of the described learning object with other objects.</td>

</tr>

<tr>

<td>8\. Annotation</td>

<td align="left">The annotation category provides a comment regarding the use of learning objects.</td>

</tr>

<tr>

<td>9\. Classification</td>

<td align="left">The classification category classifies the content of the learning object based on an appropriate classification system.</td>

</tr>

</tbody>

</table>

The learning object metadata standard formed the basis for the development of many nation-wide and project-specific application profiles. Factors that influenced the wide acceptance of this standard include:

*   its characterisation as an ISO standard in 2002;
*   its origins can be traced back to the development of significant European and international projects such as the ARIADNE project ([http://www.ariadne-eu.org/](http://www.ariadne-eu.org/)) and the IMS project ([http://www.imsglobal.org/](http://www.imsglobal.org/));
*   its partial interoperability with Dublin Core;
*   its focus on learning objects; and
*   its ability to cover a wide range of metadata elements.

Some of the most prominent application profiles include the CanCore project in Canada, the UK Learning Object Metadata Core in the UK and the SCORM application profile developed by the US Advanced Distributed Learning project. These profiles adhere to the basic semantic structure of the original standard but contextualise its use by proposing a basic core set of mandatory elements, providing guidelines for using the metadata elements as well as presenting alternative vocabularies for populating metadata elements with values.

#### The UK Learning Object Metadata Core

The UK Learning Object Metadata Core (hereafter, the "UK Core") is based on a revision of the former UK Common Metadata Framework. The latest version of the Core is the draft version 0.2 ([Campbell 2004a](#Cam04a)), but work is in progress for version 0.3 ([Campbell 2004b](#Cam04b)). The UK Core is an application profile of the IEEE standard. It does not propose new elements but specifies a basic minimum set of mandatory elements and includes recommendations and guidelines about the use of these elements in UK higher and further education. In particular, Working draft 0.3 defines twenty-seven data elements as mandatory ([Campbell 2004b](#Cam04b)). The list of mandatory elements, however, should not be perceived as a definite or ultimate list of all elements that might be useful for storing, retrieving and evaluating learning resources and learning objects.

It is worth noting that although the purpose of the UK Core is to support the description of learning objects, elements related uniquely to the structure, granularity, pedagogical context and use of a learning object have not been defined as mandatory elements. The rationale behind this decision was that these elements and their associated vocabularies have not yet been widely implemented and their use is not well understood. The rest of the metadata elements have been defined as either Recommended or Optional. These are: all metadata elements from the _Education_, _Relation_, _Annotation_ and _Classification_ metadata categories as well as the _Coverage_, _Keyword_, _Structure_ and _Aggregation level_ metadata elements from the _General_ metadata category (see Table 1). Finally, the UK Core application profile has been used as a template for the development of other UK-based metadata profiles, such as the Jorum profile.

### The application of learning object metadata

Although metadata standardisation progresses and many communities develop their own metadata schemas and application profiles, the level of uptake of learning object metadata has not been widely investigated. One of the early surveys that examined the level of application of learning object metadata standards in UK higher education revealed that metadata implementation has been monopolised by two standards: the Dublin Core Metadata Elements Set and the IEEE standard ([Currier and Campbell 2005](#Cur05)).

At the individual metadata element level, a survey conducted by the Centre for Educational Technology and Interoperability Standards (CETIS) ([2002](#Cet02)) in the UK and an international survey by CanCore (the Canadian learning resource metadata initiative) ([Friesen and Nirhamo 2003](#Fri03); [Friesen 2004](#Fri04)) revealed an under-utilisation of metadata elements applied for the description of the educational, technical, structural and aggregation level characteristics of learning objects. Both surveys were focused on the use of the IEEE standard. The survey by CETIS was informal and aimed at the identification of useful case studies for further investigation. Thus the survey did not provide a clear answer about the implementation of learning object metadata in the UK. The findings of the international survey by CanCore revealed a high level of use among the elements of the _General_ and _Classification_ categories, such as the _Title_, _Format_, _Language_, _Identifier_, _Keyword_, _Purpose_ and _Taxon path_. Other widely implemented elements were: the _Role_ and _Entity_ elements of the _Contribute_ aggregate metadata element of the _Life cycle_ metadata category, the _Format_ element from the _Technical_ category and the _Learning resource type_ element from the _Educational_ category. These metadata elements occurred in more than 50% of the metadata records under investigation. This survey, however, revealed an under-utilisation of metadata elements related to the educational context of a learning object (for example, _Typical age range_, _Context_, _Typical learning time_, _Difficulty_ and _Semantic density_) as well as elements specifically used to describe the object-oriented or interactive nature of a learning object (such as _Aggregation level_, _Structure_ and _Interactivity level_) ([Friesen 2004](#Fri04)).

The findings of other studies of the application of educational metadata conducted by Godby ([2004](#God04)), Qin and Godby ([2003](#Qin03)) and Sicilia _et al._ ([2005](#Sic05)) were similar. Godby ([2004](#God04)), who tried to update the findings of the CanCore survey, revealed that the majority of metadata elements in the _Educational_, _Technical_ and _Relation_ categories were among the least applied elements. Godby ([2004](#God04)) concluded that the focus of the description of learning objects was centred on the retrieval and discovery of metadata, ignoring the educational-learning scope of metadata standards such as the IEEE standard. Another study ([Qin and Godby 2003](#Qin03)), based on a comparison and synthetic analysis of four metadata schemas (the Ecological Metadata Language, the Gateway to Educational Materials metadata schema, IEEE Learning Object Metadata/IMS Learning Resource Metadata and the Training Exchange Definition metadata), concluded that educational metadata were underrepresented. Qin and Godby ([2003](#Qin03)) argued that there was a lack of metadata elements and vocabularies that expressed different models of learning as well as various types of learning objectives and learning contexts. For this purpose the authors proposed the creation of a learning object ontology with three main classes: learning-models, learning objectives and learning objects. Finally, the study conducted by Sicilia _et al._ ([2005](#Sic05)) provided the same conclusions regarding the use of educational metadata in two learning object repositories, the CAREO repository in Canada, and the MERLOT repository in United States. Sicilia _et al._ ([2005](#Sic05)) also highlighted the need for the provision of better quality and structured educational metadata.

Although these studies revealed an under-utilisation of _Educational_, _Technical_ and _Aggregation Level_ and _Structure_ metadata of the IEEE standard, other researchers such as Najjar _et al._ ([2003](#Naj03)) provide different conclusions in the case of the ARIADNE Knowledge Pool System. According to Najjar _et al._, many educational elements were among the most frequently applied metadata elements in the ARIADNE Knowledge Pool System. These were: the _Granularity_ element (91.9%), _Didactical context_ (53.3%), _Interactivity level_ (52.2%), _Semantic density_ (52.4%) and _Difficulty level_ (52.2%).

From these studies, only Sicilia _et al._ ([2005](#Sic05)) investigated the effects of discipline on the frequency of application of metadata elements. They compared the application of metadata elements across learning objects from five disciplines within the CAREO learning objects repository. The disciplines included were computer science, education, sciences, accounting, medical science and mathematics. The results revealed that many metadata elements were distributed homogeneously across the disciplines. These were the title, description, keywords, the meta-metadata entity element and the keyword metadata element of the classification category. However, metadata elements relating to the author of the learning object (such as _Role_, _Entity_ and _Date_) as well as most elements from the _Meta-metadata_, _Education_ and _Rights_ categories were more frequently used for the description of learning objects from computer science, mathematics and accounting. Metadata elements from the _Annotation_ and _Technical_ categories were more frequently used for the description of learning objects from sciences, medical science and education.

Although Sicilia _et al._ ([2005](#Sic05)) provided some useful insights concerning the application of certain elements, their study is characterized by a focus on the Canadian educational sector (for example, the metadata records under examination were based on CanCore, the Canadian application profile of the IEEE standard), lack of statistical tests for the examination of differences in the application of metadata elements between disciplines, and absence of data about the application of elements between groups of disciplines (e.g., humanities and social science and sciences and engineering). The present paper addresses these gaps by focusing on a UK-based learning object repository and applying statistical tests for the identification of differences, if any, between groups of disciplines in the application of certain metadata elements. In addition, the division of disciplines into two interdisciplinary groups (humanities and social sciences versus sciences and engineering) serves the simple assumption that any differences in the application of learning object metadata elements could be made more clear in the case of groups of disciplines with a different epistemological base, rather than between individual disciplines that are similar in naorganizorganizorganizture. Furthermore, the identification of statistically significant differences at the group level could justify and provide an empirical basis for the initiation of comparative studies between disciplines at the individual- or micro-level. Finally, this study updates the one by Sicilia _et al._ ([2005](#Sic05)) and resets the discourse on the application of metadata elements with an emphasis on the UK higher education sector.

Other researchers such as Zhang and Jastram ([2006](#Zha06)) found differences in the application of metadata elements between professionals from different sectors, including librarians and information technology professionals, as well as between professionals from private and public organizations. In particular, they revealed statistically significant differences in the accuracy and level of application of the keyword and description metadata elements. Information technology professionals tended to apply more metadata elements than librarians. These studies, however, were focused on the metadata (or meta-tags) used in the header of html documents and not on the IEEE standard or any other type of structured learning object metadata schema. Also the researchers investigated differences between groups of professionals by sector rather than by discipline.

## Methods

To address the aim of this study a survey was conducted that examined the metadata records and surrogates used for the description of learning objects in the Jorum repository. A stratified random sample of 470 records was selected. This sampling technique served the representation in the sample of metadata records of learning objects from all subjects (disciplines) covered by the Jorum repository and facilitated the random selection of cases within each stratum.

In the Jorum repository, learning objects are classified under nineteen subject headings for higher education. These subjects represent the classificatory structure of the Jorum repository. For the needs of this study the subjects were categorized into two interdisciplinary groups: 1\. Sciences and engineering, and 2\. Humanities and social sciences. The first group represented disciplines from natural sciences and engineering, such as physics and mathematical sciences, medicine, biology, engineering and technology. The second group included disciplines of humanistic studies as well as disciplines related to the study of society, social phenomena and relations, including economics and business administration. This categorization provides a realistic, flexible and intuitive way of grouping individual disciplines which follows the traditional categorization of academic departments in faculties. The two interdisciplinary categories were:

**A. Sciences and engineering**

1.  Medicine and dentistry
2.  Subjects allied to medicine
3.  Biological sciences
4.  Veterinary sciences
5.  Physical sciences
6.  Mathematical and computer sciences
7.  Engineering
8.  Technologies
9.  Architecture

**B. Humanities and social sciences**

1.  Social sciences
2.  Law
3.  Business and administration
4.  Mass communication and documentation
5.  Linguistics
6.  European languages
7.  Eastern, Asiatic, African and Australian languages and literatures
8.  Historical and philosophical studies
9.  Creative arts and design
10.  Education

Each of the nineteen subject headings represented a stratum (i.e. a subject area). Within each stratum a total number of thirty learning object metadata records were randomly selected for examination. It is worth mentioning, however, that a few subject headings included fewer than thirty learning objects. In these cases all metadata records in the stratum were selected for inclusion in the sample. In a typical Jorum learning object metadata record all elements are hierarchically listed following a parent-child relationship. Metadata elements are grouped in one or more categories of the IEEE standard (see Table 1). Some additional metadata categories, such as digital rights management, are also provided.

The metadata categories under investigation were: _General_, _Life-cycle,_ _Meta-metadata,_ _Technical_, _Educational_, _Rights_, _Relation_, _Annotation_ and _Classification_. In addition, the following Recommended and Optional metadata elements of the IEEE standard were selected for further investigation:

1.  Recommended: Interactivity type, Interactivity level, Learning resource type, Intended end user role, Context, Typical age range, Difficulty, Description (from the educational metadata category).
2.  Optional: Coverage, Structure, Aggregation level, Requirements, Semantic density, Typical learning time (from the General, Technical and Educational metadata categories respectively).

The selection of the particular set of metadata elements was based on the results of previous surveys according to which these were among the least applied metadata elements ([Friesen 2004](#Fri04); [Godby 2004](#God04)). Because of this it was decided to investigate further the impact of the two interdisciplinary categories on the application of these elements in the Jorum repository.

Data collected also included the frequency of application of each metadata category as well as the total number of times a specific element appeared in the sample of records. The data analysis involved the estimation of the frequencies as well as non parametric Chi-squared tests for statistical significance. Non-parametric tests were applied to investigate significant differences in the application of metadata categories and elements between disciplines (sciences & engineering versus humanities & social sciences).

### The Jorum Repository

The Jorum project ([http://www.jorum.ac.uk/](http://www.jorum.ac.uk/)) funded by JISC under the X4L programme aimed to develop a national repository of learning objects for staff across the UK higher and further education. Users of the Jorum repository can either use or contribute learning objects and digital learning material. As part of this process, the Jorum team developed a learning object metadata creation workflow with three main roles. These include the Contributor, the Cataloguer and the Reviewer. The Contributor submits some additional learning object metadata after the upload of a learning object. Then the Cataloguer completes the learning object metadata record, and finally, the Reviewer's role is to revise or reject the metadata record. In addition to the human-generated metadata this workflow supports the creation of some automatically-generated metadata ([Baird 2006](#Bai06)).

For the standardisation of the metadata creation process the Jorum metadata application profile has been developed based on the UK Core version 0.3, which provides a basic minimum set of mandatory metadata elements as well as additional elements that are identified as Recommended or Optional. In addition, the application profile specifies some guidelines and recommendations for the application of these elements and their vocabularies.

It was anticipated that the selection of the sample of metadata records from a nation-wide learning object repository such as Jorum would reflect the cataloguing behaviour of depositors from many UK universities and various disciplines. From a practical point of view, the selection of the particular repository limited the amount of time and resources needed for researchers to obtain a large sample of metadata records.

## Results

Although the sample size of this survey consisted of 470 metadata records, 59 records were excluded from the analysis. These records were incomplete and did not provide an accurate view of the application of certain metadata categories and elements in the Jorum repository. Thus, the results reported in this section derive from the analysis of 411 completed metadata records.

### The effects of discipline on the application of metadata categories

Data analysis revealed consistent application of the mandatory metadata categories across the examined records. For example, the General, Life-cycle, Meta-metadata, Technical, Educational, Rights and Classification metadata categories were present in all 411 metadata. This is not the case, however, for the optional Relation and the recommended Annotation categories. In particular, the Relation metadata category was present in fifteen records and the Annotation category in 124 records.

A set of Pearson's Chi-squared tests was applied in the case of the Relation and Annotation metadata categories to investigate statistically significant differences between the two interdisciplinary categories (sciences and engineering versus humanities and social sciences) in the application of the Relation and Annotation metadata categories. The results revealed that the relation between the application of the Relation metadata category and the type of interdisciplinary category was significant: Chi-squared (1, N= 411) = 19.21, p = <0.0005\. In particular, the Relation metadata category was more frequently applied in the case of metadata records describing learning objects from a science or engineering discipline. The association, however, was of weak strength (Phi-value = 0.216) thus, the type of discipline for which the metadata record was created for accounted only for 4.7% of the variance in the frequency of use of the Relation metadata element.

Similarly, the relation between the application of the Annotation metadata category and the type of discipline was significant: Chi-squared (1, N= 411) = 35.36, p = <0.0005\. In this case, however, the Annotation metadata category tended to be more frequently applied in records that described learning objects from the humanities and social sciences. Again, the association was of weak strength (Phi-value = 0.293) and accounted for 8.6% of the variance in the frequency of use of the Annotation metadata category between the two interdisciplinary categories.

The contingency tables (Tables 2 and 3) present the weak but significant relation between the application of the Relation and Annotation metadata categories and the two interdisciplinary categories. The Relation metadata category was applied in fifteen records of the sciences and engineering group and never applied in humanities and social sciences. The Annotation metadata category was present in nintety-six records from the humanities and social sciences group and in only twenty-eight records from the sciences and engineering group.

<table width="60%" border="1" cellspacing="0" cellpadding="3" align="center" style="border-right: #99f5fb solid; border-top: #99f5fb solid; font-size: smaller; border-left: #99f5fb solid; border-bottom: #99f5fb solid; font-style: normal; font-family: verdana, geneva, arial, helvetica, sans-serif; background-color: #fdffdd"><caption align="bottom">  
**Table 2: 2*2 contingency table for the Relation metadata category**  
</caption>

<tbody>

<tr>

<th></th>

<th>Applied</th>

<th>Not Applied</th>

<th>Row Total</th>

</tr>

<tr>

<td>Sciences and engineering</td>

<td align="center">15</td>

<td align="center">169</td>

<td align="center">184</td>

</tr>

<tr>

<td>Humanities and social sciences</td>

<td align="center">0</td>

<td align="center">227</td>

<td align="center">227</td>

</tr>

<tr>

<td>Total</td>

<td align="center">15</td>

<td align="center">396</td>

<td align="center">411</td>

</tr>

</tbody>

</table>

<table width="60%" border="1" cellspacing="0" cellpadding="3" align="center" style="border-right: #99f5fb solid; border-top: #99f5fb solid; font-size: smaller; border-left: #99f5fb solid; border-bottom: #99f5fb solid; font-style: normal; font-family: verdana, geneva, arial, helvetica, sans-serif; background-color: #fdffdd"><caption align="bottom">  
**Table 3: 2*2 contingency table for the Annotation metadata category**  
</caption>

<tbody>

<tr>

<th></th>

<th>Applied</th>

<th>Not Applied</th>

<th>Row Total</th>

</tr>

<tr>

<td>Sciences and engineering</td>

<td align="center">28</td>

<td align="center">156</td>

<td align="center">184</td>

</tr>

<tr>

<td>Humanities and social sciences</td>

<td align="center">96</td>

<td align="center">131</td>

<td align="center">227</td>

</tr>

<tr>

<td>Total</td>

<td align="center">124</td>

<td align="center">287</td>

<td align="center">411</td>

</tr>

</tbody>

</table>

### Results of the application of metadata elements

The results showed that almost all Recommended elements of the Jorum metadata application profile were frequently applied to the description of learning objects (_Interactivity type_, _Interactivity level_, _Learning resource type_, _Intended end user role_, _Context_, _Difficulty_ and _Description_) (see Table 4). Most of these elements were present in more than 400 records. This result contradicts previous studies, which revealed an under-utilisation of the particular elements in the creation of learning object records (Friesen 2004). This observation, however, does not hold for the recommended _Typical age range_ element which was present in fewer (361) records.

While all but one of the recommended elements were frequently applied across the sample records, this is not the case for the optional elements which were not frequently applied (see Table 4). In particular, the three elements of the General metadata category (_Coverage_, _Aggregation level_ and _Structure_) and the two elements of the Education metadata category (_Semantic density_ and _Typical learning time_) were applied in less than forty and sixty records respectively. Finally, the _Technical requirements_ element of the Technical metadata category was present in fifty-eight records.

<table width="60%" border="1" cellspacing="0" cellpadding="3" align="center" style="border-right: #99f5fb solid; border-top: #99f5fb solid; font-size: smaller; border-left: #99f5fb solid; border-bottom: #99f5fb solid; font-style: normal; font-family: verdana, geneva, arial, helvetica, sans-serif;background-color: #fdffdd;"><caption align="bottom">  
**Table 4: Application of metadata elements**  
</caption>

<tbody>

<tr>

<th>Recommended elements</th>

<th>Frequency</th>

<th>%</th>

</tr>

<tr>

<td>Interactivity type</td>

<td align="center">403</td>

<td align="center">98.1</td>

</tr>

<tr>

<td>Interactivity level</td>

<td align="center">408</td>

<td align="center">99.3</td>

</tr>

<tr>

<td>Learning resource type</td>

<td align="center">408</td>

<td align="center">99.3</td>

</tr>

<tr>

<td>Intended end user role</td>

<td align="center">408</td>

<td align="center">99.3</td>

</tr>

<tr>

<td>Context</td>

<td align="center">410</td>

<td align="center">99.8</td>

</tr>

<tr>

<td>Typical age range</td>

<td align="center">361</td>

<td align="center">87.8</td>

</tr>

<tr>

<td>Difficulty</td>

<td align="center">397</td>

<td align="center">96.6</td>

</tr>

<tr>

<td>Description</td>

<td align="center">405</td>

<td align="center">98.5</td>

</tr>

<tr>

<th>Optional elements</th>

<th>Frequency</th>

<th>%</th>

</tr>

<tr>

<td>Coverage</td>

<td align="center">21</td>

<td align="center">5.1</td>

</tr>

<tr>

<td>Aggregation level</td>

<td align="center">13</td>

<td align="center">3.2</td>

</tr>

<tr>

<td>Structure</td>

<td align="center">36</td>

<td align="center">8.8</td>

</tr>

<tr>

<td>Semantic density</td>

<td align="center">60</td>

<td align="center">14.6</td>

</tr>

<tr>

<td>Typical learning time</td>

<td align="center">58</td>

<td align="center">14.1</td>

</tr>

<tr>

<td>Technical requirements</td>

<td align="center">59</td>

<td align="center">14.4</td>

</tr>

</tbody>

</table>

#### The effects of discipline on the application of metadata elements

##### _The application of 'Recommended' elements across disciplines_

As shown in Table 5, all Recommended elements under investigation were more frequently applied for the description of learning objects from the humanities and social sciences. A set of Pearson's Chi-squared tests, however, were conducted to examine whether there was a significant impact of the interdisciplinary category on the application of the elements under investigation.

<table width="80%" border="1" cellspacing="0" cellpadding="3" align="center" style="border-right: #99f5fb solid; border-top: #99f5fb solid; font-size: smaller; border-left: #99f5fb solid; border-bottom: #99f5fb solid; font-style: normal; font-family: verdana, geneva, arial, helvetica, sans-serif; background-color: #fdffdd"><caption align="bottom">  
**Table 5: The application of Recommended metadata elements between disciplines**  
</caption>

<tbody>

<tr>

<th rowspan="3" valign="middle">Type of element</th>

<th colspan="4">Disciplines</th>

</tr>

<tr>

<th colspan="2">Humanities and social sciences</th>

<th colspan="2">Sciences and engineering</th>

</tr>

<tr>

<th>f</th>

<th>% within discipline</th>

<th>f</th>

<th>% within discipline</th>

</tr>

<tr>

<td>Interactivity type</td>

<td align="center">226</td>

<td align="center">99.6</td>

<td align="center">177</td>

<td align="center">96.2</td>

</tr>

<tr>

<td>Interactivity level</td>

<td align="center">227</td>

<td align="center">100</td>

<td align="center">181</td>

<td align="center">98.4</td>

</tr>

<tr>

<td>Learning resource type</td>

<td align="center">227</td>

<td align="center">100</td>

<td align="center">181</td>

<td align="center">98.4</td>

</tr>

<tr>

<td>Intended end user role</td>

<td align="center">226</td>

<td align="center">99.1</td>

<td align="center">182</td>

<td align="center">98.9</td>

</tr>

<tr>

<td>Context</td>

<td align="center">227</td>

<td align="center">100</td>

<td align="center">183</td>

<td align="center">99.5</td>

</tr>

<tr>

<td>Typical age range</td>

<td align="center">200</td>

<td align="center">88.1</td>

<td align="center">161</td>

<td align="center">87.7</td>

</tr>

<tr>

<td>Difficulty</td>

<td align="center">224</td>

<td align="center">98.7</td>

<td align="center">173</td>

<td align="center">94</td>

</tr>

<tr>

<td>Description (Educational)</td>

<td align="center">223</td>

<td align="center">98.2</td>

<td align="center">182</td>

<td align="center">98.9</td>

</tr>

</tbody>

</table>

Table 6 presents the results of the Chi-squared tests performed in the case of each Recommended element. The results revealed that there was a relationship between the application of the _Interactivity type_ and _Difficulty_ elements and interdisciplinary category. These elements tended to be more frequently applied for the description of learning objects from humanities and social sciences. It is worth mentioning, however, that the associations observed were of weak strength (Phi-value < 0.2). No significant relationships were observed in the case of the remaining metadata elements.

<table width="60%" border="1" cellspacing="0" cellpadding="3" align="center" style="border-right: #99f5fb solid; border-top: #99f5fb solid; font-size: smaller; border-left: #99f5fb solid; border-bottom: #99f5fb solid; font-style: normal; font-family: verdana, geneva, arial, helvetica, sans-serif; background-color: #fdffdd"><caption align="bottom">  
**Table 6: Table of Chi Squared tests for 'Recommended' elements**  
</caption>

<tbody>

<tr>

<th>Metadata element by discipline type</th>

<th>No. of cases</th>

<th>Value</th>

<th>DF</th>

<th>p value</th>

</tr>

<tr>

<td>Interactivity type</td>

<td align="center">411</td>

<td align="center">N/A</td>

<td align="center">N/A</td>

<td align="center">**0.025***</td>

</tr>

<tr>

<td>Interactivity level</td>

<td align="center">411</td>

<td align="center">N/A</td>

<td align="center">N/A</td>

<td align="center">0.093**</td>

</tr>

<tr>

<td>Learning resource type</td>

<td align="center">411</td>

<td align="center">N/A</td>

<td align="center">N/A</td>

<td align="center">0.093**</td>

</tr>

<tr>

<td>Intended end user role</td>

<td align="center">411</td>

<td align="center">N/A</td>

<td align="center">N/A</td>

<td align="center">0.6**</td>

</tr>

<tr>

<td>Context</td>

<td align="center">411</td>

<td align="center">N/A</td>

<td align="center">N/A</td>

<td align="center">0.45**</td>

</tr>

<tr>

<td>Typical age range</td>

<td align="center">411</td>

<td align="center">0.35</td>

<td align="center">1</td>

<td align="center">0.85</td>

</tr>

<tr>

<td>Difficulty</td>

<td align="center">411</td>

<td align="center">6.7</td>

<td align="center">1</td>

<td align="center">**0.01****</td>

</tr>

<tr>

<td>Description</td>

<td align="center">411</td>

<td align="center">N/A</td>

<td align="center">N/A</td>

<td align="center">0.7*</td>

</tr>

<tr>

<td colspan="5">* These cases are significant at the 0.05 (5%) level according to the Pearson's chi-squared tests.  
** Fisher's exact significance (2-sided) test was selected (in each of these cases two cells had and expected count of less than 5).</td>

</tr>

</tbody>

</table>

##### The application of 'Optional' elements across disciplines

Similarly, the Pearson's Chi-squared tests performed in the case of the optional elements revealed significantly higher level of application of the _Coverage_, _Aggregation level_, _Structure_ and _Semantic density_ elements for the description of learning objects from the humanities and social sciences (see Table 7). The strength of these relationships, however, was weak (Phi-value <0.2). No significant differences were observed in the case of the _Typical learning time_ and _Technical requirements_ elements. The level of application of these elements tended to be similar across the two subject categories. Finally, Figure 1 provides a graphical representation of the level of application (percentage of application within each interdisciplinary category) of all optional elements of this study between humanities and social sciences and sciences and engineering categories.

<table width="80%" border="1" cellspacing="0" cellpadding="3" align="center" style="border-right: #99f5fb solid; border-top: #99f5fb solid; font-size: smaller; border-left: #99f5fb solid; border-bottom: #99f5fb solid; font-style: normal; font-family: verdana, geneva, arial, helvetica, sans-serif; background-color: #fdffdd"><caption align="bottom">  
**Table 7: Table of Chi-squared tests for Optional elements**  
</caption>

<tbody>

<tr>

<th>Metadata element by discipline type</th>

<th>No. of cases</th>

<th>Value</th>

<th>DF</th>

<th>p value</th>

</tr>

<tr>

<td>Aggregation level</td>

<td align="center">411</td>

<td align="center">7.5</td>

<td align="center">1</td>

<td align="center">**0.006***</td>

</tr>

<tr>

<td>Coverage</td>

<td align="center">411</td>

<td align="center">5.9</td>

<td align="center">1</td>

<td align="center">**0.015***</td>

</tr>

<tr>

<td>Semantic density</td>

<td align="center">411</td>

<td align="center">9.3</td>

<td align="center">1</td>

<td align="center">**0.002***</td>

</tr>

<tr>

<td>Structure</td>

<td align="center">411</td>

<td align="center">10.2</td>

<td align="center">1</td>

<td align="center">**0.001***</td>

</tr>

<tr>

<td>Technical requirements</td>

<td align="center">411</td>

<td align="center">2.35</td>

<td align="center">1</td>

<td align="center">0.13</td>

</tr>

<tr>

<td>Typical learning time</td>

<td align="center">411</td>

<td align="center">0.08</td>

<td align="center">1</td>

<td align="center">0.8</td>

</tr>

<tr>

<td colspan="5">* These cases are significant at the 0.05 (5%) level according to the Pearson's chi-squared tests.</td>

</tr>

</tbody>

</table>

<div align="center">![Optional Elements](p481fig1.png)</div>

<div align="center">  
**Figure 1: The application of Optional elements between disciplines (% within disciplines)**  
</div>

## Discussion

In general, the results of this study seem to suggest that the level of obligation (Recommended or Optional) is more a critical factor in the frequency of use of learning object metadata than the disciplinary category to which the metadata elements are assigned. However, in both cases (level of obligation and interdisciplinary category) some exceptions were observed. For example, in the case of the level of obligation, the recommended _Typical age range_ element was not consistently applied for the description of learning objects in both disciplinary categories. This can be justified by the fact that this element is characterised by the inconsistent application of vocabulary values. For example, according to the Jorum metadata application profile, the _Typical age range_ refers to the chronological age of a user group ([Stevenson 2005](#Ste05)). In practice, however, the assignment of values for the particular element range from chronological values, such as _16+_, to values associated to the educational level of the intended end-user group, such as _teacher_ and _undergraduate students_.

In the case of the effects of disciplinary category on the use of learning object metadata elements, the results showed a consistent use of most Recommended and Optional metadata elements in the disciplines . These include: the _General_, _Life-cycle_, _Meta-metadata_, _Technical_, _Education_, _Rights_ and _Classification_ categories, and the _Technical requirements_, _Interactivity level_, _Typical learning time_, _Intended end user role_, _Learning resource type_, _Context_, _Typical age range_ and _Description_ elements. This finding supports the results of a previous study by Sicilia _et al._ ([2005](#Sic05)) who found no statistically significant differences in the application of metadata elements across disciplines and also that there is a general subset of metadata elements that is commonly used for the description of learning objects. However, the data analysis was conducted at the level of individual scientific disciplines ([Sicilia _et al._ 2005](#Sic05)) and not at the dichotomous and compound level of sciences and engineering versus humanities and social sciences (as in the present study).

Differences in the use of some metadata between the two interdisciplinary categories were observed in the following cases:

1.  Metadata that tended to be more frequently used for the description of learning objects from the humanities and social sciences were the _Annotation_ category, and the _Interactivity type_, _Difficulty_, _Aggregation level_, _Coverage_, _Structure_ and _Semantic density_ elements.
2.  Metadata that tended to be more frequently used for the description of learning objects from the sciences and engineering disciplines was the _Relation_ metadata category.

These differences represent weak, but statistically significant, associations between specific metadata elements or categories of metadata elements and interdisciplinary groups. Although there is no evidence in the literature about why this phenomenon occurs, the following assumptions can be made:

*   Different characteristics of learning objects from sciences and engineering and from humanities and social sciences. For example, differences in the frequency of use of the _Relation_ category could be attributed to the fact that lecturers from a sciences and engineering background tend to associate their learning objects with other external resources more frequently than those from humanities and social sciences.
*   Differences in the cataloguing practices between teachers or contributors of learning objects from sciences and engineering and from humanities and social sciences. These differences may be related to the importance they attach to certain learning object metadata for the description of learning objects. For example, contributors of learning objects from humanities and social sciences may perceive the use of the _Annotation_ category for the description of learning objects to be more important than contributors from sciences and engineering.
*   Differences in cataloguing training between contributors of learning objects from sciences and engineering and from humanities and social sciences. The difference in the use of metadata elements between the two disciplinary categories could be attributed to the amount and quality of training received by the contributors of learning objects in the Jorum repository. For example, this could be the case for the _Semantic density_, _Aggregation level_ and _Interactivity type_ elements which have been widely criticised in the past for semantic ambiguity and problems in their application without training.

The future investigation of these assumptions could provide in-depth knowledge about the way learning object metadata elements are applied for the description of learning objects from different disciplines. However, another question arising from this discussion is whether the application (or lack of application) of certain learning object metadata elements can have an impact on the use of learning object repositories by teachers and students from different disciplines. This question is related to the concept of metadata completeness that is defined as '_the extent to which the metadata record of the learning object provides the necessary metadata to properly support a given process or activity_' (Sicilia _et al._ 2005). Users can interact with learning object repositories at different levels, each level representing a different process or activity. These can include:

1.  The search for learning objects using learning object metadata fields.
2.  The selection of learning objects (relevance judgment based on the retrieved learning object metadata surrogates).

These processes or activities can facilitate several educational objectives, such as the re-use of learning objects by teachers or the facilitation of learning for students. For example, teachers can select learning objects for inclusion in lessons or whole courses based on _Interactivity type_ or _Typical age range_. Similarly, students can select learning objects according to their _Intended end user role_ or the _Learning resource type_. Therefore, it can be assumed that the lack of complete learning object metadata records can impede the efficiency and effectiveness of the learning experience ([Morris _et al._ 2007](#Mor07)). For example, Balatsoukas _et al._ ([2007](#Bal07)) found that students with a science background (information and computer sciences) were interested in metadata elements about the audience (_Intended end user role_) and _Interactivity_ when judging the relevance of learning objects. The absence of these metadata elements could frustrate learners and increase their cognitive load.

In the case of the Jorum repository this problem could be more evident for learning objects from sciences and engineering, where metadata elements such as _Interactivity type_, _Annotation_, _Intended end user role_ or _Learning resource type_ were applied less frequently and inconsistently when compared to learning objects from humanities and social sciences. The reasons for the low application of these metadata elements can be attributed to their semantic ambiguity and the lack of appropriate and user-centred vocabularies ([Campbell 2004b](#Cam04b); [Godby 2004](#God04)).

For example, participants in the UK [SearchLT project](http://searchlt.engineering.ac.uk/) faced problems when using specific metadata elements (from an application profile) for the creation of metadata records for learning objects in engineering ([Barker and Barker 2003](#Bar03)). These included the _Technical requirements_ element (it was difficult for cataloguers to describe the technical requirements), the _Educational_ elements (which requires specialist knowledge on pedagogy), and the _Interactivity type_ element (which was found confusing). Many of these elements were applied less frequently for the description of learning objects from a science or engineering discipline in the case of the Jorum repository (see Table 5). There is no strong empirical evidence, however, that differences between disciplines (such as diverse teaching and learning traditions, the nature and interactivity of learning objects, and the level of familiarisation and training with learning objects and learning object metadata) account for any inconsistencies in the application of certain learning object metadata elements. Researchers suggest the need for more research in this area ([Kay and Lum 2004](#Kay04)).

## Conclusions

The results of this study showed that an effect of disciplinary category (sciences and engineering and humanities and social sciences) was evident in the frequency of use of only a few metadata elements and categories of metadata elements. The _Annotation_ category tended to be used more frequently for the description of learning objects from humanities and social sciences while the _Relation_ category was more often used in the case of disciplines from sciences and engineering . At the metadata element level, the _Interactivity type_, _Difficulty_, _Aggregation level_, _Coverage_, _Structure_ and _Semantic density_ elements occurred more frequently in records describing learning objects from the humanities and social sciences. However, the results showed that the majority of metadata elements and categories of metadata under investigation were applied consistently across the two disciplinary groups.

Although the results followed the execution of a sound methodological design, which involved random representation of metadata records from all disciplines included in the Jorum repository as well as objective data collection and analysis though the use of statistical tests, they should be interpreted with caution. For example, the categorization of disciplines as humanities and social sciences and sciences and engineering could have obscured the unique characteristics of individual disciplines. That is, differences in the application of metadata elements could have been observed between disciplines that occurred within the same disciplinary category. Furthermore, this research limited its focus only to certain learning object metadata elements, i.e., most of the elements of the _Educational_ category and a selection of elements which, according to previous international studies, are less frequently used for the description of learning objects.

Setting aside these limitations, the present research (the first of its kind in the UK) provides new knowledge about the level of application and uptake of certain learning object metadata elements in the UK higher education. In addition, the findings reported in this paper can be used as a basis for further investigation. For instance, future research should examine the reasons why specific metadata elements tend to be used more frequently for the description of learning objects in the respective discpline groups. Furthermore, follow-up studies could strengthen the generalisability of the findings reported in this paper by examining the frequency of use of metadata elements across individual disciplines and larger samples of metadata records as well as across other learning object repositories in the UK.

## About the authors

Panos Balatsoukas is a Research Fellow in the Department of Computer and Information Sciences, University of Strathclyde, Glasgow. His research interests include information retrieval, user-centered design of information systems and relevance judgment on the web. He can be contacted at: [panos@cis.strath.ac.uk](mailto:panos@cis.strath.ac.uk)

Ann O'Brien is a Lecturer in the Department of Information Science, Loughborough University, UK. Her research interests include information organization and retrieval, metadata and taxonomies. She can be contacted at: [A.O-brien@lboro.ac.uk](A.O-brien@lboro.ac.uk)

Anne Morris is a Professor of Information Science in the Department of Information Science, Loughborough University, UK. Her research interests include e-learning, e-metrics and economic valuation of information services, electronic books, the evaluation of information services, the impact of information technology on end-users, electronic document delivery, library ergonomics including health and safety issues and the strategic management of academic libraries. She can be contacted at: [A.Morris@lboro.ac.uk](mailto:A.Morris@lboro.ac.uk)

#### References

*   Baird, K. (2006). [_Automated metadata: A review of existing and potential metadata automation within Jorum and an overview of other automation systems._](http://www.webcitation.org/60jKdg958) Retrieved 8 August, 2011 from http://www.jorum.ac.uk/squeezy/site/docs/pdf/automated_metadata_report.pdf (Archived by WebCite at http://www.webcitation.org/60jKdg958)
*   Balatsoukas, P., Morris, A. & O'Brien, A. (2007).[Designing metadata surrogates for search result interfaces of learning object repositories: linear versus clustered metadata design.](http://www.webcitation.org/60jMNC21K) In Leslie Chan and Bob Martens (Eds.), _Openness in digital publishing: awareness, discovery and access - Proceedings of the 11th International Conference on Electronic Publishing_, ELPUB 2007, Vienna, Austria, June 3rd to 15th, 2007 (pp. 415-424). Vienna: Technical University of Vienna. Retrieved 8 August, 2011 from http://www.iadis.net/dl/final_uploads/200811L002.pdf (Archived by WebCite at http://www.webcitation.org/60jMNC21K)
*   Balatsoukas, P., Morris, A. & O'Brien, A. (2008). [Learning objects update: review and critical approach to content aggregation.](http://www.webcitation.org/60jMJYySn) _Journal of Educational technology and society_, **11**(2), 119-130\. Retrieved 8 August, 2011 from http://www.ifets.info/journals/11_2/11.pdf (Archived by WebCite at http://www.webcitation.org/60jMJYySn)
*   Barker, E. & Barker, P. (2003). [_Case studies in implementing educational metadata standards: SearchLT: an online catalogue of engineering learning resources for UK HE_](http://www.webcitation.org/60jKpmj6n). Bolton, UK: JISC Cetis. Retrieved 8 August, 2011 from http://metadata.cetis.ac.uk/usage_survey/cs_searchlt.pdf (Archived by WebCite at http://www.webcitation.org/60jKpmj6n)
*   Campbell, L.M. (2004a). [_UK learning object metadata core: draft 0.2_](http://www.webcitation.org/60jL1noYA). Bolton, UK: JISC Cetis. Retrieved 8 August, 2011 from http://metadata.cetis.ac.uk/profiles/uklomcore/uklomcore_v0p2_may04.doc (Archived by WebCite at http://www.webcitation.org/60jL1noYA)
*   Campbell, L. M. (2004b). [_UK Learning object metadata core: working draft, version 0.3_12042_](http://www.webcitation.org/60jL7qNCZ). Bolton, UK: JISC Cetis. Retrieved 8 August, 2011 from http://metadata.cetis.ac.uk/profiles/uklomcore/wip/uklomcore_v0p3_1204.doc (Archived by WebCite at http://www.webcitation.org/60jL7qNCZ)
*   CETIS (2002). [_Survey of educational metadata use_](http://www.webcitation.org/60jLC7UQ0). Bolton, UK: JISC Cetis. Retrieved 8 August, 2011 from http://metadata.cetis.ac.uk/usage_survey/ed_md_survey_2002-07-29.pdf (Archived by WebCite at http://www.webcitation.org/60jLC7UQ0)
*   Currier, S., & Campbell, L.M. (2005). Evaluating 5/99 content for reusability as learning objects. _VINE: The journal of information and knowledge management systems_, **35**(1/2), 85-96.
*   Friesen, N. (2004). [_International learning object metadata survey_](http://www.webcitation.org/60jLH9VLY). _International Review of Research in Open and Distance Learning_, **5**(3). Retrieved 8 August, 2011 from http://www.irrodl.org/index.php/irrodl/article/view/195/277 (Archived by WebCite at http://www.webcitation.org/60jLH9VLY)
*   Friesen, N. & Nirhamo, L. (2003). [_Survey of learning object metdata implementation: preliminary report_](http://www.webcitation.org/60jLKnfnJ). Retrieved 8 August, 2011 from http://www.estandard.no/docs/Survey_of_LOM_Implementations_Lassi.doc (Archived by WebCite at http://www.webcitation.org/60jLKnfnJ)
*   Godby, C. J. (2004). [What do application profiles reveal about the learning object metadata standard?](http://www.webcitation.org/60jLOq4CK) _Ariadne_, **41**. Retrieved 8 August, 2011 from http://www.ariadne.ac.uk/issue41/godby/ (Archived by WebCite at http://www.webcitation.org/60jLOq4CK)
*   Greenberg, J. (2005). Metadata and the World Wide Web. In _Encyclopedia of library and information science_ (pp. 1876-1888). New York, NY: Marcel Dekker.
*   Karampiperis, P. & Sampson, D. (2003). Enhancing educational metadata management systems to support interoperable learning object repositories. In _Proceedings of the 3rd IEEE International Conference on Advanced Learning Technologies, 9-11 July, 2003, Athens, Greece._ (pp. 214-218). Los Alamitos, CA: IEEE.
*   Kay, J. & Lum, A. (2004). Building user models from observations of users accessing multimedia learning objects. In A. Nuernberger and N. Detyniecki (Eds.), _Adaptive multimedia retrieval_ (pp. 36-57). Berlin: Springer.
*   Liddy, E.D., Allen, E.E., Finneran, C.M., Gay, G., Hembrooke, H. & Granka, L.A. (2003). MetaTest: evaluation of metadata from generation to use. In _Proceedings 2003 Joint Conference on Digital Libraries_ (p. 398). New York, NY: IEEE Press.
*   IEEE Learning Technology Standards Committee. (2002). [_Draft standard for learning object metadata_](http://www.webcitation.org/60jLU7DwS). New York, NY: IEEE. (IEEE 1484.12.1-2002). Retrieved 8 August, 2011 from http://ltsc.ieee.org/wg12/files/LOM_1484_12_1_v1_Final_Draft.pdf (Archived by WebCite at http://www.webcitation.org/60jLU7DwS)
*   Mason, J. & Sutton, S. (2000). [_Education Working Group: draft proposal_](http://www.webcitation.org/60jLXlZpY). Singapore: Dublin Core Metadata Initiative Ltd. Retrieved 8 August, 2011 from http://dublincore.org/documents/education-namespace/ (Archived by WebCite at http://www.webcitation.org/60jLXlZpY)
*   Morris, A., O'Brien, A. & Balatsoukas, P. (2007). User-centred learning object metadata for effective and efficient e-learning environments. _ERCIM News_, No. 71, 21-22.
*   Najjar, J., Duval, E., Ternier, S. & Neven, F. (2003). [Towards interoperable learning object repositories: the ARIADNE experience](http://www.webcitation.org/60jLcLTXU). In Pedro Isaias and Nitya Karmahav (Eds.), _Proceedings of the IADIS International Conference WWW/Internet, Algarve, Portugal, 5-8 November 2003_, (pp. 219-226). Lisbon: IADIS. Retrieved 8 August, 2011 from http://www.iadis.net/dl/final_uploads/200302L028.pdf (Archived by WebCite at http://www.webcitation.org/60jLcLTXU)
*   Najjar, J., Ternier, S. & Duval, E. (2003). [The actual use of metadata in ARIADNE: an empirical analysis](http://www.webcitation.org/60n73oQSk). In _Proceedings of ARIADNE 3rd International Conference_. Retrieved 8 August, 2011 from http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.93.3666&rep=rep1&type=pdf (Archived by WebCite at http://www.webcitation.org/60n73oQSk)
*   Polsani, P. R. (2003). [Use and abuse of reusable learning objects](http://www.webcitation.org/60jLj4Hov). _Journal of digital information_, **3**(4). Retrieved 8 August, 2011 from http://journals.tdl.org/jodi/article/viewArticle/89/88 (Archived by WebCite at http://www.webcitation.org/60jLj4Hov)
*   Qin, J. & Godby, C. J. (2003). Incorporating educational vocabulary in learning object metadata schema. In T. Koch and I.T. Solvberg (Eds.), _Proceedings of the 7th European Conference on Digital libraries_ (pp. 52-57). Berlin: Springer.
*   Sampson, D., Karagiannidis, C., Schenone, A. & Cardinali, F. (2002). Knowledge-on-Demand in e-Learning and e-Working settings. _Educational Technology & Society_, **5**(2), 107-112.
*   Sicilia, M.A., Garcia, E., Pages, C., Martinez, J.J. & Guttierez, J.M. (2005). Complete metadata records in learning object repositories: some evidence and requirements. _International Journal of Learning Technology_, **1**(4), 411-424.
*   Stevenson, A. (2005). [_JORUM application profile_](http://www.webcitation.org/60jMC11sy). Retrieved 8 August, 2011 from http://www.scribd.com/doc/209179/Jorum-Application-Profile-draft-version-10 (Archived by WebCite at http://www.webcitation.org/60jMC11sy)
*   Wiley, D.A (2000). [Connecting learning objects to instructional design theory: a definition, a metaphor, and a taxonomy](http://www.webcitation.org/60jLztXRS). In D.A. Wiley (Ed.), _The instructional use of learning objects (online version)_. Retrieved 8 August, 2011 from http://reusability.org/read/chapters/wiley.doc (Archived by WebCite at http://www.webcitation.org/60jLztXRS)
*   Zhang, J. & Jastram, I. (2006). A study of the metadata creation behavior of different user groups on the internet. _Information Processing and Management_, **42**, 1099-1122.