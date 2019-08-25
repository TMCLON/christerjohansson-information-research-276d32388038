#### Vol. 11 No. 2, January 2006


# Constructing Web subject gateways using Dublin Core, the Resource Description Framework and Topic Maps

#### [Jesús Tramullas](mailto:tramullas@unizar.es), Department of Librarianship and Information Sciences

and  

#### [Piedad Garrido](mailto:piedad@unizar.es), Department of Computer Science and Systems Engineering

Zaragoza University  
Zaragoza  
Spain

#### Abstract

> **Introduction**. Specialised subject gateways have become an essential tool for locating and accessing digital information resources, with the added value of organisation and previous evaluation catering for the needs of the varying communities using these. Within the framework of a research project on the subject, a software tool has been developed that enables subject gateways to be developed and managed.  
> **Method**. General guidelines for the work were established which set out the main principles for the technical aspects of the application, on one hand, and on aspects of the treatment and management of information, on the other. All this has been integrated into a prototype model for developing software tools.  
> **Analysis.** The needs analysis established the conditions to be fulfilled by the application. A detailed study of the available options for the treatment of information on metadata proved that the best option was to use the Dublin Core, and that the metadata set should be included, in turn, in RDF tags, or in tags based on XML.  
> **Results.** The project has resulted in the development of two versions of an application called Potnia (versions 1 and 2), which fulfil the requirements set out in the main principles, and which have been tested by users in real application environments.  
> **Conclusion.** The tagging layout found to be the best, and the one used by the writers, is based on integrating the Dublin Core metadata set within the Topic Maps paradigm, formatted in XTM.



## Introduction

The tools for retrieving and accessing information available on the Internet to answer users’ needs take three main forms, namely search engines, subject gateways and vertical portals. Among these, the subject gateways are gaining in popularity and importance as a source of digital information that has been chosen and assessed, and which is being provided with added value services, as described by Navarro & Tramullas (<a id="nav05" name="nav05">2005</a>). This type of information service, by which is understood the structures proposed by Colomb (<a id="col02" name="col02">2002</a>), is based on sets of documents which are browsed by the user with the aid of auxiliary information structures. Koch proposed the following definition, which is widely accepted:

> Subject gateways are Internet services which support systematic resource discovery. They provide links to resources (documents, objects, sites or services), predominantly accessible via the Internet. The service is based on resource description. Browsing access to the resources via a subject structure is an important feature. (<a id="koc00" name="koc00">Koch 2000</a>: 24-25)

