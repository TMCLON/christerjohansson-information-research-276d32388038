#### Vol. 6 No. 2, January 2001



# Converting a controlled vocabulary into an ontology: the case of GEM

#### [Jian Qin](mailto:jqin@syr.edu) & [Stephen Paling](mailto:swpaling@syr.edu)  
School of Information Studies  
Syracuse University  
Syracuse, New York, USA

#### Abstract

> The prevalance of digital information raised issues regarding the suitability of conventional library tools for organizing information. The multi-dimensionality of digital resources requires a more versatile and flexible representation to accommodate intelligent information representation and retrieval. Ontologies are used as a solution to such issues in many application domains, mainly due to their ability explicitly to specify the semantics and relations and to express them in a computer understandable language. Conventional knowledge organization tools such as classifications and thesauri resemble ontologies in a way that they define concepts and relationships in a systematic manner, but they are less expressive than ontologies when it comes to machine language. This paper used the controlled vocabulary at the Gateway to Educational Materials (GEM) as an example to address the issues in representing digital resources. The theoretical and methodological framework in this paper serves as the rationale and guideline for converting the GEM controlled vocabulary into an ontology. Compared to the original semantic model of GEM controlled vocabulary, the major difference between the two models lies in the values added through deeper semantics in describing digital objects, both conceptually and relationally.

## Introduction

