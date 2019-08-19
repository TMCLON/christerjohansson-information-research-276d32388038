####Information Research, Vol. 11 No. 3, April 2006


# The use of genre analysis in the design of electronic meeting systems

#### [Pedro Antunes](mailto:paa@di.fc.ul.pt)  
Department of Informatics, Faculty of Sciences of the University of Lisboa,  
Campo Grande, 1700 Lisboa, Portugal

#### [Carlos J. Costa](mailto:carlos.costa@iscte.pt)  
Departamento de Ciências e Tecnologias de Informação, ISCTE,  
Av. das Forças Armadas, 1649 Lisboa, Portugal

#### [José A. Pino](mailto:jpino@dcc.uchile.cl)  
Computer Science Department, Universidad de Chile,  
Blanco Encalada 2120, Santiago, Chile

#### Abstract

> **Introduction.** Genre analysis is an approach to study communication patterns and thus it can be applied to the specific context of meetings. This research investigates the use of genre analysis in the design of electronic meeting systems.  
> **Background.** The primary goal of genre analysis is to understand how virtual communities use digital communication to collaborate. This knowledge is fundamental for informing the design of information systems, particularly in areas where communication and informality are paramount. However, the research literature does not report any experiments where genre analysis has been used to inform the design of electronic meeting systems.  
> **Problems.** The paper tackles the following common problems found in current electronic meeting systems: (1) reduced organizational integration, neglecting many contextual cues and explaining factors necessary to make meeting outcomes usable within the organization; (2) lack of support to specific communities of users, stressing the dependency on a facilitator to configure and manage the technology; and (3) lack of support to meeting occurrences that span long time periods.  
> **Conclusions.** The paper describes how genre analysis was used to develop electronic meeting systems for several organizations and meeting genres. It covers the complete design process, from genre elicitation to validation. The obtained results demonstrate that the genre approach produces electronic meeting systems focused on organizational integration, pre-configured to communities of users, supporting long-term usage and added organizational value.

* * *

## Introduction