Therefore, they are areas of information designed for a user to discover relevant information for a given need (<a id="pit01" name="pit01">Pitschmann 2001</a>). Although the engines and portals have received a great deal of attention in the bibliography, this is not the case with specialised gateways, in spite of their importance as a tool for searching for and retrieving information (<a id="rob99" name="rob99">Robinson & Bawden 1999</a>; <a id="baw02" name="baw02">Bawden & Robinson 2002</a>). Only in Britain, thanks to the excellent development of the [Resource Description Network](http://www.rdn.ac.uk/) (RDN), can one talk of high quality subject gateways.

The undertaking of a research project on subject gateways in the libraries of Spanish universities by a research group, to which the writers of this article belong, had among its objectives the creation of a software tool which, with minimum technical requirements and applying the basic principles of digital information management, would enable the rapid start-up of a specialised subject gateway A set of guidelines was established for the purpose, which would have to be adhered to both during development and for the final tool:

1.  It must be based on free software, and therefore, would also be free.
2.  It must use standard data base technology to save and retrieve information.
3.  It must comply with XML standards.
4.  It must use standard resource description for information.

Bearing in mind the above, and the need for the tool to be able to evolve in line with future developments of information treatment in XML environments, in addition to new techniques for displaying large amounts of information, a free software tool was designed and implemented, called _Potnia_ (<a id="gar05" name="gar05">Garrido & Tramullas 2005</a>), distributed under a Mozilla Public License.

## Description and treatment of data on digital information resources

In line with the basic concepts mentioned above, the structure of the resource description of information conforms to standard ISO 15836 [Dublin Core](http://www.dublincore.org). However, this structure for description based on metadata reaches its full potential when it is integrated into XML coding schemes. For the digital information resource description, [Dublin Core](http://www.dublincore.org) was embedded within the [Resource Description Framework](http://www.w3.org/RDF/) (RDF), with the aim of boosting its description capacity and its (future) use in the semantic web framework. Projects following this structure can be found in the literature , for example [Berry & Browne](#ber99) (1999), [Chakrabarti](#cha02) (2002), [Firestone](#fir03) (2003) and [Michalak](#mic05) (2005).

However, one of the objectives set for the _Potnia_ tool is to develop interfaces based on visual metaphors, which will complement the usual presentation of a list of replies. The most suitable paradigm for this is to combine DC/RDF with Topic Maps (Lacher & Decker 2001), a paradigm which is contained within standard [ISO 13250](http://www.y12.doe.gov/sgml/sc34/document/0322_files/iso13250-2nd-ed-v2.pdf) (<a id="iso02" name="iso02">2002</a>; <a id="par03" name="par03">Park 2003</a>). Topic Maps have been formatted as [XTM](http://www.topicmaps.org/xtm/index.html) (2001) through the use of XML notation. Once the connection point has been introduced and studied in depth, it would be advisable to integrate the Dublin Core and Topic Maps. As demonstrated by Bowers ( <a id="bow00" name="bow00">2000</a>) in a study of superimposed information based on models, there are many similarities between the structural layers found in XML, RDF and Topic Maps. Therefore, it is perfectly possible, and right, to represent the majority of RDF structures through the use of syntax for topic maps, and vice-versa (<a id="fre03" name="fre03">Freese 2003</a>). However, in the latter direction (representing topic maps with RDF structures) part of the semantics is lost. Since the main objective of the application is provide a greater degree of precision in the results of searches, such a loss of semantics is detrimental, and therefore it was decided to use the structure and syntax of topic maps, since these are a more modern, flexible and abstract paradigm.

In addition, topic maps have been repeatedly put forward for other projects as an extremely suitable tool for classifying and organising information. Classification tools, such as taxonomies, thesauri, ontology or faceted metadata can be integrated into topic maps, as demonstrated by Garshol (<a id="gars04" name="gars04">2004</a>). In the same way, they are also more complex and allow for the development of richer, more complex information structures than the widely-used conceptual maps, which can also be integrated into XTM (<a id="gar04a" name="gar04a">Garrido & Tramullas 2004</a>). The many examples of proprietary software tools for displaying information through topic maps, and the fact that there are open source development packages, make it possible to say that the paradigm of topic maps is the information tagging environment that offers the highest number of opportunities for developing metadata-rich digital information products, presented through graphic interfaces.

## First version: Potnia 1.0

The needs analysis before the development of _Potnia_ showed that it would be of most use on a personal or departmental level, answering the needs of special interest groups or communities. The prototype for development had very specific characteristics and was much more manageable than if a structure of specialised subject gateways had been used, such as those used by general gateways like [Yahoo](http://www.yahoo.com)! or [dmoz](http://dmoz.org). The first objective of the design was to have the simplest possible search system, which would reduce the problem of over-complicated interfaces for novice users, and would reply faster with information in greater detail, and be more agile. The second design objective was for the users themselves from a specific discipline to gradually fill the data base supporting the information resource. The initial architecture for the application planned for this project is shown in the figure below:

<div align="center">![fig1](p248fig1.jpg)</div>

<div align="center">  
**Figure 1: Architecture for the application**</div>

The following guidelines were set for working on the development of the first version:

1.  Non-declarative programming must be used.
2.  It must be supported by a Relational Database Management System.
3.  Advanced information display techniques must not be used.
4.  The information resource description structure must comply with the ISO 15836 (DCMI 2003) standard.

The technology chosen to implement this was:

1.  [PHP Script Language](http://www.php.net) (4.3.3RC1) and XHTML 1.0 for Graphical User Interface
2.  [MySQL Database Server](http://www.mysql.com)Versión 4.0.13
3.  SQL/92 (Structured Query Language, for the design of the search engine).

Eventually, the final product was given the name _Potnia_. A test application can be found at [http://imhotep.unizar.es/potnia](http://imhotep.unizar.es/potnia). The application is distributed as open source on the following servers:

*   [http://potnia.sourceforge.net/](http://potnia.sourceforge.net/)
*   [http://freshmeat.net/projects/potnia](http://freshmeat.net/projects/potnia)

### Database design

The resulting relational scheme consists of six tables: data, types, users, data-keyword relations (dk), keywords and pma_relation (Figure 1 above). This last relation proves essential when working with this version of MySQL in order to enable the database management system to interpret the relations with many-to-many cardinality. The users table remains apart from the scheme and not related to the other tables, as its only task is to centre on administering the various types of users who access the application. Tables for managing the information from the resources are the types, dk, keywords and data tables, which bear the weight of the application. When these tables are implemented, the Dublín Core Metadata Set (simple) can be used in a database relational structure.

<div align="center">![fig2](p248fig2.jpg)</div>

<div align="center">  
**Figure 2: Relations among tables**</div>

### Search code

The search process differentiates between a simple search and an advanced search, following the most common search layout interface found at present in the technology for web-based information resource gateways. As a relational database management system with textual information is being used, the recovery model needed is boolean, whose main feature is the consideration of relevance that is purely binary. This was achieved by embedding SQL code within PHP programming, which, in turn, included Javascripts and HTML code. The following figures show examples of SQL embedded code needed to execute searches:

<div align="center">![fig3](p248fig3.jpg)</div>

<div align="center">  
**Figure 3\. Treatment of character strings**</div>

## Second version: Potnia 2.0

As shown below, some decisions taken in implementation, the technology used and suggestions from persons or groups who have used _Potnia_, have motivated a series of decisions to be taken that have gradually affected the architecture of the application, and caused the appearance of several versions of the tool throughout its lifespan. The advantage of this idea lay in the wish to re-design _Potnia_. Once the first version was in operation, checked for any faults and accepted by the various groups using it, it was suggested that a second version should be developed. The first version of _Potnia_ had been evaluated partly from suggestions and comments sent in by e-mail from various groups and individuals who had downloaded the application from Sourceforge or Freshmeat; and partly because the team working on the development were well aware that some aspects had not been included in the first version. Important among these lacks was the need to incorporate sessions, to improve the perception and running of searches by the end user, and the extension of the Dublin Core metadata set, in order to be able to use the qualified set.

Once the usefulness of the project had been evaluated, re-designing was approached by incorporating a set of improvements to different design aspects centred on the user, such as information retrieval and security. In order to fulfil these objectives, several markup languages were considered for prior representation of the information. Among these were [OWL (Ontology Web Language)](http://www.w3.org/2004/OWL/), XML (eXtensible Markup Language) and XTM (XML Topic Maps), all highly suitable markup languages for the treatment of metadata, and which offered powerful new options to combat the deficiencies and limitations in the usual text access to digital information resources. Integration of OWL into XTM has been proven (<a id="vat04" name="vat04">Vatant 2004</a>). These languages can be stored in some of the different types of information repository found on the market, such as: SGBDR, BDOO, BD natives in XML or hybrid systems. This approach can provide higher performance treatment to meta-information saved in the database and formatted to ISO 15386 standard requirements, and, obviously, to improve the display interface for the information in the not too distant future. This main objective will centre on replacing the simple interface of a text list of static replies and thus be able to use a language which is capable of representing the semantics inherent in the inter-relations targeted among the objectives (<a id="hof99" name="hof99">Hofmann 1999</a>). Lastly, from the point of view of security, the application was to be improved by including sessions, a modification that will directly affect the design and programming of the user's graphic interface.

This was achieved by taking a new look at the initial design of the whole project (see work hypothesis), and incorporating XTM Topic Maps (ISO 13250) and a Hybrid Database (SGBR working with an XML manager) into its design:

Relating to the first point, integrating XTM to the resource description for digital information studied should mean that a DTD had had to be used in the first place to enable the topic map paradigms to be read by a computer (see figure 5), followed by the process of describing the information already stored in the MySQL database with the corresponding metadata, in compliance with the ISO 13250 standard. Thus, due to the flexibility of XTM and to the fact that the descriptive information of the resources has been treated previously according to ISO 15386, a simple process is used to enable an information exchange with other tools using mark-up languages such as RDF, making later development possible in the framework of semantic web technology (<a id="bec02" name="bec02">Beckett 2002</a>).

<div align="center">![fig4](p248fig4.jpg)</div>

<div align="center">  
**Figure 4: Inclusion of the DTD in the application**</div>

<div align="center">![fig5](p248fig5.jpg)</div>

<div align="center">  
**Figure 5: Example of a code with integrated XTM**</div>

As for the second point, which involves the changeover of a purely relational database manager to a hybrid database manager (<a id="thu02" name="thu02">Thuraisingham 2002</a>), it must be emphasised that the process of introducing a digital information resource within the application remains the same as in the first version, as far as the end user is concerned. However, in the internal architecture, the user opens with a validation session as the authorised user of the system, and proceeds to include the description of a resource, and, after having passed through an error control filter, passes on the process of instantiation. In this process, part of the information is instantiated in the tablespaces data and keywords, created in MySQL for the purpose, and a parallel instantiation process appears, which stores the metadata in a structure called a description file. This description file saves the data in XML in a secondary memory, thus comprising the XML manager which works with the relational database at all times. As a complement, part of the description file is stored in a hash table, in the main memory, in order to make more rapid and efficient searches. This change in the architecture has, in turn, forced a change in the architecture of the search system, with the search process being structured as shown in Figure 6\.

<div align="center">![fig6](p248fig6.jpg)</div>

<div align="center">  
**Figure 6: Search process on the hybrid manager**</div>

## Conclusion and future developments

The development of tools for information management needs to have an inter-disciplinary approach that will ensure the quality of the resulting products. The project described here was aimed at the needs for information management of the end users, and has determined the main features on the _Potnia_ application. Technical problems were solved by using the topic maps paradigm to provide the information with semantics (<a id="rat01" name="rat01">Rath 2001</a>). This enables the search processes to be refined and adjusted, as they establish points of contact between the keywords which were ignored by the traditional process of treatment and retrieval of information used initially. In addition, the greater advantages obtained by incorporating a hybrid manager into the application has improved the speed of reply on the search engine

However, one of the drawbacks that may arise from this new version is the use of an XML manager, since this does not allow for the most suitable treatment for textual information in the case of more complex searches. For this reason, the use of soft-computing techniques is being analysed to solve problems arising from this type of retrieval.

The future development of _Potnia_ will take the following aspects into account:

*   Display: using paradigms such as self-organizing maps, conceptual maps or topic maps, the display and clustering of the results obtained will provide added value visual information on the search results (<a id="ger03" name="ger03">Geroimenko & Chen 2003</a>).
*   Development of a possible support system to make generic searches in traditional search engines, or other sources of digital information, to feed the Potnia gateway.
*   Soft-computing techniques for information retrieval, since the particular features of textual information conform to an imprecise, uncertain information profile that is difficult to categorise; this makes soft-computing techniques into a very useful paradigm to solve the problem ( <a id="cre01" name="cre01">Crestani & Passi 2001</a>).

## References

*   <a name="baw02" id="baw02"></a>Bawden, D. & Robinson, L. (2002). Internet subject gateways revisited. _International Journal of Information Management_, **22**(2), 157-162.
*   <a name="bec02" id="bec02"></a>Beckett, D (2002). [_Connecting XML, RDF and Web technologies for representing knowledge on the Semantic Web_](http://www.idealliance.org/papers/xmle02/dx_xmle02/papers/03-05-07/03-05-07.html). Paper presented at XML Europe Conference 2002, Barcelona, May 2002\. Retrieved 2 May, 2004 from http://www.idealliance.org/papers/xmle02/dx_xmle02/papers/03-05-07/03-05-07.html
*   <a name="ber99" id="ber99"></a>Berry, M.E. & Browne, M. (1999). Understanding search engines: mathematical modeling and text retrieval. Software, environments, tools. Philadelphia, PA: Society for Industrial & Applied Mathematics.
*   <a name="bow02" id="bow02"></a>Bowers, S. (2000). _[A generic approach for representing model-based superimposed information.](http://www.cse.ogi.edu/tech-reports/2000/00-008.pdf&ei=MlWkQ4rAJKKQiALG56ydBw&sig2=qycTahRJnfO2HwaZ5mGX3g)_ Beaverton, OR: Oregon Health and Science University. Retrieved 17 December, 2005 from http://www.cse.ogi.edu/tech-reports/2000/00-008.pdf&ei=MlWkQ4rAJKKQiALG56ydBw&sig2=qycTahRJnfO2HwaZ5mGX3g
*   <a name="cau02" id="cau02"></a>Caussanel J., Cahier J-P., Zacklad M. & Charlet, J. (2002). [_Les Topic Maps sont-ils un bon candidat pour l’ingénierie du Web Sémantique?_](http://tech-web-n2.utt.fr/ssw/cahier/docs/IC2002.pdf) Paper presented at Actes de la conférence Ingénierie des Connaissances, Rouen, 2002\. Retrieved 1 April, 2005 from http://tech-web-n2.utt.fr/ssw/cahier/docs/IC2002.pdf
*   <a name="cha02" id="cha02"></a>Chakrabarti, S. (2002). _Mining the Web: analysis of hypertext and semi-structured data._ Boston, MA: Morgan Kaufmann.
*   <a name="col02" id="col02"></a>Colomb, R.M. (2002). _Information spaces: the architecture of cyberspace_. London: Springer.
*   <a name="cre00" id="cre00"></a>Crestani, F. & Passi, G. (Eds.) (2000). _Soft computing in information retrieval: techniques and applications_. Heidelberg: Physica-Verlag
*   <a name="fir02" id="fir02"></a>Firestone, J.M. (2003). _Enterprise information portals and knowledge management._ Oxford: Butterworth-Heinemann.
*   <a name="fre03" id="fre03"></a>Freese, E. (2003). Topic maps and RDF. In Park, J., (Ed.) _XML topic maps. Creating and using topic maps for the web._ (pp. 283-325) Boston, MA: Addison-Wesley.
*   <a name="gar04a" id="gar04a"></a>Garrido, P. & Tramullas, J. (2004). Convergence of topic maps and concept maps: prototype foundations. In _Proceedings of the IADIS International Conference. WWW/Internet 2004, Madrid_, vol. 2, (pp. 1105-1108). Lisbon: International Association for the Development of the Information Society.
*   <a name="gar04b" id="gar04b"></a>Garrido, P. & Tramullas, J. (2004). Topic maps: an alternative or a complement to concept maps? _Concept Maps: Theory, Methodology, Technology. First International Conference on Concept Mapping_, Pamplona, vol. 2, (pp. 185-188). Pamplona, Spain: Universidad Pública de Navarra.
*   <a name="gar05" id="gar05"></a>Garrido, P. & Tramullas, J. (2005). _Potnia: una herramienta para directorios temáticos basada en Dublin Core y Topic Maps._ Paper presented at the 7th. Congreso ISKO España, Barcelona, July 2005.
*   <a name="gars04" id="gars04"></a>Garshol, L.M. (2004). Metadata? Thesauri? Taxonomies? Topic Maps! _Journal of Information Science_, **30**(4), 378-391.
*   <a name="ger03" id="ger03"></a>Geroimenko, V. & Chen, C. (Eds.) (2003). _Visualizing the semantic web: xml based internet and information visualization_. London: Springer.
*   <a name="hof99" id="hof99"></a>Hofmann, T. (1999). Probabilistic Topic Maps: navigating through large text collections. In David J. Hand, Joost N. Kok, Michael R. Berthold (Eds.) _Advances in intelligent data analysis: third international symposium, IDA-99, Amsterdam, The Netherlands, August 1999\._ (pp. 161-172). Berlin: Springer.
*   <a name="iso02" id="iso02"></a>International Organization for Standardization and International Electrotechnical Commission. Joint Technical Committee 1\. (2002) [ISO/IEC 13250\. Topic Maps. Information technology. Document description and processing languages.](http://www.y12.doe.gov/sgml/sc34/document/0322_files/iso13250-2nd-ed-v2.pdf) Retrieved 22 September, 2004 from http://www.y12.doe.gov/sgml/sc34/document/0322_files/iso13250-2nd-ed-v2.pdf
*   <a name="koc00" id="koc00"></a>Koch, T. (2000). Quality-controlled subject gateways: definitions, typologies, empirical overview. _Online Information Review_, 24(1), 24-34.
*   <a name="lac01" id="lac01"></a>Lacher, M.S. & Decker, S (2001). [On the integration of Topic Maps and RDF data](http://www.mulberrytech.com/Extreme/Proceedings/html/2001/Lacher01/EML2001Lacher01.html). In _Aggregated Proceedings for the Extreme Markup Languages® Conferences (2001-2005)_. Rockville, MD: Mulberry Technologies Inc. Retrieved 17 December, 2005 from http://www.mulberrytech.com/Extreme/Proceedings/html/2001/Lacher01/EML2001Lacher01.html
*   <a name="mic05" id="mic05"></a>Michalak, S.C. (Ed.). (2005). _Portals and libraries_. Binghamton, NY: Haworth Press.
*   <a name="nav05" id="nav05"></a>Navarro, D. & Tramullas, J. (2005). Directorios temáticos especializados: definición, características y perspectivas de desarrollo. _Revista Española de Documentación Científica_, **28**(1), 49-61.
*   <a name="par03" id="par03"></a>Park, J., (Ed.) (2003). _XML topic maps. Creating and using topic maps for the web_. Boston: Addison-Wesley.
*   <a name="pit01" id="pit01"></a>Pitschmann, L. A. (2001). _Building sustainable collections of free Web third-party resources_. Washington, DC: Digital Library Federation.
*   <a name="rat01" id="rat01"></a>Rath, H.H. (2001). Semantic resource exploitation with Topic Maps. In Henning Lobin, (Ed.) _Sprach- und Texttechnologie in digitalen Medien. Frühjahrstagung der Gesellschaft für linguistische Datenverarbeitung (GLDV), Justus-Liebig-Universität Giessen, 28.-30.03.2001_, (pp. 3 -15). Norderstedt, Germany: Books on Demand.
*   <a name="rob99" id="rob99"></a>Robinson, L. & Bawden, D. (1999). Internet subject gateways. _International Journal of Information Management,_ **19**(6), 511-522.
*   <a name="thu02" id="thu02"></a>Thuraisingham, B. (2002). _XML databases and the semantic web_. Boca Raton, FL: CRC Press.
*   <a name="vat04" id="vat04"></a>Vatant, B. (2004). [_Ontology-driven topic maps_](http://www.idealliance.org/papers/dx_xmle04/papers/03-03-03/03-03-03.pdf). Paper presented at XML Europe 2004, Amsterdam, May 2004\. Retrieved 2 May, 2005 http://www.idealliance.org/papers/dx_xmle04/papers/03-03-03/03-03-03.pdf
*   <a name="xtm01" id="xtm01"></a>XTM TopicMaps.Org (2001). ([XML Topic Maps Specification (XTM) 1.0](http://www.topicmaps.org/xtm/index.html). XTM TopicMaps.Org. Retrieved 2 March, 2003 from http://www.topicmaps.org/xtm/index.html