Ontologies, as a form of knowledge representation, are defined as a systematic account of existence, a specification of a conceptualization ([Gruber](#Gruber93a), 1993a). They represent a domain of discourse, and allow for relationships such as the definition of classes, relations, and functions. Despite their high level of specification of these classes and relationships, ontologies also allow a great deal of flexibility. Among the more flexible possibilities are the sharing and reuse of ontologies, and the ability to accommodate varying descriptive terms. In the context of metadata for digital library objects, ontologies are specified in the form of definitions of representational vocabulary. Conventional representational vocabularies used in libraries include cataloguing codes as embodied in MAchine Readable Cataloguing (MARC), thesauri or subject heading lists, and classification schemes. There is a clear functional distinction between such vocabularies. Thesauri and classifications, on the one hand, are used to represent the subject content of a book, journal article, a film, or any form of recorded knowledge, though they also contain a limited number of terms for document formats and genre. Semantic relationships among different concepts are reflected through broader terms, narrower terms, and related terms in thesauri, and a hierarchical structure in classification schemes. On the other hand, because a thesaurus is a subject content rich vocabulary, it does not handle descriptive data (title, author, publisher, etc.) object well. Libraries use separate representational vocabularies for the descriptive data such as Anglo-American Cataloging Rules 2nd ed. (AACR2) to meet the need for descriptive representation.

The prevalance of digital information resources raised several issues for conventional representational vocabularies. Firstly, digital objects, as those in the Gateway to Educational Materials (GEM, [http://www.thegateway.org/](http://www.thegateway.org/)) collections, encompass multiple dimensions of characteristics and such characteristics often play important roles for users in search for precise information in an efficient manner. For example, a lesson plan of arithmetic for fifth graders may contain information on pedagogy, class activities, math games, test samples, educational standards for fifth grade mathematics curriculum; as a digital object, it may include text, images, audio/video clips; and it may be a parent object of a collection of child objects or a child object of a parent object. A conventional cataloguing code will be inadequate to describe these details in a lesson plan, for many of these elements do not even exist in the vocabulary. Secondly, different metadata schemes are used to represent digital objects in different domains. When an information repository has heterogeneous digital objects, interoperability becomes the first obstacle to provide access to these resources. A library catalogue system may not be able to translate a record from a museum or a library MARC record can not be recognized by an Internet-based information gateway system. Finally, more and more systems today use agents and other intelligent applications to improve information search performance. While such capabilities are hard to implement directly within the metadata records, it seems to make more sense if we create agents that bear the concept models with deeper semantics. Such effort does not have to start from scratch, but rather, can make use of the knowledge structure and vocabularies in classifications and thesauri and add values to these representations.

Ontologies are in a right position to address these issues. The fundamental difference between an ontology and a conventional representational vocabulary is the level of abstraction and relationships among concept. In this paper, we report the conversion of the GEM controlled vocabulary into an ontology, which is the first step in a larger project towards an ontology-driven information gateway for educational materials. The current study discusses the preliminary planning and steps involved in converting the existing GEM vocabulary to an ontology. The purpose of the conversion is not only to reduce the duplication of effort involved in building an ontology from scratch by using the existing vocabulary, but also to establish a mechanism for allowing differing vocabularies to be mapped onto the ontology. [Soergel](#Soergel99) (1999) drew connections between ontologies and other methods of classification, pointing out that ontological and lexical structures underpin much scientific and scholarly work. He criticises scholars in scientific communities for not communicating more effectively with each other about their classifications, and laments the fact that the intellectual capital of classification schemes and thesauri is often ignored. This project also attempts to avoid this problem. It uses the existing capital represented by the GEM scheme, and makes it available not just for automated processing at GEM, but also to other communities who choose to take up the structure of the ontology. The following sections include an introduction to GEM's background, a literature review of formal ontologies and applications, conversion considerations, and the constructs of GEM ontology.

## Background of GEM

GEM is an initiative of the US Department of Education's National Library of Education (NLE) to expand educators' capability to access Internet-based lesson plans, curriculum units and other educational materials ([Sutton](#Sutton1999), 1999). There are over 14,500 metadata records in the GEM database as of this writing. Its resources come from more than 100 collections, including AskERIC Virtual Library, Math Forum, Microsoft Encarta, North Carolina Department of Public Instruction, and U.S. Department of Education. GEM acquires indexing records through distributed cataloguing that uses a proprietary cataloguing system. The software contains an interface that allows GEM cataloguers to enter metadata under the 15 Dublin Core Metadata Elements (short for Dublin Core or DC) from the Online Computer Library Center (OCLC) and 8 local elements that are designed specifically for the resources covered by GEM (Table 1). Elements with an asterisk in Table 1 describe the subject content of a resource, among which the _Subject_ element allows two types of vocabulary: the GEM controlled vocabulary and the keywords selected by metadata creators. Box 1 shows a typical GEM cataloguing record. Note that the _Description, Subject,_ and _Title_ elements contain information on what the resource is about. In the _Subject_ element, GEM requires metadata creators to include a level one subject from the GEM Subject Vocabulary ([Morgan](#Morgan1999), 1999). Other elements such as _Audience, Grade,_ and _Pedagogy_ include information on what and whom the resource is for, which can play important roles in narrowing down a search when querying the database. Box 1 shows an example of a GEM metadata record, where the two-levelled subject terms were selected from the GEM Controlled Vocabulary, and the keywords extracted by metadata creators from the resource.

<table align="center" border="" cellspacing="0" cellpadding="0" width="60%" bgcolor="#FFFFFF" style="border-collapse:collapse; border:none;mso-border-alt:solid windowtext .5pt;mso-padding-alt:0in 5.4pt 0in 5.4pt"><caption align="bottom">Table 1: Data elements for GEM indexing records</caption>

<tbody>

<tr>

<td valign="top" colspan="2" style="border:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt">

<center>**Elements from Dublin Core**</center>

</td>

<td valign="top" width="40%" style="border:solid windowtext .5pt;border-left:none;
  mso-border-left-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt">

<center>**Elements from GEM**</center>

</td>

</tr>

<tr valign="top">

<td style="border-top:none;border-left:solid windowtext .5pt;border-bottom:
  solid windowtext .5pt;border-right:none;mso-border-top-alt:solid windowtext .5pt;
  padding:0in 5.4pt 0in 5.4pt">

<div style="text-indent:0in;line-height:normal">DC.Contributor</div>

<div style="text-indent:0in;line-height:normal">DC.Coverage</div>

<div style="text-indent:0in;line-height:normal">DC.Creator</div>

<div style="text-indent:0in;line-height:normal">DC.Date</div>

<div style="text-indent:0in;line-height:normal">DC.Description*</div>

<div style="text-indent:0in;line-height:normal">DC.Format</div>

<div style="text-indent:0in;line-height:normal">DC.Identifier</div>

<div style="text-indent:0in;line-height:normal">DC.Language</div>

</td>

<td valign="top" style="border-top:none;border-left:none;border-bottom:solid windowtext .5pt;
  border-right:solid windowtext .5pt;mso-border-top-alt:solid windowtext .5pt;
  padding:0in 5.4pt 0in 5.4pt">

<div style="text-indent:0in;line-height:normal">DC.Publisher</div>

<div style="text-indent:0in;line-height:normal">DC.Relation</div>

<div style="text-indent:0in;line-height:normal">DC.Rights</div>

<div style="text-indent:0in;line-height:normal">DC.Source</div>

<div style="text-indent:0in;line-height:normal">DC.Subject*</div>

<div style="text-indent:0in;line-height:normal">DC.Title*</div>

<div style="text-indent:0in;line-height:normal">DC.Type</div>

</td>

<td valign="top" style="border-top:none;border-left:none;border-bottom:solid windowtext .5pt;
  border-right:solid windowtext .5pt;mso-border-top-alt:solid windowtext .5pt;
  mso-border-left-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt">

<div style="text-indent:0in;line-height:normal">GEM.Audience</div>

<div style="text-indent:0in;line-height:normal">GEM.Cataloging</div>

<div style="text-indent:0in;line-height:normal">GEM.Duration</div>

<div style="text-indent:0in;line-height:normal">GEM.EssentialResources</div>

<div style="text-indent:0in;line-height:normal">GEM.Grade</div>

<div style="text-indent:0in;line-height:normal">GEM.Pedagogy</div>

<div style="text-indent:0in;line-height:normal">GEM.Quality</div>

<div style="text-indent:0in;line-height:normal">GEM.Standards</div>

</td>

</tr>

</tbody>

</table>

<div align="center">* Indicates elements that are used to tell what a resource is about.</div>

<table align="center" border="" cellspacing="0" cellpadding="0" width="75%"><caption align="bottom">Box 1\. A sample GEM metadata record</caption>

<tbody>

<tr>

<td valign="top" width="50%" bgcolor="#FFFFFF" style="border:.75pt solid black;vertical-align:top;background:white">**Title:** Eyes on the Sky, Feet on the Ground: Hands On Astronomy Activities for Kids

<div style="margin-left:1.0in;text-indent:-1.0in;line-height:
    normal">**Description:** This resource contains hundreds of fun explorations into astronomy as a classroom tool for learning how to theorise, experiment, and analyze data. The activities are fully illustrated and contain detailed, step-by-step instructions as well as suggested discussion topics. </div>

<div style="margin-left:1.0in;text-indent:-1.0in;line-height:
    normal">**Grade Levels:** 2 3 4 5 6</div>

<div style="line-height:normal">                       * </div>

<div style="text-indent:0in;line-height:normal">**GEM Subjects:** Science--Astronomy</div>

<div style="line-height:normal">Science--Physics</div>

<div style="line-height:normal">Science--Space Sciences</div>

<div style="line-height:normal">Science--Technology</div>

<div style="text-indent:0in;line-height:normal">**Keywords:**Orbit, Time, Calendar, Maps, Solar system, Moon, Rotation </div>

<div style="text-indent:0in;line-height:normal">**GEM Audience: **</div>

<div style="line-height:normal">    Tool For: Teachers </div>

<div style="line-height:normal">    Beneficiary: Students </div>

</td>

<td valign="top">

<div style="text-indent:0in;line-height:normal">

<div style="text-indent:0in;line-height:normal">**Pedagogy:**</div>

<div style="line-height:normal">    Teaching Method: Hands-on learning</div>

<div style="text-indent:0in;line-height:normal">    Multiple activities  
**Resource Type:** Collection </div>

</div>

<div style="text-indent:0in;line-height:normal">**Format:** text/HTML </div>

<div style="text-indent:0in;line-height:normal">**Relation:**</div>

<div style="text-indent:0in;line-height:normal">**Rights Management:**</div>

<div style="line-height:normal">    Cost: free </div>

<div style="text-indent:0in;line-height:normal">**Date:** Record Created: 2000-04-13T01:45:39-5:00 </div>

<div style="text-indent:0in;line-height:normal">**Publisher:**</div>

<div style="line-height:normal">     Name: Harvard-Smithsonian Center for Astrophysics, High Energy Astrophysics Division </div>

<div style="line-height:normal">     Role: onlineProvider </div>

<div style="line-height:normal">     Homepage: http://hea-www.harvard.edu/ </div>

<div style="text-indent:0in;line-height:normal">**cataloguing Agency:**</div>

<div style="line-height:normal">     Name: GEM </div>

<div style="line-height:normal">     Version: 3.2</div>

<div style="line-height:normal">     Homepage: http://www.geminfo.org</div>

</td>

</tr>

</tbody>

</table>

The GEM controlled vocabulary is resource-oriented (Figure 1), i.e., it defines the categories (classes) and subcategories (subclasses) of information that are included in educational resources. Among other classes that describe the many physical/medium attributes for a resource, the subject class encompasses a typical curriculum in the US elementary and secondary schools, which has a two level subdivisions--subclass and concept names. Currently, the GEM controlled vocabulary is used as a metadata scheme for representing the multiple dimensions for digital educational objects. The GEM system provides access to these multi-dimensions by using Boolean operators through the search interface. Though this controlled vocabulary integrates the descriptive data elements with subject categories, it is difficult to achieve a higher level of representation of these digital objects (such as games, test samples, and classroom activities in a math lesson plan) and the relationships among and in the digital objects. This difficulty manifests a need for a more systematic abstraction that will explicitly specify the concepts as well as the relationship between these concepts.

<div align="center">![](p94fig1.gif)</div>

<div align="center">Figure 1\. The hierarchy of GEM controlled vocabulary</div>

## Formal Ontologies and Ontological Applications

Researchers in the areas of knowledge representation have debated the nature of ontologies in the last few decades. In general, "[a]n ontology is an explicit specification of a conceptualization" ([Gruber](#Gruber1993), 1993). While Gruber's definition is widely cited, there have been questions about the meaning of conceptualization. [Guarino](#Guarino1997) (1997) argues that an ontology is "not a specification of a conceptualization, but a (possibly incomplete) agreement about a conceptualization." He further states that:

> An ontology is a logical theory accounting for the intended meaning of a formal vocabulary, i.e. its ontological commitment to a particular conceptualization of the world. The intended models of a logical language using such a vocabulary are constrained by its ontological commitment. An ontology indirectly reflects this commitment (and the underlying conceptualization) by approximating these intended models. ([Guarino](#Guarino1998),1998)

When ontologies are used at system development time, they get transformed and translated into an information system component, thus reduce the costs of conceptual analysis in system development; when used at run time, ontologies enables communication between software agents (ontology-driven communication). Guarino also demonstrates in his paper how ontologies affect the architecture of information systems. Thus, to be more accurate, an ontology is a partial specification of a shared conceptualization, to be used for formulating knowledge-level theories about a domain ([Domingue and Motta](#Domingue99), 1999).

Various formal analysis methods provide a wide range of choices for modelling the "world." One of the main purposes of formal analysis is to investigate the logical properties of concepts and their relations. [Goasdoue and Reynaud](#Goasdou99) (1999) used semantic concept skeletons to identify and model relevant concepts. The process involves the use of the Entity-Relationship model to generate semantic concepts, which, in turn, is used to group entities and relationships. Conceptual structures can also be modelled as a hierarchical network in the form of a mathematical lattice ([Priss](#Priss1998), 1998). The main purpose of formal concept analysis is to define a formal model in which there exists a set of formal objects _G_, a set of formal attributes _M_, and a relation _I_ between _G_ and _M._ For example, in the context of a lesson plan, {arithmetic, test}={accelerated} is a formal concept. A formal concept does not necessarily define a topic (i.e., subject); it may well be used to specify a process. The University Michigan Digital Library (UMDL) ontology ([Weinstein](#Weistein98), 1998) delineates the process of publications from the birth of an idea to the final product as 6 formal concepts: conception; expression; manifestation; materialization, digitization; and instance. For each of these concepts, the UMDL ontology maps elements in the descriptive schema, MAchine Readable cataloguing (MARC), with either "has" or "of" or "kind-of" or "extends" relationship.

Different kinds of ontologies are developed to serve different levels of generality. [Guarino](#Guarino1998) (1998) proposes that ""top-level" ontologies describe all general concepts such as space, time, matter, object, event, action, and so forth; domain ontologies and task ontologies describe, respectively, the vocabulary related to a generic domain (like medicine, or automobiles) or a generic task or activity (like diagnosing or selling), by specializing the terms introduced in the top-level ontology; and application ontologies describe concepts depending both on a particular domain and task, which are often specializations of both the related ontologies. The ontology library at Stanford University Knowledge Systems Laboratory ([http://www-ksl.stanford.edu/](http://www-ksl.stanford.edu/)) contains many examples of these kinds.

The ultimate goal of developing ontologies is to enhance information representation and information retrieval systems. The Web provides a perfect test-bed for ontology-driven applications ranging from information extraction to information retrieval. [Embley, _et al._](#Embley98) (1998) built an ontology-based system for extracting information from data-rich, unstructured documents. They define "data-rich" documents as those having a number of identifiable constants such as dates, names, account numbers, ID numbers, part numbers, times, and currency values. With such a narrow ontology breadth, an application ontology can be modelled by object-oriented analysis. The application ontology was mainly used to generate SQL tables. In this sense, their application ontology functions as a database schema. Another system dealing with the similar type of documents is OntoSeek developed by [Guarino](#Guarino99), _et al._ (1999), which targets content-based information retrieval from online yellow pages and product catalogues. Unlike Embley _et al._'s information extraction system, they used linguistic tools such as WordNet ([http://www.cogsci.princeton.edu/~wn/](http://www.cogsci.princeton.edu/~wn/)) and Penman to avoid building the ontology from scratch. OntoSeek utilizes ontology not only at the encoding level but also the end-user level. Ontology has also been used to build Web agents ([Luke](#Luke97), et al., 1997) to add semantics to HTML in order to define attributes and relationships in machine-readable form, and to map Web sites for information exploration ([Zhu](#Zhu99), et al., 1999).

The above discussion of formal ontologies and ontological applications reveals an intrinsic relationship of ontological commitments with thesauri and classifications that have long tradition in the library and information science communities. While classifications play an increasingly important role in knowledge representation and discovery ([Kwasnik](#Kwasnik99), 1999), a practical question for converting a controlled vocabulary into an ontology is: What is the added value of an ontology compared to the knowledge representation vocabularies used in libraries and information industries? The answer is given in the next section.

## Design Considerations

[Gruber](#Gruber93b) (1993b) discusses ontologies as design artefacts, and outlines a set of design criteria to guide ontology development. These criteria are:

*   **Clarity**: Definitions should be objective, free of social or computational context, and documented with natural language.
*   **Coherence**: The defining axioms should be logically consistent and sanction inferences consistent with the definitions.
*   **Extendibility**: The ontology should anticipate new used of the shared vocabulary.
*   **Minimal encoding bias**: Encoding bias occurs when a choice of representation is made simply for the convenience of notation. The conceptualization should be specified at he knowledge level without depending on a particular symbol-level encoding.
*   **Minimal ontological commitment**: An agent is said to commit to an ontology when its actions are consistent with the ontology's definitions. An ontology should make a minimal number of claims about the world being modelled. ([Gruber,](#Gruber93b) 1993b).

This study maintains that while these criteria serve as useful guides, they do not apply uniformly to all ontology projects. The conversion of an existing vocabulary brings with it certain assumptions that vary from the criteria. For example, we diverge from the views of clarity being expressed. Because we are converting terms already defined in a social context, we do not believe that they can be defined independently of that context. The terms define different facets of Internet resources used for education, and the definitions are constructed in service of the people who use the resources. Because the facets are relatively independent, they will not be connected by a large number of axioms. Taking the above criteria into account, the ontology must have the following added values compared to the existing vocabulary:

1.  Higher levels of conception of descriptive vocabulary;
2.  Deeper semantics for class/subclass and cross-class relationships;
3.  Ability to express such concepts and relationships in a description language; and
4.  Reusability and "share-ability" of the ontological constructs in heterogeneous systems.

**_Higher levels of conception._** Current GEM controlled vocabulary represents digital objects in the sense of its "whole"," i.e., similar to a library cataloguing record that describes the object by its overall characteristics. But from a GEM user survey, we found that blocks within a digital object whole are frequently the ones that users are looking for. When we represent the information contained in a lesson plan, simply labelling it as "lesson plan" would not give users much valuable information on its test samples, interactive games, in-class activities, or the state standard it relates to. An ontology would enrich the representation vocabulary for such information blocks.

**_Deeper semantics for class/subclass and cross-class relationships._** Converting an existing vocabulary into an ontology does not simply mean adding more classes or subclasses to it. The relationships have to be explicitly specified between these classes. When we define a math lesson plan, it is important to indicate that it has game(s) or relates to standard(s), and how these contents are related.

**_Description language for concepts and their relationships._** A formal description language is based on Description Logic (DL) that is used to describe situations using various kinds of _individuals_ (as _instance_ in a collection of objects), related by _roles_ (as _relation)_, and grouped into _concepts_ (a _primitive_ specified elsewhere) ([Brachman et al.](#Brachman99), 1999_)_. The real significance of a formal description language is for the representation to have the ability to reason about descriptions.

**_Reusability and "share-ability" of the ontology._** If teachers, administrators, and researchers are to share educational knowledge, they must share more than a common vocabulary of previously identified terms; they must delineate the relationships among the objects in the world to which the terms refer. Ontologies describe formal descriptions of objects in the world, the properties of those objects, and the relationships among them. Hence, the value that they add to existing vocabularies such as thesauri or classification schemes is additional information that defines how objects can be classified and related to one another.

In addition to these value-added considerations, there are considerations relating to methodology for the conversion. Two aspects of any knowledge representation process have direct implications to this study: structuring and linguistic ([Bièbow and Szulman](#Bièbow99), 1999). The structuring aspect refers to the way a concept has been introduced into a model, e.g., bottom-up or top-down, and the linguistic aspect pertains to the linguistic accuracy of a concept. In GEM's situation where a structure is already in place, it makes it a natural choice to use the top-down approach to building the GEM concept model. For the linguistic accuracy, GEM controlled vocabulary is adopted whenever possible. If a new term or concept needs to be added, the educational thesaurus would be consulted.

## The GEM Ontology

We used the Ontolingua system (http://www-ksl-svc.stanford.edu:5915/) at Stanford's Knowledge Systems Laboratory (http://www-ksl.stanford.edu/) to create the ontology. Ontolingua provides a development environment for ontology construction. In addition to editing tools, it allows the creation of modular, combinable ontologies.

Because the GEM controlled vocabulary was already in existence, our task was simplified. The following schematic shows the proposed GEM ontology:

<table align="center" border="" cellspacing="0" width="85%"><caption align="bottom">**Table 2: The GEM ontology first order relationships**</caption>

<tbody>

<tr>

<td>

<div class="MsoNormal">**Top-Level Class**</div>

</td>

<td>

<div class="MsoNormal">**Slot**</div>

</td>

<td>**Relation**</td>

<td>

<div class="MsoNormal">**Example**</div>

</td>

</tr>

<tr>

<td valign="top">Resource</td>

<td>Audience</td>

<td>_resource_ For-Audience _slot_  
_slot_ Audience-Of _resource_</td>

<td valign="top">_LessonPlan_ For-Audience _Teachers_  
_Teachers_ Audience-Of _LessonPlan_</td>

</tr>

<tr>

<td> </td>

<td>

<div class="MsoNormal">Educational Level</div>

</td>

<td>_resource_ For-EducationalLevel_slot_  
_slot_ EducationalLevel-Of_resource_</td>

<td valign="top">_LessonPlan_ For-EducationalLevel _elementary_  
_elementary_ EducationalLevel-Of _LessonPlan_</td>

</tr>

<tr>

<td> </td>

<td>

<div class="MsoNormal">Format</div>

</td>

<td>_resource_ In-Format _slot_  
_slot_ Format-Of _resource_</td>

<td valign="top">_LessonPlan_ In-Format _html_  
_html_ Format-Of _LessonPlan_</td>

</tr>

<tr>

<td> </td>

<td>

<div class="MsoNormal">Grade</div>

</td>

<td>_resource_ For-Grade_slot_  
_slot_ Grade-Of_resource_</td>

<td valign="top">_LessonPlan_ For-Grade _03_  
_03_ Grade-Of _LessonPlan_</td>

</tr>

<tr>

<td> </td>

<td>

<div class="MsoNormal">Language</div>

 </td>

<td>_resource_ In-Language _slot_  
_slot_ Language-Of _resource_</td>

<td valign="top">_LessonPlan_ In-Language _english_  
_english_ Language-Of _LessonPlan_</td>

</tr>

<tr>

<td> </td>

<td>

<div class="MsoNormal">Pedagogy </div>

</td>

<td>

<div class="MsoNormal">_resource_ Used-For_slot_</div>

<div class="MsoNormal">_slot_ Use-Of _resource_</div>

</td>

<td valign="top">_Exam_ Used-For _assessment_  
_assessment_ Use-Of _Exam_</td>

</tr>

<tr>

<td valign="top"> </td>

<td valign="top">

<div class="MsoNormal">Relation Type</div>

</td>

<td valign="top">

<div class="MsoNormal">_resource_ Has-RelationType _slot1_ [_slot2_]</div>

<div class="MsoNormal">_slot2_ Related-To _resource_ by _slot1_</div>

</td>

<td valign="top">_LessonPlan_ Has-Relation _IsOverviewOf_ _multiplication tables_  
_multiplication tables_ Related-To _LessonPlan_ by _IsOverviewOf_</td>

</tr>

<tr>

<td> </td>

<td>

<div class="MsoNormal">Subject </div>

</td>

<td>

<div class="MsoNormal">_resource_ Is-About _slot_</div>

<div class="MsoNormal">_slot_ Subject-Of _resource_</div>

</td>

<td valign="top">_LessonPlan_ Is-About _multiplication_  
_multiplication_ Subject-Of _LessonPlan_</td>

</tr>

</tbody>

</table>

A slot represents an attribute of a class in an ontology. For example, a lesson plan class might have title, author, subject, audience, grade level, format, and language as slots. A slot has value and value type. Teacher is one of the values for slot Audience, Mathematics-Geometry is a value for slot Subject, and so forth. These values are typically _string_ type. Theoretically, the value for slots may be a class (such as Audience that may be modelled as a class), a Boolean operator, a number, or a symbol. Apart from the taxonomic relationships between classes, a full-fledged ontology attaches properties or slots to classes, where a subclass inherits the slots from all of its (direct or indirect) super-classes. In a class hierarchy, inheritance proceeds simultaneously along multiple paths. Using a math lesson plan for high school students as an example, the diagram below demonstrates the semantic model of the ontology:

<div align="center">![](p94fig2.gif)</div>

<div align="center">Figure 2\. A semantic model for lesson plans</div>

In this example, the lesson plan, Measuring the Earth, inherits all the slots from its super-classes. That is, as a resource, it bears properties of the Resource class, and as a lesson plan, it contains a special set of slots pertaining to lesson plans only. The _Subject_ slot is linked to an external knowledge structure because of the complexity and amount of vocabulary involved.

Most of the descriptions involve simple first-order relationships. Each descriptive element is relatively independent, so the individual subclasses have no necessary relationships expressed in the ontology. Most of the relationships are simple statements about a particular descriptive element, such as _Language_ and _Pedagogy_. The most complicated is _Relation Type_. In the GEM controlled vocabulary, the following relation types are available:

<table align="center" cols="2" width="60%">

<tbody>

<tr>

<td>

*   hasBibliographicInforIn
*   isAgencyReview
*   isChildOf
*   isContentRatingFor
*   isCriticalReviewOf
*   isDataFor
*   isDerivedFrom
*   isOveriewOf

</td>

<td>

*   isParentOf
*   isPeerReviewisQualityScore
*   isRevisionHistoryFor
*   isSiblingOf
*   isSiteCriteria
*   isSourceOf
*   isSponsoredBy
*   isStandardsMappingOf

</td>

</tr>

</tbody>

</table>

These terms present a mix of first- and second-order relationships. Expressing this requires three elements: the subclass for the resource itself, a slot for the relation type, and a second, optional, slot for the entity constituting the second half of the relationship. The slots must also have their _cardinality_ defined. Cardinality governs the number of possible values a slot can have, and the cardinality is defined as the minimum and maximum number of values. The first slot has a minimum and maximum cardinality of one, i.e., it cannot be empty, and it can only hold one value. The second slot has a minimum cardinality of zero and a maximum cardinality of one. It can be empty in the case of first-order relationships, and can take a single value if necessary to express a second-order relationship. For example:

<table align="center" border="" cellspacing="0" width="70%"><caption align="bottom">**Table 3\. Examples of first order and second order relationships**</caption>

<tbody>

<tr>

<td align="center">**Example**</td>

<td align="center" valign="top">**Relationship**</td>

</tr>

<tr>

<td>Developing Geometry Concepts Using Computer Programming Environments _<font color="#990000">Is-an-instance-of</font>_Activity

Activity _<font color="#990000">Is-a-subclass-of</font> _Resource

Activity _<font color="#990000">Has-RelationType</font> _<font color="#000000">IsSponsoredBy</font><font color="#006600">National Council of Teachers of Mathematics</font>

Project _<font color="#990000">Has-RelationType</font>_ <font color="#000000">IsSiteCriteria</font>

Course _<font color="#990000">Has-RelationType</font> _<font color="#000000">IsDerivedFrom</font><font color="#006600">Exemplary and Promising Mathematics Programs</font>

</td>

<td valign="top">First-order

First-order

Second-order

First-order

Second-order

</td>

</tr>

</tbody>

</table>

This structure accomplishes a number of goals. It leaves the essential flexibility of the GEM vocabulary intact. The resource serves as the parent class, and subclasses can be repeated to enrich a description. Ontolingua allows an ontology to be exported in LISP code, and this adds an important dimension by formalizing relationships in ways that will make the records more easily manipulable by retrieval agents. The relatively simple structure of the ontology reflects the underlying simplicity of the controlled vocabulary.

## Conclusions and Future Research

The theoretical and methodological framework described in this paper serves as the rationale and guideline for converting the GEM controlled vocabulary into an ontology.  Compared to the original semantic model of GEM controlled vocabulary, the major difference between the two models lies in the values added through deeper semantics in describing digital objects, both conceptually and relationally. Unlike most of ontological effort that made no reference to controlled vocabularies created by the librarians and information scientists, this study recognized the importance of connecting existing knowledge structures as well as the difficulty in implementing such structures in ontologies. Since the purpose of this ontology is to describe digital objects in the GEM repository, their characteristics become central to the ontology. From an information architecture point of view, the ontology promotes standardization and reusability of information representation through identifying characteristics common to all digital objects for the top class and subsets of characteristics common only to one particular subclass of objects.

As a continuing effort, GEM ontology components will continue to be built under the current framework. The future research will look into problems such as cross-class relationships (which class is to be used as a slot of which class under what condition), develop templates for representing differing digital object classes, and eventually, implement the ontology into the GEM system for the purposes of enriched representation of digital objects and intelligent information retrieval.

## References

*   <a name="Bièbow99"></a>Bièbow, B. and Szulman, S. (1999) "TERMINAE: a linguistic-based tool for the building of domain ontology", in: _Knowledge Acquisition, Modeling, and Management: 11th European Workshop, EKAW '99 Proceedings_, edited by D. Fensel and R. Studer. Berlin: Springer.  pp. 49-66.
*   <a name="Brachman99"></a>Brachman, R.J., McGuinness, D.L., Patel-Schneider, P.F., and Borgida, A. (1999) "'Reducing' CLASSIC to practice: knowledge representation theory meets reality". _Artificial Intelligence,_ **114**, 203-237.
*   <a name="Domingue99"></a>Domingue, J. and Motta, E. (1999) "A knowledge-based news server supporting ontology-driven story enrichment and knowledge retrieval," in: _Knowledge Acquisition, Modeling and Management: 11th European Workshop, EKAW '99 Proceedings_, edited by D. Fensel and R. Studer. Berlin: Springer, pp. 103-120.
*   <a name="Embley98"></a>Embley, D.W., Campbell, D.M., Smith, R.D., and Liddle, S.W. (1998) "Ontology-based extraction and structuring of information from data-rich unstructured documents," in: _Proceedings of CIKM '98 - 7th International Conference on Information and Knowledge Management_, edited by G. Gardarin, J. French, N. Pissinou, K. Makki, and L. Bouganim, L. New York: ACM Press, pp. 52-59.
*   <a name="Gruber93a"></a>Gruber, T. (1993a) "A translation approach to portable ontology specifications." _Knowledge acquisition_, **5**(2), 199-220\. Also available online at [http://ksl-web.stanford.edu/knowledge-sharing/papers/README.html#ontolingua-intro](http://ksl-web.stanford.edu/knowledge-sharing/papers/README.html#ontolingua-intro).
*   <a name="Gruber93b"></a>Gruber, T.R. (1993b)  "Toward principles for the design of ontologies used for knowledge sharing." [http://ksl-web.stanford.edu/KSL_Abstracts/KSL-93-04.html](http://ksl-web.stanford.edu/KSL_Abstracts/KSL-93-04.html)
*   <a name="Goasdou99"></a>Goasdoué, F. and Reynaud, C. (1999) "Modeling information sources for information integration," in: _Knowledge Acquisition, Modeling and Management: 11th European Workshop, EKAW '99 Proceedings_, edited by D. Fensel and R. Studer. Berlin: Springer, pp. 121-138.
*   <a name="Guarino1997"></a>Guarino, N. (1997) "Understanding, building, and using ontologies." _International Journal of Human-Computer Studies_, **46**: 293-310.
*   <a name="Guarino1998"></a>Guarino, N. (1998) "Formal ontology and information systems," in: _Formal Ontology in Information Systems_, edited by N. Gurino. Amsterdam, IOS Press. pp. 3-15.
*   <a name="Guarino99"></a>Guarino, N., Masolo, C., and Vetere, G. (1999) "OntoSeek: content-based access to the Web." _IEEE Intelligent Systems_, **14**(3), 70-80.
*   <a name="Kwasnik99"></a>Kwasnik, B. (1999) "The Role of Classification in Knowledge Representation and Discovery." _Library Trends_, **48**(1), 22-47.
*   <a name="Luke97"></a>Luke, S., Spector, L., Rager, D., and Hendler, J. (1997) "Ontology-based Web agents," in: _Proceedings of the First International Conference on Autonomous Agents_, edited by W.L. Johnson, and B. Hayes-Roth. New York: ACM Press, pp. 59-66.
*   <a name="Morgan1999"></a>Morgan, N. (1999) _GEMCat Training Manual: Index._ [http://geminfo.org/Workbench/training/index.htm](http://geminfo.org/Workbench/training/index.htm)
*   <a name="Priss1998"></a>Priss, U. E. (1998) "The formalization of WordNet by methods of relational concept analysis," in: _WordNet: An Electronic Lexical Database_, edited by C. Fellbaum. Cambridge, MA: The MIT Press. pp. 179-196.
*   <a name="Soergel99"></a>Soergel, D. (1999) "The rise of ontologies or the reinvention of classification." _Journal of the American Society for Information Science_, **50,** 1119-1120.
*   <a name="Sutton1999"></a>Sutton, S. (1999) "Conceptual design and deployment of a metadata framework for educational resources on the Internet." _Journal of the American Society for Information Science_, **50**,1182-1192.
*   <a name="Uschold1996"></a>Uschold, M. & Gruninger, M. (1996) "Ontologies: principles, methods and applications." _The Knowledge Engineering Review_, **11**(2), 93-136.
*   <a name="Weistein98"></a>Weinstein, P. (1998) "Ontology-based metadata: transforms the MARC legacy," in: _Digital Libraries 98, Third ACM Conference on Digital Libraries_, edited by I. Witten, R. Akscyn, and F.M. Shipman. New York: ACM Press, 254-63.
*   <a name="Zhu99"></a>Zhu, X., Gauch, S., Gerhard, L., Kral, N., and Pretschner, A. (1999) "Ontology-based Web site mapping for information exploration," in: Proceedings of the Eighth International Conference on Information Knowledge Management, edited by S. Gauch. New York: ACM Press, pp. 188-194.


</td>


</tr>

</tbody>

</table>