Genre analysis investigates communication among people. Its primary characteristic is that it avoids a formalized way to describe communication, highlighting rather informal interaction patterns found in well-established groups of people. As such, genre analysis has found a niche in organizational behaviour, where informal communication channels and _ad-hoc_ work structures abound ([Yates & Orlikowski 2002](#Yates3); [Yates & Orlikowski 1992](#Yates1)).

With the advent of virtual communities, genre analysis has found another flourishing application ground. In that context, genre analysis contributes to understanding how virtual communities use digital communication to collaborate. Two good examples are videoconferencing ([Pargman & Lantz 2002](#Pargman)) and computer mediated communication ([Erikson 2000](#Erikson); [Bregman & Haythornthwaite 2001](#Bregman)). Other studies in this area include the characterization of Web genres ([Crowston & Williams 2000](#Crowston)), online newspapers ([Ihlstrom & Lundberg 2004](#Ihlstrom)), and even the classification of user interface components ([Spinuzzi 1999](#Spinuzzi1)).

The genre approach has also been successfully used in IT development. Some examples are improving Web search engines ([Roussinov _et al._ 2001](#Roussinov)), developing collaborative information retrieval tools ([Procter _et al._ 1998](#Procter)), reorganizing document management systems ([Rauber & Kogler 2001](#Rauber); [Tyrvainen & Paivarinta 1999](#Tyrvainen)), constructing new types of documentation ([Zachry 1999](#Zachry)), and defining metadata for computer mediated information ([Karjalainen & Salminen 2000](#Karjalainen)).

Electronic meeting systems deal mainly with communication, which suggests that there may be an opportunity to apply genre analysis to the design of electronic meeting systems, something we have not seen done in the past.

In this paper we report our investigation on the impact of genre analysis on the design of electronic meeting systems. We find two major arguments justifying this research. The first states that communication is a fundamental component of meetings and thus there is a potential direct impact of the genre analysis outcomes on the design of electronic meeting systems. The second argument mentions that electronic meeting systems have been relatively unsuccessful for various reasons (e.g., conflicting results, unbalanced positive or negative effects ([Fjermestad & Hiltz 1999](#Fjermestad)), process issues ([Briggs _et al._ 2003](#Briggs)), facilitation problems ([Costa & Antunes 2001](#Costa2)) and usage and budget difficulties ([Briggs _et al._ 2003](#Briggs))). On the other hand, the goal of electronic meeting systems in aiding effective and efficient meetings remains quite attractive. In fact, this goal is becoming increasingly desirable because of the growing frequency and cost of meetings in organizations ([Romano & Nunamaker 2001](#Romano)). Thus, there is a demand for innovative electronic meeting systems designs. This paper shows genre analysis produces innovative and viable electronic meeting systems.

The paper is organized as follows. We describe the genre analysis process in the [next](#s1) section. We also discuss genre theory in the context of meetings and electronic meeting systems, and propose a schema for the analysis of genres in meetings. We then describe how genre analysis is applied, using two case studies we have carried out in the [Applying genre analysis](#s2) section. Next, we address electronic meeting systems design in the [From genre analysis to design](#s3) section. Given that genre analysis produces under-specified system requirements - at least when compared to other systems analysis techniques - our purpose in this section is to clarify how electronic meeting systems requirements can be drawn from genre analysis. The [Electronic meeting systems implementation](#s4) section describes some implementation details common to our designs. Finally, we discuss the overall contributions of this research in the [Lessons learned and discussion](#s5) section and we draw some conclusions in the [last](#s6) section.

## <a name="s1" id="s1"></a>Genre analysis

### Genre theory

The concept of _genre_ (a French term meaning 'type') had its genesis in rhetoric and literature analysis. In that context, a literary genre is a category of literary works having the same basic purpose and following similar conventions. Its systematic study started with Aristotle who sought to typify literary works according to their common characteristics ([Bazerman 1988](#Bazerman)). For centuries, this concept served as a practical way to organize and index literary works, as well as a way of entailing rules to literary creation.

Formally, a _genre_ is a taxonomic collection of speech or written text types showing the systematic use of _genre elements_ ([Lacey 2000](#Lacey)). The genre elements are related to either _form_ or _content_. The navigational elements in a Web page ([Ihlstrom & Lundberg 2004](#Ihlstrom)) provide a good example of genre elements related to form, while salutations, introductory remarks and conclusions are good examples of genre elements related to contents.

Another viewpoint considers _communicative purpose_ as a fundamental property of genres ([Yates & Orlikowski 2002](#Yates3)). Here, a genre is a template for action enacted within a community to accomplish a socially recognized purpose. A simple example is the Call-for-Papers genre, understood by the research community as an invitation to submit manuscripts intended for a scientific conference.

The above definition has two implications. The first concerns the introduction of a new property of genre, _community ownership_, meaning the conventions of form, contents and purpose reflect the recurrent practices of a community and not individual or opportunistic motivations ([Bergquist & Ljungberg 1998](#Bergquist1)).

The second implication is that genres may now be applied to the organizational context. An _organizational communication genre_ is, then, a typified communicative action invoked in response to a recurrent situation within an organization ([Yates & Orlikowski 1992](#Yates1)).

Another property of genre is _relative stability_ ([Spinuzzi 2003](#Spinuzzi3)), meaning that a genre must be conventional within a community, otherwise community ownership would not be possible. However, a genre is not static: it may be appropriated from outside and restructured by the community, evolve to reflect new practices or technology and, of course, its use frequency may become so low that it naturally dies.

Genre analysis has interested people studying organizational interaction, as it provides clues about how organizations structure their work. Organizations adopt and modify genres to suit their coordination and collaboration needs ([Yoshioka & Herman 2000](#Yoshioka)). Such a collection of genres is called a _genre repertoire_ ([Yates _et al._ 1999](#Yates2); [Orlikowski & Yates 1994](#Orlikowski)). Furthermore, in an organization, several genres are linked together forming what is designated as _genre systems_ ([Yoshioka _et al._ 2001](#Yoshioka2)). Finally, genres may also form a _hierarchy_, where a genre may be a specialization of a more general genre ('is-a' relationship) or participate in the decomposition of a genre in several distinct genres ('has-a' relationship) ([Crowston & Williams 2000](#Crowston)). Yates & Orlikowski ([1992](#Yates1)) proposed the notion of _sub-genre_ to express these hierarchical relations. However, the hierarchy must necessarily preserve community ownership; otherwise the community would not recognize sub-genres as such ([Bergquist & Ljungberg 1999](#Bergquist2)).

Besides the previously discussed properties, we should also consider two additional ones: contingency and decentralization ([Spinuzzi 2000](#Spinuzzi2)). _Contingency_ means organizational work is opportunistic sometimes and, thus, genre systems should not be considered formal specifications of coordinated activities (as workflow specifications) but rather under-specified communication patterns. _Decentralization_ means purpose is disseminated throughout a genre system and, thus, the whole combination of genres is necessary to explain an individual genre. For example, if a person wants to understand a Call-for-Papers, then he needs to comprehend the whole conferencing system. The contingency and decentralization properties contribute to characterize what is known as _genre ecologies_ ([Spinuzzi 2003](#Spinuzzi3)).

Finally, the increasing computerization of the organization expanded the notion of genre from classic verbal and written communication towards _digital genres_. Examples of digital genres are Newsgroups, FAQ (Frequently Asked Questions) and Web Portals. These considerations substantiate the genre theory of organizational communication as an analysis tool capable of explaining organizational work ([Yates & Orlikowski 2002](#Yates3)).

### The process

Genre analysis infers work structure by inquiring about communicative actions. We illustrate the approach with the aid of Figure 1\. The process departs from the analysis of communicative actions - e.g., Ci and Cj - observed in an organization and materialized through various media, such as memos, reports, e-mails, meetings, telephone calls, etc. These communicative actions may be consistently interpreted as members of genres - e.g., Gi and Gj - meaning they have recognizable form, contents and purpose. These genres may also be interpreted as being consistently related to each other, and thus aggregated in genre systems (denoted by Rij). In a certain way, the combination of Gi, Gj and Rij explains a work pattern performed by an organization.

<div align="center">![figure 1](p251fig1.jpg)</div>

<div align="center">  
**Figure 1: genre analysis process**</div>

One way of analysing communicative actions is to gather the following metadata: why (purpose), what (content), who (participants), when (timing), where (location), and how (form) ([Yates & Orlikowski 2002](#Yates3), [Yoshioka _et al._ 2001](#Yoshioka2)). This can be done using several techniques, e.g., document analysis, interviews, group discussions, ethnography and contextual inquiry ([Beyer & Holtzblatt 1998](#Beyer)).

This process is somewhat complex for two reasons: first, community ownership of genres must be guaranteed. Along with the analysis process, many genre candidates may appear, and scrutinizing which are true genres is a permanent overhead. The construction of genre hierarchies is particularly difficult because analysts must regard organizational communication at different levels of detail ([Yates & Orlikowski 1992](#Yates1)) and come up with meaningful views to describe work structures. The second reason is the required analysis of a large number of communicative actions, which is necessary to find sufficient evidence of repeating patterns and to exclude opportunistic communications.

Currently, there is no broadly accepted formalism to express the outcomes of genre analysis. Yoshioka & Herman ([2000](#Yoshioka1)) use tables to describe genres, trees to display genre repertoires and dependency diagrams to describe genre systems. Spinuzzi ([2003](#Spinuzzi3)) uses genre ecology diagrams, which are basically node maps.

Focusing on our stated goals, we should now relate genre analysis with meetings. Meetings are a form of communication within organizations. Communication, in turn, is considered a fundamental component of organizations: "communication - the exchange of information and the transmission of meaning - is the very essence of a social system or an organization" ([Katz & Kahn 1978](#Katz)). Myers & Myers ([1982](#Myers)) even assert there is no organized activity without communication. These authors claim that communication implies a transactional process whereby people build meanings and develop expectations on what surrounds them by interchanging symbols. Te'eni ([2001](#Teeni)) builds on the theory of communicative action ([Habermas 1998](#Habermas)) to develop a model to explain how people choose the message form and the medium according to goals and situation. This model considers three perspectives: action, social relationships and choice.

People may then choose a meeting to have certain types of knowledge interchange. Meetings may also be recurrent in organizations, since they tend to nurture relatively stable communities of people coordinating themselves in meetings. Thus, the meeting is a genre of organizational communication generally recognized by most organizations (see Romano & Nunamaker ([2001](#Romano)) for a characterization in terms of purpose, content, etc.). Planning meetings, project meetings, briefings, brainstorming sessions, welcome meetings, and workshops are just few examples of meeting sub-genres common in organizations.

Moreover, meetings are also genre systems. Yates & Orlikowski ([2002](#Yates3)) defined the meeting genre system as composed of the following genres:

*   Logistics - Information exchange about time, place and who participates in the meeting.
*   Agenda - Information circulated stating the meeting objectives, either before, during or after meetings.
*   The meeting itself - The interactions among meeting participants necessary to accomplish the meeting objectives.
*   Meeting report - The meeting outcomes, serving two important purposes: as meeting memory and triggers for subsequent work.

The dual perspective of meetings, both as genre and genre system, highlights the organizational macro-level and micro-level perspectives typical in organizational literature. The micro-level perspective is particularly interesting if we wish to analyse several recurrent patterns in meetings, such as facilitation, negotiation or decision processes ([Antunes & Ho 2001](#Antunes3)).

We developed the schema shown in Figure 2 to facilitate meeting genre analysis. The schema shows that, at the macro-level, meetings are one of the several genres used by organizations to structure work. The specialization concept affords specialized meeting genres, such as obtaining consensus, brainstorming, planning, briefing people, etc. Each of these meeting genres may be decomposed into a meeting genre system, consisting of logistics, agenda, meeting itself and report genres. The genres belonging to a meeting genre system may be specialized and decomposed at the micro-level. We will discuss three hypotheses concerning this schema in the next section:

> **H1** - The schema, incorporating the notions of meeting genre and genre system, can be easily understood by a community of users.  
> **H2** - The schema can facilitate the interaction between analysts and users, fostering participation in the modeling and validation tasks.  
> **H3** - The schema is adequate to cases when the organizational context must be clarified, work situations are undocumented and the user activities are hard to formalize.

<div align="center">![figure2](p251fig2.jpg)</div>

<div align="center">  
**Figure 2: Schema for genre analysis of meetings**</div>

## <a name="s2" id="s2"></a>Applying genre analysis

We illustrate the application of genre analysis to meetings using the case study method ([Yin 1994](#Yin)). Two case studies are described, based on two real-world organizations which we had the opportunity to study in detail.

**Case 1 - High administration meetings in a university**

This case used genre analysis to explain management meetings held in a public higher education institution. The explanations we were seeking were related to the external role of management meetings, shaping and coordinating the organizational manoeuvre.

**Study questions.** The generic question is how genre analysis can be used in practice to infer work structure by analysing meeting reports. Our main motivation for this study was to evaluate the adequacy of the schema (hypothesis H1).

**Site selection.** The selected organization was the Engineering School of a public university. The School is organized in a very traditional way, with an executive board, management and pedagogical committees. The management committee is headed by a member of the executive board and has representatives from the employees' and students' unions.

**Unit of analysis.** We analysed the meeting reports produced by the School management committee. The schema was used to reverse-engineer the meeting genre system exclusively from the meeting reports.

**Data collection.** We collected meeting reports produced in a period of four years (corresponding to about thirty management meetings). We then followed these analysis steps:

*   Fragment the meeting reports into a raw list of data items.
*   Based on that list, identify all decisions made (214 were identified) and classify them according to decision sub-genres.
*   From the decision sub-genres we inferred the collection of originating agenda topics. These agenda topics, in turn, were grouped into agenda sub-genres.
*   Based on the decision sub-genres and data items we identified the collection of report sub-genres.
*   Finally, we analysed the associations between these different collections and identified the genre systems behind the management meeting genre.

The resulting model is shown in Figure 3\. The 214 decisions were grouped by similarity into the following genres: decision for action, decide unitary plan, postpone decision and decide continuing plan. 'Decision for action' has the purpose of instructing organizational agents to accomplish specific actions. 'Decide unitary plan' is concerned with planning activities that usually span a long period of time. 'Postpone decision' refers to the choice of delaying the decision making for a future time. 'Decide continuing plan' produces rules or procedures adopted by the organization.

<div align="center">![figure3](p251fig3.gif)</div>

<div align="center">  
**Figure 3: Model of management meetings (we also show the number of items considered members of the identified genres)**</div>

In this type of meetings, decisions are made in response to direct requests. We could identify two types of requests: occasional and recurrent. An example of recurrent request is the petition to approve the annual budget.

We found out this organization uses eight different report genres: answers to requests or offers (typically, 'yes' or 'no'); directives to organizational agents; transfer of documents to internal or external entities; approval of documents; re-scheduling of agenda items; requests for additional information from internal or external entities; rules, procedures or explanations; and delegation, which concerns the transfer of control to other entities. It should also be mentioned there is only one logistics genre associated with these meetings, since they are periodic and the membership is highly formalized.

We identified four genre systems associated with management meetings (see Figure 3). These genre systems were mostly associated with the four decision genres previously identified, and thus we named them according to the decision genres: decide for action, decide unitary plan, postpone decision and decide continuing plan.

Finally, we validated this genre model. The validation was implemented by first selecting a group of persons belonging either to the target organization or to organizations similar to the target organization (other public universities). Then, we had a meeting with them where we described genre theory and our model. We then supplied the group with the corpus (214 decisions) and requested them to classify those decisions according to one of the genre systems. The results are shown in Figure 3: 116 (54%) decisions were classified as decisions for action; 7 (3%) as unitary plans; 15 (7%) as postponed decisions; and 66 (31%) as decisions over continuous plans. Ten decisions (5%) could not be classified by the group.

We also requested the group to classify these decisions according to the report genres. The obtained results are shown on the right hand side of Figure 3\. The 116 decisions for action produced 46 (40%) answers, 102 (88%) instructions and 2 (2%) document transfers, implying that most decisions produced more than one report item. Unitary plan decisions produced the same number of document approvals, while 15 postponed decisions produced 4 (27%) reschedules and 11 (73%) requests for information. Finally, 66 decisions over continuing plans produced 47 (71%) rules, procedures or explanations and 21 (32%) delegations of power.

**Case study analysis.** The classification process highlighted several important characteristics of meeting genre analysis:

*   The obtained model describes how the organization uses management meetings to control organizational work. A significant percentage of decisions correspond to direct instructions. It is also interesting to note very few decisions are related with new problems or situations (3%).
*   The work structure seems to be organized according to a small number of genre systems. Four genre systems were identified and, from these, more than 50% of all communication was related to one of them. Furthermore, a mere 5% of communication could not be related to one of these genres.
*   The participants in the validation task could recognize the proposed genres and relate them to decisions and report items with a 5% error margin, which means genres are easy to understand (hypothesis H1).

From these remarks we conclude that genre analysis is easily understood by the users. Furthermore, the obtained model is capable to describe how the community structures work around meetings, based on a repertoire of relatively few genres and genre systems.

**Case 2 - Staff briefings in an accounting company**

This case studied several meetings held by an accounting company. Some meetings were filtered out and the study continued only for staff briefings, a type of meeting used to assess current work and assign activities to people.

**Study questions.** The generic question is how genre analysis can be used in practice to infer work structure by inquiring about communicative actions. Our motivation to carry out this study was to obtain a list of requirements to develop an electronic meeting system for this organization. We followed the previously described schema. Specifically, our study goal was to validate hypotheses H1, H2 and H3\.

**Site selection.** The studied accounting company is a small organization, with a flat structure, and a core business (mostly external consultancy work done by autonomous professionals) where meetings serve as a primary coordination mechanism. These characteristics made it difficult to identify a list of requirements for electronic meeting system development, since the company had an overall feeling that their meetings were not very productive but the degree of informality associated with meetings prevented them from devising a concrete list of requirements.

**Unit of analysis.** The unit of analysis is the type of meeting used by top management to coordinate the company's effort in the consultancy projects in which it is involved.

**Data collection.** We started by participating in several meetings as observers. From these observations, using the schema, we discovered the target organization, at the macro-level, coordinates itself through three meeting genres: (1) _process definition meetings_, dedicated to analysing work processes in an informal way, clarifying and improving the organizational manoeuvre; (2) _planning meetings_, dedicated to settin up new projects; and (3) _staff briefings_, where the current status of projects is analysed.

Then, we discussed the relative importance of these meeting genres with some of the staff, to conclude staff briefings are regarded as the most important coordination mechanism within the organization. Considering this information, we focused our observations on staff briefings to analyse it at the micro-level.

Staff briefings are held once a week. Typical participants are two senior consultants and one senior accountant. Staff briefings call for members to report on the weekly work progress, allowing the group to assess the overall project status, identify risks and apply corrective actions.

Using the schema, we observed that the briefing genre can be decomposed into a genre system, consisting of four sub-genres, namely, logistics, agenda, meeting and report. Through specialization, we characterized the sub-genres making up the briefing genre system. The obtained model is presented in Figure 4\. We identified three different genre systems in staff briefings and named them according to the various agenda topics: accompanying projects, management and control, and clarifying problems.

<div align="center">![figure4](p251fig4.gif)</div>

<div align="center">  
**Figure 4: Staff briefings model**</div>

The purpose of the 'accompanying projects' genre system is to get fresh information on current projects. The purpose of the 'management and control' genre system is to propose and discuss modifications to projects, such as changing schedules or re-allocating personnel. Finally, the purpose of the 'clarify problems' genre system is to raise and clarify problems related to project development, staffing, earnings, etc.

We also analysed the other properties of staff briefings. The agenda and report are paper-based while the meeting itself is face-to-face. No particular person owns the agenda. The sense of ownership is completely lost since the agenda does not change from week to week. Every briefing produces individual to-do lists and no formal report is generated. To-do lists identify projects, tasks, deadlines and allocated staff. Briefings are held on every Friday at a fixed hour and thus there is no need to communicate changes in time or location. The briefings are cancelled if the participants are unable to attend, or whenever a meeting collides with a holiday, which are the only situations when the logistics genre is enacted.

This model was presented to members of the target organization. After discussion, it was approved. Some details related to the genre theory were provided to the participants but, unlike the previous case, we avoided unfolding the genre theory behind the model.

**Case study analysis.** The genre analysis process was very successful, considering the time and effort necessary to produce a model of staff briefings. We attribute this success to the simplicity of the model and to the straightforwardness of the process.

The participants understood the approach and agreed to participate in it. The portrayal of meetings as a genre system with logistics, agenda, meeting itself and report was validated by the users. The high level of detail and simple formalisms used to describe genres also contributed to the acceptance of genre analysis (hypothesis H1).

Generally, meetings such as briefings are not documented by organizations. These circumstances require a significant effort to model the work situation, given the process reveals many different views and personal opinions. The adoption of a cooperative approach facilitated data consolidation and fostered consensus around the final model. The cooperative approach was also efficient, considering only two short meetings were necessary to elicit and validate the model (hypothesis H2).

The participants regarded meetings as inadequate to formalization. Although they could provide us with meeting patterns (genre systems), they did not regard them as processes. The informality and focus on patterns seems to be a major strength of genre analysis (hypothesis H3).

Regarding both case studies, we should note they reflect two different approaches to genre analysis: bottom-up (from sub-genres to genre systems) and top-down (from genre systems to sub-genres). Both approaches gave indications to support hypotheses H1, H2 and H3\.

Besides the two cases described above, we have been able to apply the schema to several other meeting genres, such as executive board meetings, general assembly meetings, strategy meetings and marketing meetings ([Costa _et al._ 2002](#Costa6); [Antunes _et al._ 2001](#Antunes2); [Costa _et al._ 2001b](#Costa5); [Costa _et al._ 2001a](#Costa4); [Costa _et al._ 2000](#Costa3)). Although the applied techniques have changed from case to case (we have used document analysis, interviews, electronic meetings and surveys), the analysis process has been kept very similar to the one described above, consisting of: (1) information gathering; (2) modelling genres and genre systems; and (3) validating the model with users.

## <a name="s3" id="s3"></a>From genre analysis to design

The issue we will now address is to discuss whether the genre analysis outcomes inform electronic meeting system design. We will take a practical approach and apply genre analysis to concrete designs. We start by discussing why electronic meeting system design is a good application area for this approach and what benefits genre analysis may bring to design. Then we describe two cases demonstrating those benefits.

### Electronic meeting system design

An electronic meeting system has been characterized as a combination of several tools allowing users to communicate, deliberate and manage information in a concerted effort ([Nunamaker _et al._ 1997](#Nunamaker)). Typical examples are tools for generating, organizing and evaluating ideas. Considering electronic meeting system design in this context means we would focus on the functional properties of the tools, e.g., finding various possibilities for managing ideas.

Another approach to characterize electronic meeting systems consists of identifying what kinds of outcomes emerge from such systems, that affect the network of individuals and groups ([Oravec 1996](#Oravec)). These outcomes can be characterized as contributing to the organization through:

*   an intangible value—the contribution of electronic meeting systems to organizational objectives, such as building group abilities, making decisions and planning (e.g., an extensive study of meetings by Romano _et al._ ([2001](#Romano)) shows 66% of meetings are intended to reconcile conflicts, reach group judgements or decisions and solve problems).
*   a tangible value—physical testimonials reporting and preserving the intangible things produced during meetings. Examples are meeting minutes and action plans.

This categorization is interesting because it is well aligned with genre theory, since intangible and tangible values correspond directly to genre purpose and content. In this context, electronic meeting system design would focus on the support for organizational objectives and assets. We may now align a set of fundamental differences between the two views described above.

**Integration.** As shown in section 2, meetings are an organizational communication genre. This genre, being part of the organizational genre system, is connected to other genres, which support other work activities in the organization. Thus, from an organizational point of view, the production of value is not necessarily attached to the single meeting genre, but is in fact dispersed throughout the genre system. This perspective is challenging because it highlights the need for electronic meeting systems to be integrated in the organization, while they are frequently regarded in isolation, as unusual tools used in exceptional events. As a consequence, this integration introduces new requirements for electronic meeting systems: they should facilitate the transfer of information from and to the other components of the organization such as organizational repositories or workflow systems (focusing on tangible value); and they should become part of the mainstream decision processes in the organization (addressing intangible value).

**Pre-configuration.** A possible criticism of typical electronic meeting systems is that they support generic purposes, like idea generation or idea consolidation, in a context which is strongly affected by unique group and organizational characteristics. Generic-purpose electronic meeting systems have an important drawback: they require significant expertise and overhead to configure the technology to the context of use, a task usually attributed to a facilitator ([Bostrom _et al._ 1993](#Bostrom); [Antunes & Ho 2001](#Antunes3)). On the contrary, genre based electronic meeting systems have that expertise codified during the design phase and thus require no facilitator. It should be emphasized that dependency on the facilitator has been considered a negative factor for electronic meeting system success ([Briggs _et al._ 2003](#Briggs)).

**Long-term usage.** The genre approach reflects community ownership and relative stability. Thus, electronic meeting systems should accommodate a long-term usage scenario, rather than focusing on single tasks or processes. Again, this perspective is challenging because it requires the systems consistently to preserve and manage historical records of past meetings. The notion of genre system provides the framework needed to preserve meeting occurrences in a meaningful way.

**Value production.** Meeting reports are fundamental to generating organizational value. Simple transcripts of the information acquired by the electronic meeting system may not produce value, even if post-produced by a human reporter, lacking malleability and openness. The meeting reports must be malleable to accommodate different views adjusted to specific targets (a process, department, agent or system). The meeting reports may also be open to reflect the underlying communication patterns that originated them, rather than opaque, with elements such as agenda items, decisions and future actions but no contextual cues or explaining factors.

We will substantiate these observations below. They may be summarized in the following hypotheses:

> **H4** - Genre based EMSs can be pre-configured for specific communities, avoiding the need of a facilitator to configure the technology.
> 
> **H5** - The genre approach improves the value of meeting outcomes.

**Case 3 - Electronic meeting systems for an accounting company**

This case concerns the design and implementation of an electronic meeting systems for Case 2 above (staff briefings in the accounting company). Design, implementation and validation are described below.

**Design.** When discussing the schema, we associated a pattern with the meeting genre system: the logistics and agenda precede the meeting, and the meeting is followed by the report (we use the terms 'precede' and 'follow' in a loose way). It thus makes sense to inform the electronic meeting system design with this knowledge. So far, this is not really innovative since most electronic meeting systems assume the same logical pattern. However, considering that the genre system is specialized according to the community, the electronic meeting system may be tailored to comply with the established patterns. For instance, the community may not have an agenda and thus the system should not require that an agenda be used.

Following the same line of thought, innovation may come from incorporating the properties of genres (why, what, who, when, where, how) used by the community into the design. In this case, the accounting company uses a specific type of report for staff briefings: a to-do list. The electronic meeting system should then support that purpose, content and form.

Innovation may also come from changes in medium. For instance, the agenda and report may become digital genres, allowing users to easily manipulate and search the available information. The meeting genre may also be transformed into a digital genre. This digital genre may be implemented with a shared whiteboard, thus preserving the face-to-face interaction, or a chat or videoconferencing tool, if remote interaction is envisaged. Our efforts in designing a solution for the accounting company were mostly centred on preserving face-to-face interaction, which turned us to the issue of transforming the agenda and report genres into digital genres.

Finally, innovation may also appear from supplying users with an integrated view of the meeting genre system rather than individual genres. This means the users will not only interact with genres, but they will be able to view genres within the context of the other genres making up the genre system. In summary, we followed these guidelines while designing the EMS for the accounting company:

*   Tailor the meeting genre system to the community practices.
*   Design digital genres to substitute previous genres, offering increased value.
*   Provide an integrated and historical view of the meeting genre system.

**Implementation.** We had to accomplish two tasks to implement the above requirements: (1) convert the agenda and report genres into concrete artefacts, including support for additional functionality; and (2) develop a management system for digital genres (see Figure 5). Task 1 was accomplished by developing agenda and report HTML pages. These pages were pre-configured to the specific needs of the accounting company (hypothesis H4). Forms within the agenda and report allow users to track agenda items, and manage projects, tasks, deadlines and allocated personnel. Task 2 is described below.

<div align="center">![figure5](p251fig5.gif)</div>

<div align="center">  
**Figure 5: Integrated view of the genre system for the accounting company electronic meeting system**</div>

**Validation.** Validation with users was more an ongoing cooperative process than a single task. Users started their participation in the genre elicitation phase and proceeded with the validation of the genre model. Then, they participated in the re-design of digital genres and, finally, ended their participation by validating the final prototype.

Our approach to validation consisted of setting up meetings with the users and discussing the electronic meetings system with them. Although this was a very informal approach, it allowed participants to express their concerns about the system freely. For instance, some of the people participating in the evaluation meetings expressed their concerns about flexibility threats, since the system could be too restrictive. These observations led us to avoid placing excessive constraints into the system.

We got good feedback on how outcomes from the system could satisfy group needs (hypothesis H4). From the several validation sessions we concluded that the genre approach was also well understood and accepted by users, allowing them to identify subtle problems with the system and to contribute suggestions to improve its design.

**Case 4 - Adding value to meeting reports**

This case describes how genre analysis may lead to the improvement of meeting reports and addresses specifically the validation of hypothesis H5\. The case involved a group of expert consultants in finance analysing the national budget.

**Design.** Typical meeting reports fall in one of these two categories: (1) a very long narrative, including a detailed list of participants, copy of the agenda, list of decisions made during the meeting and sometimes a transcription of the communications; or (2) a very brief reference to logistics plus a brief list of decisions made during the meeting. In both situations the meeting reports tend to satisfy archiving requirements.

However, the evolution to a digital genre introduces new opportunities for adding value ([Borges _et al._ 2004](#Borges2)); for example, easing dissemination of the meeting results throughout the organization, providing triggers for organizational action, supporting content search based on meeting metadata, or even preserving information about the genre system associated with the meeting report.

We investigated these opportunities using the Portuguese Parliament reports. Analysis of these reports revealed they fall into the narrative category, being extremely detailed, including a complete transcription of the dialogues as well as Congressmen's attitudes and behaviour. As a consequence, a report from a normal parliamentary session is long; typically seventy printed pages.

We set up an experiment to evaluate the value of Parliamentary reports to a group of expert consultants in finance. A meeting with these experts was set up to discuss the implications of the recently approved national budget. The group met face-to-face and had access to the Parliamentary report. At the end of the meeting we requested the participants to qualitatively evaluate the contribution of the report to their objectives. The obtained results made clear the available digital report did not produce value.

We then requested suggestions for improving the report. Some of the suggestions were: add links to specific parts of the document, divide the text into small manageable parts, organize the interventions from the same persons, add some contextual information and include a search engine for the various topics discussed during the session. Overall, the participants asked for a report suitable to their organizational goals.

**Implementation.** Based on the above observations, we developed a new digital genre for the Parliamentary report customized to the community. We incorporated a genre view of the Parliamentary session into the report. The report was organized according to the logistics, agenda, and meeting genres. Another genre was added to deliver the contextual information required to explain some of the interventions, proposals or decisions made. Official documents, newspapers, pictures, previous session reports can now be explicitly referenced in the report.

**Validation.** The improved digital genre was compared to the initial one. To accomplish this, we requested thirty-one students from economics classes to answer questions about the national budget while using the two genres. Afterwards, the students were requested to respond to a nine-point Likert scale questionnaire. Table 1 shows a partial list of the obtained results. There, the t-test for equality of means indicates that the opinions related to both agendas are significatively different. On the other hand, correlation analysis indicated that the perception of the agenda utility was the most important factor contributing to the perceived genre differences ([Costa 2002](#Costa1)). These results confirm that the improved genre is better suited to the participants' needs than the previous one. This, in turn, supports the claim that genre analysis improves the value of meeting outcomes (hypothesis H5).

<table width="80%" border="1" cellspacing="0" cellpadding="3" align="center" style="border-right: #99f5fb solid; border-top: #99f5fb solid; font-size: smaller; border-left: #99f5fb solid; border-bottom: #99f5fb solid; font-style: normal; font-family: verdana, geneva, arial, helvetica, sans-serif; background-color: #fdffdd"><caption align="bottom">  
**Table 1: Results from the questionnaire**</caption>

<tbody>

<tr>

<td colspan="2"> </td>

<th>Initial genre</th>

<th>Improved genre</th>

<td> </td>

<th>N</th>

<th>t</th>

<th>df</th>

<th>p</th>

</tr>

<tr>

<td>Frustrating</td>

<td align="center">Average</td>

<td align="center">3.6</td>

<td align="center">6.8</td>

<td>Very satisfactory</td>

<td>31</td>

<td>-7.02</td>

<td>60</td>

<td>0</td>

</tr>

<tr>

<td> </td>

<td align="center">S.D.</td>

<td align="center">1.8</td>

<td align="center">1.8</td>

<td colspan="5"> </td>

</tr>

<tr>

<td>Terrible</td>

<td align="center">Average</td>

<td align="center">4.1</td>

<td align="center">6.4</td>

<td>Wonderful</td>

<td>31</td>

<td>-5.68</td>

<td>60</td>

<td>0</td>

</tr>

<tr>

<td> </td>

<td align="center">S.D.</td>

<td align="center">1.5</td>

<td align="center">1.7</td>

<td colspan="5"> </td>

</tr>

<tr>

<td>Boring</td>

<td align="center">Average</td>

<td align="center">3.4</td>

<td align="center">6.2</td>

<td>Stimulating</td>

<td>31</td>

<td>-5.88</td>

<td>60</td>

<td>0</td>

</tr>

<tr>

<td> </td>

<td align="center">S.D.</td>

<td align="center">2.0</td>

<td align="center">1.8</td>

<td colspan="5"> </td>

</tr>

<tr>

<td>Hard</td>

<td align="center">Average</td>

<td align="center">3.8</td>

<td align="center">7.0</td>

<td>Easy</td>

<td>31</td>

<td>-6.33</td>

<td>60</td>

<td>0</td>

</tr>

<tr>

<td> </td>

<td align="center">S.D.</td>

<td align="center">1.9</td>

<td align="center">2.0</td>

<td colspan="5"> </td>

</tr>

<tr>

<td>Rigid</td>

<td align="center">Average</td>

<td align="center">3.9</td>

<td align="center">6.7</td>

<td>Flexible</td>

<td>31</td>

<td>-5.71</td>

<td>60</td>

<td>0</td>

</tr>

<tr>

<td> </td>

<td align="center">S.D.</td>

<td align="center">2.0</td>

<td align="center">1.9</td>

<td colspan="5"> </td>

</tr>

<tr>

<td>Hard to read</td>

<td align="center">Average</td>

<td align="center">3.8</td>

<td align="center">6.9</td>

<td>Very easy to read</td>

<td>31</td>

<td>-6.06</td>

<td>60</td>

<td>0</td>

</tr>

<tr>

<td> </td>

<td align="center">S.D.</td>

<td align="center">1.9</td>

<td align="center">2.2</td>

<td colspan="5"> </td>

</tr>

<tr>

<td>Inadequate</td>

<td align="center">Average</td>

<td align="center">4.6</td>

<td align="center">7.0</td>

<td>Adequate</td>

<td>31</td>

<td>-4.79</td>

<td>60</td>

<td>0</td>

</tr>

<tr>

<td> </td>

<td align="center">S.D.</td>

<td align="center">2.1</td>

<td align="center">1.9</td>

<td colspan="5"> </td>

</tr>

<tr>

<td>Inefficient</td>

<td align="center">Average</td>

<td align="center">4.3</td>

<td align="center">7.0</td>

<td>Efficient</td>

<td>31</td>

<td>-5.44</td>

<td>60</td>

<td>0</td>

</tr>

<tr>

<td> </td>

<td align="center">S.D.</td>

<td align="center">2.0</td>

<td align="center">1.8</td>

<td colspan="5"> </td>

</tr>

<tr>

<td>Unproductive</td>

<td align="center">Average</td>

<td align="center">4.6</td>

<td align="center">7.1</td>

<td>Productive</td>

<td>31</td>

<td>-5.08</td>

<td>60</td>

<td>0</td>

</tr>

<tr>

<td> </td>

<td align="center">S.D.</td>

<td align="center">2.1</td>

<td align="center">2.0</td>

<td colspan="5"> </td>

</tr>

</tbody>

</table>

## <a name="s4" id="s4"></a>Electronic meeting system implementation

The electronic meeting systems developed for the several situations described in this paper have a common three-tier architecture, using a client Web browser, meeting server and genre database. The genre database stores genres independently of their purpose, form and contents. The database structure follows the meeting genre system, which establishes the links between logistics, agenda, meeting and report genres and sub-genres. We avoided placing restrictions on the database based on any pre-conceived ideas about meeting processes. For instance, the database does not require a meeting to have an agenda or that the agenda should precede the meeting.

The meeting server offers several services related to genre management, such as enacting and using genres, viewing genres in the context of a genre system, searching genres or analysing historical links between genres. Furthermore, designers may use the meeting server to specify the genre repertoire for a community, characterizing genres (name, purpose, form, producers and consumers), sub-genres (ancestor, descendants) and genre relationships (precedence). The designers may also link genres to HTML templates implementing the genre purposes and forms. The meeting server resides on a Web server, allowing the available services to be accessible through a Web browser. Figure 6 shows several client interfaces to the meeting server.

<div align="center">![figure6a](p251fig7a.gif)</div>

<div align="center">  
**Figure 6a: Genre management: genre characterization**</div>

<div align="center">  
![figure6b](p251fig7b.gif)</div>

<div align="center">  
**Figure 6b: Genre management: hierarchy of sub-genres**</div>

<div align="center">  
![figure6c](p251fig7c.gif)</div>

<div align="center">  
**Figure 6c: Genre management: genre system.**</div>

The greatest advantage of using a browser as front-end is that it eases the implementation of genres: we use HTML templates to materialize genres and frames to organize and display the genre system. This solution offers two features required by our approach. One of them is flexibility. For instance, we have used the electronic meeting system described in Case 3 in both face-to-face and remote settings. The only new element we incorporated into the system, in the latter case, was a chat applet in the HTML template corresponding to the meeting genre.

The second feature of the approach is low implementation cost, assured by low effort required to set up HTML templates for agendas, reports and other genres. In fact, using this approach, we were able to develop several EMSs besides the one described in Case 3, some of them dedicated to supporting single meeting events.

One of these electronic meeting systems was developed for a general assembly meeting intended to approve annual financial reports. We had to develop HTML templates for the agenda and report genres to implement this system. Another system dealt with several marketing meetings related to a real estate project. The objective was to creatively develop a marketing slogan for the real estate project. We designed the system to support three types of meetings, devoted respectively to generating ideas, evaluating ideas and selecting a slogan. The design involved writing different HTML templates for the agenda and report genres. In the case of idea generation, we integrated a chat applet in the electronic meeting system, thus supporting a remote meeting. The other two meetings were held face-to-face. We also developed a very similar system for strategy meetings at a software company. Three meetings were held with the purpose of generating business ideas, evaluating ideas and creating an action plan. Some examples of these systems are shown in Figure 7\.

<div align="center">![figure7a](p251fig6a.gif)</div>

<div align="center">  
**Figure 7a: Electronic meeting system for a marketing meeting**</div>

<div align="center">  
![figure7b](p251fig6b.gif)</div>

<div align="center">  
**Figure 7b: Electronic meeting system for a discussion.**</div>

Overall, from these experiments we can observe each case required little effort to develop templates for the logistics, agenda and report genres. By contrast, support for the meeting genre is challenging because there are several design options to consider.

Despite the various types of electronic meeting systems we analysed, we make no claim of completeness. For instance, we have not addressed meeting preparation ([Borges _et al._ 1999](#Borges1)). However, the cases presented in previous sections clearly demonstrate the need to deploy a pre-configured electronic meeting system for a specific community of users.

## <a name="s5" id="s5"></a>Lessons learned and discussion

We have analysed and modelled various meeting genres: staff briefings, general assembly, marketing, strategy and discussion meetings. We developed pre-configured electronic meeting systems for these meeting genres. From these experiments we were able to draw several lessons summarized below.

**Genre analysis**

*   The genre concept was useful to clarify the organizational context of meetings. The approach resolved a difficult situation in preliminary design, when neither the problems nor solutions are sufficiently known to build a requirements list.
*   Genres were easily comprehended by the participants in genre analysis. The simple formalisms used to represent genres were sufficient to support their identification, discussion and validation by participants.
*   genre analysis did not cover 100% of the meeting genres, which means electronic meeting system implementations will not aim at full meeting support. However, the participants in genre analysis identified which genres were more important to their organization and did not seem worried about 100% coverage.
*   Most of the meetings we evaluated were very informal. The participants considered formalization of meetings to be inappropriate. Although the participants could provide us with several meeting patterns, they did not regard them as formal procedures. Focus on patterns seems to be a major strength of genre analysis.
*   Users understood the genre analysis process and agreed to participate in it. We felt that this technique was very successful, considering the typical time and effort constraints IT analysts commonly have. Success may be partly due to the circumstance that usually just two short meetings were enough to elicit and validate genre systems.
*   The portrayal of meetings as patterns including logistics, agenda, meeting itself and report were always valid in our experiments. Nevertheless, in several circumstances we had to include one additional genre (context genre, referencing external information) to support the discussion.
*   Meetings and meeting arrangements are typically not well documented in organizations. In addition, the perspectives are also very personal and people avoid sharing strategic data. Thus, the adoption of a cooperative elicitation process was very useful and efficient.

**Design of digital genres**

*   Digital genres were fundamental to electronic meeting system design, as natural targets for increasing organizational value of artefacts like the agenda and report.
*   The participants liked having reports reflecting the genre system.
*   Our approach to designing new digital genres involved a significant participation of users, who contributed many suggestions for improving value.
*   It was only at this phase of designing digital genres that a formal list of requirements started to be clear for the participants.

**Electronic management system design**

*   The participants were accustomed to working face-to-face and felt no need to use IT to improve meetings. This situation challenged electronic management system design, but the focus on communication (rather than functionality) allowed us to propose systems acceptable to the users.
*   The electronic management system can be pre-configured with genres pertaining to a community, which means that the system is general and special-purpose at the same time. Little development effort is required to pre-configure the system.
*   The participants confirmed that the most complex issue with the electronic management system concerns the meeting genre. Additional support in this area seems to raise negative reactions, except when meetings are remotely held.
*   A solution having satisfied participants has the preservation of team flexibility as a major feature. The electronic management system does not mandate formal work procedures but, instead, supports the recurrent work practices and types of information exchanged by the meeting participants.

**General implications for electronic management system design**

We will now discuss how far genre analysis has influenced electronic management system design. The observations presented below are based on a detailed comparison of our approach with other commercial and research electronic management systems developed elsewhere ([Antunes & Costa 2003](#Antunes1), [Costa 2002](#Costa1)).

**Organizational integration.** A meeting is one of many mechanisms for coordinating work in organizations. Thus, there is a natural emphasis on organizational integration (emphasizing the roles of logistics, agenda and report as triggers for action) and less focus on the meeting itself. This should be contrasted with other approaches stressing support for the meeting itself (e.g., generate ideas, organize ideas, and vote).

**Pre-configuration.** The genre-based electronic management system manages genres that are pre-configured to a specific community. As a consequence, no expert facilitator is required to handle the system. This should be contrasted with mostly generic purpose electronic management systems where configuration is complex and participants must assign that important task to a facilitator.

**Long-term usage.** Genres highlight the fact meeting occurrences and effects may span across long time periods. Thus, electronic management systems must preserve and integrate meeting information in the long run. This should be contrasted with electronic management systems focused on single tasks or processes.

**Patterns.** Genres highlight patterns, not processes. The genre-based electronic management system avoids managing high-level and complex issues associated with decision-making processes (e.g., strategy, negotiation, team-building).

**Meeting memory.** The digital artefacts reflect and preserve the genre system which originated them, providing many contextual cues and explaining factors necessary to make them usable within the organization.

**General implications to IT design**

Meetings involve a very significant effort to coordinate work in organizations. Therefore, it is expected that the adoption of electronic management systems in organizations has a strong impact, something that has yet to be accomplished. However, we would like to emphasize two characteristics of genre-based electronic management systems showing alternative paths for future IT developments in the organizational context. The first is related to the support for informality and flexibility. The genre approach addresses the informal and flexible mechanisms needed to accomplish work but frequently undocumented by organizations. This approach thus complements formal methods such as workflow. Note that workflow sometimes fails under exceptional occurrences because it lacks adaptability ([Mourão & Antunes 2004](#Mourao)).

The second characteristic we highlight is the special-purpose support. The development of general-purpose systems has always been an endeavour for economic reasons. Following a different path, the genre approach leads to the development of special-purpose systems aiming to support a single community of users, sometimes even for a single event. The implementations described in this paper showed us that this alternative approach may be viable, thanks to an easy way of pre-configuring the system.

## <a name="s6" id="s6"></a>Conclusions

Our hypotheses concerning the impact of genre analysis on electronic management systems were validated in the several case studies described in this paper. Obviously, this does not mean that they are formally proved, but a considerable engineering work has been done to validate them with varied organizations, target users, types of meetings and analysis techniques.

This research provides the following contributions to electronic management systems design. It highlights the organizational dimension of such systems, showing that electronic meetings are not isolated but rather interconnected with other organizational genres. It shows that an electronic management system can be pre-configured to a community and meeting type without much effort. It provides an approach to avoiding having a facilitator configuring the system. It also introduces a long-term view of electronic meetings, where meeting information produced in the past must be integrated in present meetings. The proposed solution focuses more on patterns than processes, avoiding formalized work and emphasizing informality and flexibility. Finally, the meeting memory produced by the design solution reflects the underlying genres and genre systems, preserving many contextual cues and explaining factors about work in meetings.

## Acknowledgements

This work was partially supported by grant No. 1040952 from Fondecyt (Chile).

## References

*   <a name="Antunes1" id="Antunes1"></a>Antunes, P. & Costa, C. (2003). Perceived value: a low-cost approach to evaluate meetingware. _Lecture Notes in Computer Science_, **2806**, 109-125.
*   <a name="Antunes2" id="Antunes2"></a>Antunes, P., Costa, C. & Dias, J. (2001). Applying genre analysis to EMS design: the example of a small accounting firm. In _7th International Workshop on Groupware (CRIWG 2001)_ (pp. 74-81). IEEE Computer Society Press.
*   <a name="Antunes3" id="Antunes3"></a>Antunes, P. & Ho, T. (2001). The design of a GDSS meeting preparation tool. _Group Decision and Negotiation_, **10**(1), 5-25.
*   <a name="Bazerman" id="Bazerman"></a>Bazerman, C. (1988). _Shaping written knowledge: the genre and activity of the experimental article in science_. Madison, WI: University of Wisconsin Press.
*   <a name="Bergquist1" id="Bergquist1"></a>Bergquist, M. & Ljungberg, F. (1998). From memo to intranet. In Buch, N.J., Damsgaard, J., Eriksen, L.B., Iversen, J.H., & Nielsen, P.A. (eds.), Proceedings of IRIS 21\. Aalborg, Denmark: Department of Computer Science, Aalborg University.
*   <a name="Bergquist2" id="Bergquist2"></a>Bergquist, M. & Ljungberg, F. (1999). Genres in action: negotiating genres in practice. In _Proceedings of the 32nd Hawaii International Conference on System Sciences._ IEEE Computer Society Press.
*   <a name="Beyer" id="Beyer"></a>Beyer, H. & Holtzblatt, K. (1998). _Contextual design: defining customer-centered systems_. San Francisco, CA: Morgan Kaufmann.
*   <a name="Borges1" id="Borges1"></a>Borges, M.R.S., Pino, J.A., Fuller, D.A., & Salgado, A.C. (1999). Key issues in the design of an asynchronous system to support meeting preparation. _Decision Support Systems_, **27**, 269-287.
*   <a name="Borges2" id="Borges2"></a>Borges, M.R.S., Pino, J.A., & Araujo, R. (2004). Bridging the gap between decisions and their implementation. _Lecture Notes in Computer Science_, **3198**, 153-165.
*   <a name="Bostrom" id="Bostrom"></a>Bostrom, R., Anson, R., & Clawson, V. (1993). Group facilitation and Group Support Systems. In L.M. Jessup & J.S. Valacich (eds.), _Group Support Systems - New Perspectives_ (pp. 146-168). New York, NY: Macmillan Pub. Co.
*   <a name="Bregman" id="Bregman"></a>Bregman A. & Haythornthwaite, C. (2001). Radicals of presentation in persistent conversation. In _Proceedings of the 34th Hawaii International Conference on System Sciences._ IEEE Computer Society Press.
*   <a name="Briggs" id="Briggs"></a>Briggs, R., Vreede, G., & Nunamaker, J. (2003). Collaboration engineering with ThinkLets to pursue sustained success with group support systems. _Journal of Management Information Systems_, **19**(4), 31-64.
*   <a name="Costa1" id="Costa1"></a>Costa, C. (2002). _Organizational integration of meeting results_. Ph.D. Thesis, ISCTE. (in Portuguese).
*   <a name="Costa2" id="Costa2"></a>Costa, C. & Antunes, P. (2001). Meetings as genre systems: some consequences for EMS design. In F. Ackermann & G.J. de Vreede, (eds.), _Proceedings of Group Decision and Negotiation 2001\. Group Decision & Negotiation 2001, La Rochelle, France, 4-7 June 2001._ (pp. 261-263). Delft, Netherlands: Delft University of Technology, Faculty of Technology, Policy and Management.
*   <a name="Costa3" id="Costa3"></a>Costa, C., Antunes, P., & Dias, J. (2000). Supporting the meeting report process. In L. Svensson, U. Snis, C. Sørensen, H. Fägerlind, T. Lindroth, M. Magnusson, _et al._ (Eds.) _Proceedings of the 23rd Information Systems Research Seminar in Scandinavia, IRIS 23_ (pp. 1141-1150). Uddevalla, Sweden: Laboratorium for Interaction Technology, University of Trollahattan Uddevalla.
*   <a name="Costa4" id="Costa4"></a>Costa, C., Antunes, P., & Dias, J. (2001a). EMS/PDA: connecting meetings with people in organizations. In S. Bjørnestad, S., R.E. Moe, A.I. Mørch, & A.L. Opdahl, (Eds.) _Knowledge Systems - Proceedings of the 24th Information Systems Research Seminar in Scandinavia (IRIS 24)_. Bergen, Norway: University of Bergen
*   <a name="Costa5" id="Costa5"></a>Costa, C., Antunes, P., & Dias, J. (2001b). A model for organizational integration of meeting outcomes. In M.K. Sein, B. Munkvold, T. Ørvik, W. Wojtkowski, W.G. Wojtkowski, J. Zupancic _et al._ (Eds.), _Contemporary trends in systems development_. Dordrecht, Netherlands: Kluwer Academic and Plenum Press.
*   <a name="Costa6" id="Costa6"></a>Costa, C., Antunes, P., & Dias, J. (2002). Integrating two organisational systems through communication genres. _Lecture Notes in Computer Science_, **2315**, 125-132.
*   <a name="Crowston" id="Crowston"></a>Crowston K. & Williams, M. (2000). Reproduced and emergent genres of communication on the World-Wide Web. _The Information Society_ **16**(3), 201-216.
*   <a name="Erikson" id="Erikson"></a>Erikson, T. (2000). Making sense of computer-mediated communication (CMC): conversations as genres, CMC systems as genre ecologies. In _Proceedings of the 33rd Hawaii International Conference on System Sciences_. Washington, DC: IEEE Computer Society Press.
*   <a name="Fjermestad" id="Fjermestad"></a>Fjermestad, J. & Hiltz, S. (1999). An assessment of group support systems experimental research: methodology and results. _Journal of Management Information Systems_, **15**(3), 7-149\.
*   <a name="Habermas" id="Habermas"></a>Habermas, J. (1998). _On the pragmatics of communication_. Cambridge, MA: The MIT Press.
*   <a name="Ihlstrom" id="Ihlstrom"></a>Ihlstrom, C. & Lundberg, J. (2004). A genre perspective on online newspaper front page design. _Journal of Web Engineering_, **3**(1), 50-74\.
*   <a name="Karjalainen" id="Karjalainen"></a>Karjalainen, A. & Salminen, A. (2000). Bridging the gap between hard and soft information genres. In M. Khosrowpour (Ed.), _Challenges of Information Technology Management in the 21st Century. 2000 Information Resources Management Association International Conference, Anchorage, Alaska._ (pp. 92-95). Hershey, PA: Idea Group Publishing.
*   <a name="Katz" id="Katz"></a>Katz, D. & Kahn, R. (1978). _The social psychology of organizations_. 2nd. ed. New York, NY: John Wiley & Sons.
*   <a name="Lacey" id="Lacey"></a>Lacey, N. (2000). _Narrative and genre: key concepts in media studies_. New York, NY: St. Martin's Press.
*   <a name="Myers" id="Myers"></a>Myers, M.T. & Myers, G.E. (1982). _Managing by communication: an organizational approach_. New York, NY: McGraw-Hill.
*   <a name="Mourao" id="Mourao"></a>Mourão, H. & Antunes, P. (2004). Exception handling through a workflow. _Lecture Notes in Computer Science_, **3290**, 37-54.
*   <a name="Nunamaker" id="Nunamaker"></a>Nunamaker, J., Briggs, R., Mittleman, D., Vogel, D., & Balthazard, P. (1997). Lessons from a dozen years of group support systems research: a discussion of lab and field findings. _Journal of Management Information Systems_, **13**(3), 163-207.
*   <a name="Oravec" id="Oravec"></a>Oravec, J. (1996). _Virtual individuals, virtual groups: human dimensions of groupware and computer networking_. Cambridge: Cambridge University Press.
*   <a name="Orlikowski" id="Orlikowski"></a>Orlikowski, W. & Yates, J. (1994). Genre repertoire: the structuring of communicative practice in organizations. _Administrative Science Quarterly_, **39**, 547-574\.
*   <a name="Pargman" id="Pargman"></a>Pargman, T. & Lantz, A. (2002). The role of "genre" in the analysis of the use of videoconference systems at work. NordiCHI. Arhus, Denmark.
*   <a name="Procter" id="Procter"></a>Procter, R., Goldenberg, A., Davenport, E., & McKinlay, A. (1998). Genres in support of collaborative information retrieval in the virtual library. _Interacting with Computers_, **10**, 157-175\.
*   <a name="Rauber" id="Rauber"></a>Rauber A., & Kogler, A. (2001). Integrating automatic genre analysis into digital libraries. In Proceedings of the First ACM/IEEE-CS Joint Conference on Digital Libraries. Roanoke, Virginia: ACM Press.
*   <a name="Romano" id="Romano"></a>Romano, N. & Nunamaker, J. (2001). Meeting analysis: findings from research and practice. In Proceedings of the 34th Hawaii International Conference on Systems Science. Washington, DC: IEEE Computer Society Press.
*   <a name="Roussinov" id="Roussinov"></a>Roussinov, D., Crowston, K., Nilan, M., Kwasnik, B., Cai, J., & Liu, X. (2001). Genre based navigation on the Web. In Proceedings of the 34th Hawaii International Conference on System Sciences. Washington, DC: IEEE Computer Society Press.
*   <a name="Spinuzzi1" id="Spinuzzi1"></a>Spinuzzi, C. (1999). Grappling with distributed usability: a cultural-historical examination of documentation genres over four decades. In Proceedings of the 17th annual international conference on computer documentation (pp. 419-432). New Orleans: ACM Press.
*   <a name="Spinuzzi2" id="Spinuzzi2"></a>Spinuzzi, C. (2000). Genre ecologies: an open-system approach to understanding and constructing documentation. _ACM Journal of Computer Documentation_, **24**(3), 169-181\.
*   <a name="Spinuzzi3" id="Spinuzzi3"></a>Spinuzzi, C. (2003). _Tracing genres through organizations: a sociocultural approach to information design_. Cambridge, MA: The MIT Press.
*   <a name="Teeni" id="Teeni"></a>Te'eni, D. (2001). Review: A cognitive-affective model of organizational communication for designing IT. _MIS Quarterly_, **25**(2).
*   <a name="Tyrvainen" id="Tyrvainen"></a>Tyrvainen, P. & Paivarinta, T. (1999). On rethinking organizational document genres for electronic document management. In Proceedings of the 32nd Hawaii International Conference on System Sciences. Washington, DC: IEEE Computer Society Press.
*   <a name="Yates1" id="Yates1"></a>Yates, J. & Orlikowski, W. (1992). Genres of organizational communication: a structurational approach to studying communication and media. _Academy of Management Review_, **17**(2), 299-326.
*   <a name="Yates2" id="Yates2"></a>Yates, J., Orlikowski, W., & Okamura, K. (1999). [Explicit and implicit structuring of genres: electronic communication in a japanese R&D organization](http://ccs.mit.edu/papers/CCSWP188.html). _Organization Science_, **10**(1), 83-103\. [Working paper version retrieved 14 January, 2006 from http://ccs.mit.edu/papers/CCSWP188.html]
*   <a name="Yates3" id="Yates3"></a>Yates, J. & Orlikowski, W. (2002). Genre systems: structuring interaction through communicative norms. _Journal of Business Communication_, **39**(1), 13-35.
*   <a name="Yin" id="Yin"></a>Yin, R. (1994). _Case study research: design and methods_. Thousand Oaks, CA: Sage Publications Inc.
*   <a name="Yoshioka1" id="Yoshioka1"></a>Yoshioka, T. & Herman, G. (2000). _[Coordinating information using genres](http://ccs.mit.edu/papers/pdf/wp214.pdf)_. Cambridge, MA: Massachusetts Institute of Technology, Center for Coordination Science. (Working paper CCS No. 214, Sloan No. 4127). Retrieved 14 January, 2006 from http://ccs.mit.edu/papers/pdf/wp214.pdf
*   <a name="Yoshioka2" id="Yoshioka2"></a>Yoshioka, T., Herman, G., Yates, J., & Orlikowski, W. (2001). Genre taxonomy: a knowledge repository of communicative actions. _ACM Transactions on Information Systems_, **19**(4), 431-456\.
*   <a name="Zachry" id="Zachry"></a>Zachry, M. (1999). Constructing usable documentation: a study of communicative practices and the early uses of mainframe computing in industry. In Proceedings of the 17th annual international conference on computer documentation (pp. 22-25). New Orleans: ACM Press.



