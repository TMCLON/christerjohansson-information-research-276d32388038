####  vol. 13 no. 2, June 2008

# An activity-theory-based model to analyse Web application requirements

#### [Lorna Uden](mailto:l.uden@staffs.ac.uk)  
Faculty of Computing, Engineering and Technology, Staffordshire University, The Octagon, Beaconside, Stafford, ST18 OAD. UK  
[Pedro Valderas](mailto:pvalderas@dsic.upv.es) and [Oscar Pastor](mailto:opastor@dsic.upv.es)  
Department of Information Systems and Computation, Technical University of Valencia, 46022 Cami de Vera s/n, Valencia, Spain

#### Abstract

> **Introduction**. Few proposals for modelling and developing Web applications, deal with how to properly elicit and represent Web application requirements. Web applications introduce unique characteristics such as navigation that are not properly considered at the requirements level. In this paper, we seek to improve on improve on existing methods through the use of cultural-historical activity theory.  
> **Elaboration**. First the main notions of activity theory are analysed and an activity theory based model to analyse Web applications is defined. This is a task model, which we show can be used in requirements engineering by applying it in the analysis of an e-commerce application.  
> **Results**. The main contribution of this work is the definition of a requirements engineering approach based on Activity Theory which is ideally suited to properly handle Web application requirements. This approach allows us to properly capture navigational and organizational requirements of Web applications.  
> **Conclusions**. Activity Theory constitutes a valuable tool for analysing software requirements. Furthermore, the use of a task-based Activity Theory model provides Web application developers with a model that allows them to properly specify navigational and organizational requirements.



## Introduction

It is well known that effective and efficient requirements engineering activities are absolutely essential if software systems are to meet the expectations of their customers and users, and are to be delivered on time and within budget ([Al-Rawas and Easterbrook 1996](#Al-Rawas96)). Requirement engineering is typically not taken into account in Web application development. In a survey carried out by [McDonald and Welland (2001)](#McDonald01), Web application developers claim that most of their Web development projects are running over budget and time because of problems in capturing requirements and poor communication between themselves and their clients.

_Capturing requirements_ was one of the most important problems to be solved when Web engineering was introduced at the beginning of the current decade ([Deshpande _et al._ 2002](#Deshpande02)). However, although a significant number of proposals has been presented that provide methodological solutions for developing Web applications, they mainly focus on defining Web applications from conceptual models and do not pay much attention to the requirements engineering activity ([Escalona and Koch (2004)](#Escalona04)).This lack of specific requirements engineering techniques for Web applications has been also detected in other works such as England and Finney ([1999](#England99)), Burdman ([1999](#Burdman99)), Overmyer ([2000](#Overmyer00)) and Lowe ([2003](#Lowe03)) which state that new requirements engineering methods are needed for Web applications because of requirements engineering methods for traditional software are not appropriate to support the unique characteristics of Web application development.

One of the unique characteristics of Web applications is that, mainly, they focus only on providing information. Since the World Wide Web is an information medium ([Greenspun 1999](#Greenspun99)), many Web applications are fully or partially developed as magazines or brochures and their development only involves capturing and organizing a complex information domain and making that domain accessible to users. The information is organized in a structure made up of nodes, links and anchors (according to the hypertext paradigm ([Conklin 1987](#Conklin97))), which allow users to _navigate_ through the information in a nonlinear way. It is important, therefore, at the early stages of Web application development, to consider the best navigational structure that will allow users to navigate through the provided information. In this context, although requirements engineering methods for traditional software such as Constantine and Lockwood ([1999](#Constantine99)), Jaaksi ([1998](#Jaaksi98)), Leite _et al._ ([1998](#Leite98)) or Rosenberg _et al._ ([1999](#Rosenberg99)) have done excellent work in capturing structural and behavioural requirements, they do not explicitly deal with the navigational aspect.

On the other hand, _the communication between developers and clients_ is a very important aspect in requirements engineering which makes requirements engineering sensitive to how people perceive and understand the world around them, how they interact with it, and how the sociology of the workplace affects their actions. This human factor in requirements engineering is not only concerned with disciplines that handle technical aspects, but also in disciplines that handle cultural, cognitive or social aspects ([Goguen and Jirotka 1994](#Goguen94)). In this context, the requirements elicitation problem becomes unsolvable if we use methods that are based entirely upon individual cognition and ignore organizational requirements ([Goguen and Linde 1993](#Goguen93)).

Organizational requirements are those that are captured when a system is being viewed in a social context rather than from a purely technical, administrative or procedural view of the functions to be performed. Sources of such requirements could be power structures, roles, obligations, responsibilities, control and autonomy issues, values and ethics ([Avison & Wood-Harper 1990](#Avison90)). These types of requirements are so deeply embedded in organizational structure and policies that often they cannot easily be directly observed or articulated. Most established requirements engineering techniques however, do not adequately address the critical organizational and ‘softer', people-related issues of software systems.

From the above discussion, it would seem that current requirements engineering models could not provide a theoretical basis for understanding 'regularly patterned' human activity ([Probert 1999](#Probert99)). In order to overcome these mentioned problems, it is necessary to have a methodology and tools that can support the continuous evaluation of a statement of requirements as these evolve against a highly complex and dynamic problem situation. What is needed is to shift the focus from fixed and final requirements to those of a more dynamic nature. In particular, it is necessary to consider human information which, in social terms, does not have a physical reality and is not objective like physical information media. Instead, it is based on individual, group or organizational needs. Such information informs action in organizations and is thus closely related to organizational activity and organizational form.

In this paper, we address the two problems presented above by introducing a requirements engineering method for Web applications that is defined from cultural-historical activity theory ([Engeström 1987)](#Engestrom87). First, we believe that applying activity theory to requirements engineering provides us with a conceptual framework that allow us to address the important issue of organizational requirements. Activity theory focuses on the interaction of human activity and consciousness within its relevant environmental context ([Vygotsky 1978](#Vygotsky78)). The basic unit of analysis in activity theory is human activity. Activity theory incorporates notions of understanding, history, mediation, motivation, culture and community. In this context, activity theory enables us to shift the focus of requirements engineering from the interaction between isolated and stand-alone systems to a larger, more ecologically and valid interaction between human beings and their environments.

We present a task model to analyse Web applications based on the principles of activity theory in order to overcome the limitations of traditional task analysis methods. This is properly to support the description of human activities and the related information to the environmental context (that is, activity theory notions). The proposed extensions have been introduced considering the navigational aspect of Web applications as a priority in requirements engineering activities. Thus, we provide mechanisms, such as temporal constraints between activities, that allow us to extract valuable semantics that can be used to derive the proper Web application navigational structure from requirements.

To sum up, the main contributions of this paper are the following:

*   We apply the concepts of activity theory in the requirements engineering activities of Web applications. This allows us to consider organizational requirements which capture the cultural, cognitive and social aspects that are related to requirements engineering.
*   We complement the theoretical pillars provided by activity theory with a description technique which extends traditional task analysis techniques, which provides us with mechanisms to handle properly the navigational requirements of Web applications.
*   Additionally, we present a practical example of how activity theory is applied to perform requirements activities in the development of a case study. This case study is an e-commerce application similar to the [Amazon online bookshop](http://www.amazon.com)

## Related work

In this section, we describe related work on requirements engineering for Web applications. In particular, we analyse how navigational and organizational requirements are handled in three different contexts: requirements engineering ([Hofman 2000](#Hofman00)), human-computer interaction ([Grechenig and Tscheligi 1993)](#Grechenig93) and Web engineering ([Deshpande _et al._ 2002](#Deshpande02)).

In the context of requirements engineering, we can find approaches such as Constantine and Lockwood ([1999](#Constantine99)), Jaaksi([1998](#Jaaksi98)), Leite _et al._ ([1998](#Leite98)) or Rosenberg et al. ([1999](#Rosenberg99)) that are mainly focused on traditional requirements, such as functional or data requirements, and they do not explicitly handle navigational requirements. They use requirements engineering techniques such as use cases or scenarios. Although these techniques are suitable for the Web Application development, they do not consider specific characteristics of Web applications such as navigation. These approaches to software development also lack an effective theoretical basis to deal with the complexities involved in the identification of the requirements of the different stakeholders involved in Web system development.

Work such as that of Robert _et al._ ([1998](#Robert98)), Nunes and Cunha ([2000](#Nunes00)), Harmelen ([2001](#Harmelen01)) and Vanderdonckt and Berquin ([1999](#Vanderdonckt99)) for human-computer interaction are focused on user interface requirements. These approaches use graphical models such as use cases, task diagrams, or sequence diagrams in order to obtain user interface specifications. The aim of these methods is the design of user interfaces with their visual components and the identification of the window (form) activation sequence (usually defined by means of state diagrams). Approaches of this kind are usually focused on traditional window applications (non-Web). The ultimate goal of these approaches is to obtain design models at the solution space level. What we want to achieve is to capture navigation in the requirements model.

Furthermore, according to Kaptelinin ([2000](#Kaptelinin00)), traditional approaches to human-computer interaction requirements analysis were dominated by the cognitive approach. This approach is characterized as transformation of human processing caused by new artefacts. Although this perspective appears to be useful in certain respects, there are several shortcomings. These include ([Kaptelinin 2000](#Kaptelinin00)):

*   the cognitive approach separates cognition from action and is only interested in the former,
*   mental processes other than cognitive ones, such as motivation and emotions are considered to be outside the scope of analysis, and
*   social interaction is rarely the object of cognitive studies.

There is an emerging consensus among researchers that the cognitive approach to human-computer interaction may be limited. It does not provide an appropriate conceptual basis for studies of computer use in its social, organizational and authorial context, in relation to the goals, plans and values of the user or in the context of development ([Uden and Willis2001](#Uden01)). Activity theory provides a broad theoretical framework for describing the structure, development and context of human activity.

Finally, in the context of Web engineering, Web applications require a more extensive and detailed requirements engineering process because of the number of stakeholders involved and the diversity of the requirements including, among others, requirements on the navigation ([Escalona and Koch 2004](#Escalona04)). However, navigation is often ignored at the requirement stage of development.For instance, approaches such a Web services distributed management ([De Troyer 2003](#DeTroyer03)) although proposed as task-based model, is used in the definition of business processes and requirements are textually described by means of scenarios. Other approaches such as UML-based Web engineering (UWE) ([Koch 2000](#Koch00)) or object-oriented hypermedia (OOH) ([Gómez _et al. 2000_](#Gomez00))introduce the definition of use case diagrams to specify Web application requirements and the different kinds of users. In addition, a process model (based on tasks or activities) is included to model the business process of Web applications. However, this model is used to complement a preliminary class diagram already defined from use cases. In this context, decisions about navigation must be taken from use cases. This is a traditional technique which does not properly consider specific characteristics of navigation. The object-oriented hypermedia design model (OOHDM) ([Schwabe _et al._ 1996](#Schwabe96)) introduces techniques for early requirements handling.

Text-based descriptions of use cases are complemented with _user interaction diagrams_, each of which graphically describes the information exchange between the application and the user in order to detect the navigational requirements. This approach mainly focuses on capturing the hypermedia design of Web applications. Interaction diagrams describe the information the user can access in every step of a _use case_ as well as the operations the user can activate. However, they do not consider relations between different interaction diagrams. We solve this problem by capturing requirement by using activity theory notions that introduce concepts such as activity, action and operation which are related throughout precise relationships. These concepts together with their relationships can be used to support the definition of navigational requirements.

Our work also differs from all these Web engineering approaches in that we provide well-defined theoretical principles upon which the requirements engineering method is based. This aspect allows us to improve the requirement engineering process by considering cultural, cognitive or social aspects related to the human activity that is performed during the requirements engineering stages. Furthermore, activity theory provides a precise interpretation of our abstractions avoiding possible ambiguities and allowing a better understanding.

## Activity theory background

Activity theory has evolved through three generations of research ([Engeström 2001](#Engestrom01)). The first generation drew heavily on Vygotsky's ([1978](#Vygotsky78)) conception of mediation The idea was crystallised in Vygotsky's famous triangular model in which the conditioned direct connection between stimulus (S) and responses (R) was transcended by a complex mediated act. The limitation of the first generation was that the unit of analysis remained individually focused. This was overcome by the second generation, based on Leont'ev's work ([1978](#Leont78)). In relation to Leont'ev, Engeström ([1999](#Engestrom99)) advocates the study of tools or artefacts as integral and inseparable components of human functioning. He argues that the focus of the study of mediation should be on its relationship with the other components of an activity system. The third generation of activity theory takes joint activity or practice (rather than individual activity or practice) as the unit of analysis for activity theory.

Engeström's analysis is concerned with the process of social transformation and incorporates the structure of the social world, with particular emphasis upon the conflictual nature of social practice. Instability and contradictions are the motive force of change and development and the transitions and reorganization within and between activity systems are parts of the evolution. The aim of the third generation of activity theory is to understand dialogues, multiple perspectives and networks of interacting activity systems. In activity theory, the human mind emerges, exists and can only be understood within the context of human interaction with the world and this interaction, i.e., activity, is socially and culturally determined ([Kaptelinin _et al._ 1999](#Kaptelinin99)).

Activity theory focuses on the interaction of human activity and consciousness within its relevant environmental context ([Vygotsky 1978](#Vygotsky78); [Leont'ev 1981](#Leontev81)). The basic unit of analysis in activity theory is human activity. Human activities are driven by certain needs where people wish to achieve certain purposes. It is obvious that activity cannot exist as an isolated entity. The very concept of activity implies that there is an agent who acts (an individual or collective _subject_). An activity is undertaken by a subject (individual or subgroup) using tools to achieve an object (objective) thus transforming objects into outcomes. Relations between elements of an activity are not directed, but mediated.

The relationship between subject and object of activity is mediated by a tool. A tool can be anything used in the transformation process, including both material tools and tools for thinking. Transforming the object into an outcome requires various tools (e.g., computers, software, methods, ideas, procedures, Internet, paper, pen etc.). The object is seen and manipulated not _as such_, but within the limitations set by the tools ([Kuutti 1996](#Kuutti96)). Artefacts are created and transformed during the development of the activity itself and carry with them a particular culture; a historical remnant of that development.

The relationship between subject and the community is mediated by rules. Rules cover both implicit and explicit norms, conventions and social relations within a community as related to the transformation process of the object into an outcome. Rules in our case consist of organizational practices and policies, working hours, working regulations, etc. The relationship between object and community is mediated by the division of labour: how the activity is distributed among the members of the community. That is, the role each individual in the community plays in the activity, the power each wields and the tasks each is held responsible for. Each of the mediating terms is historically formed and opens to further development ([Kuutti 1996](#Kuutti96)). The basic structure of an activity can be illustrated as in Figure 1.

<div align="center">![Basic structure of an activity](p340fig1.gif)</div>

<div align="center">  
**Figure 1: Basic structure of an activity.**</div>

Thus, activity has double nature, both an external and an internal side. The subject and object of an activity are in a reciprocal relationship. The subject transforms the object. Conversely, the properties of the object penetrate into the subject and transform him or her. This is called internalisation ([Kuutti 1996](#Kuutti96))

Finally, although time is a crucial part of context, Figure 1 does not reflect this. It is important not only to include current time, but also past time (a history element of context) and future time (to allow for prediction of a user's action from current context). To do this we adopted the context modelling of [Kaenampornpan and O'Neil (2004)](#Kaenampornpan04) as shown in Figure 2.

<div align="center">![Representing the history of activity theory](p340fig2.gif)</div>

<div align="center">  
**Figure 2: Representing the history of activity theory (adapted from [Kaenampornpan and O'Neil 2004](#Kaenampornpan04))**</div>

### Activities, actions and operations

According to Kuutti ([1996](#Kuutti96)) activities can be considered as having three hierarchical levels: activity, action and operation, which can be individual or cooperative. They can be considered as corresponding to motive, goal and conditions. An activity (global) may be achieved through a variety of actions. The same action may be used as contribution to different activities. Similarly, operations may contribute to a variety of actions (See Figure 3). Kuutti uses a simple example of these levels to describe the activity (motive) of _building a house_ in which _fixing the roof_ and _transporting bricks by truck_ are at the action level and _hammering_ and _changing gears_ when driving are at the operation level. Every activity has an internal and external component with the subject and object existing as part of a dynamic and reciprocal relationship.

<div align="center">![The three levels of activity](p340fig3.gif)</div>

<div align="center">  
**Figure 3:The three levels of activity.**</div>

Activity theory provides us a means to analyse the dynamics of the application as it distinguishes between motives, goals and conditions. When conditions change, operations become perturbed and the system adapts to the new situation automatically. When goals are disturbed, new goals are constructed, providing that motives remain stable. The activity changes when the motive changes. The future is unpredictable ([Kaptelinin 1996](#Kaptelinin96)). This distinction provides the means to define levels of collaborative activity: condition, goal and object-based ([Engeström 1987](#Engestrom87)).

In condition-based activities, users work towards a common objective. However, their individual actions are related to each other externally and they are unaware of the common objective. The goal-based form occurs when the common object is stable and shared by users, while the means might not be known or agreed upon. The object-based form occurs when the object of the work is blocked and needs to be constructed together ([Bardram 1998](#Bardram98)).

In activity theory, tasks are goal-driven when they are performed consciously, while actions are dependent upon operational conditions of the task and become automatic through routine use or practice. This distinction is important because it reveals the different task structure: a fundamental layer that does not depend on the target platform and an operational layer.

The three levels of collaborative activity are not separate entities, but rather systematic relationships, relating to needs, intentions and conditions. A motive and a goal may remain constant; the ways of achieving the results may differ according to the circumstances. The motives, goals and operational constituents are not arbitrary, but flexible and dynamic.

Activities may loose their motives and become included as parts of other activities, i.e., carried out as goal-directed actions realising other activities. Actions may be automated and frozen when carried out repeatedly under similar circumstances, making conscious control unnecessary, thus transforming the acts into operational constituents of an action. This transformation may also work the other way round, making a living, dynamic structure ([Baerentsen and Trettvik 2002](#Baerentsen02)).

However, activities are realised by actions that are defined by their conscious intentions ([Baerentsen and Trettvik 2002](#Baerentsen02)). Actions are what are talked about when one is asked what one is doing. The intention and the conditions that are directly related to the achievement of goals are normally in focus for conscious awareness. Conditions are not related to goals and they are not conscious ([Leont'ev 1978](#Leont'ev78)).

Although concrete conditions, such as the physical layout of the environment, are not directly relevant to the achievement of goals it is necessary to adapt the form of the activity to them. These conditions are relevant to the form of the actions, i.e., the operations by which the actions are realised and must be taken into account by the sensory-motor control if the actions are to succeed.

## Applying activity theory to the analysis of Web application requirements

In this section, we present a practical example of how activity theory is used in the analysis of a Web application. This Web application is an e-commerce application, which provides support for the online purchase of products. In this example, the basic unit of analysis for our case study is the activities that users need to carry out with the application. It is based on contributions from Engeström ([1987](#Engestrom87)); Jonassen & Rohrer-Murphy ([1999](#Jonassen99)), Bodker ([1996](#Bodker96)), Mwanza ([2001](#Mwanza01)) and Uden ([2007](#Uden07)). The methodology consists of the following steps:

1.  **_Clarify the purpose of the activity system._** It is important to clarify the motives and goals of the activity system. The purpose of this step is twofold: (a) to understand the context within which activities occur and (b) to reach a thorough understanding of the motivations for the activity being modelled and any interpretations of perceived contradictions.  
    _The purpose of the case study is to provide support for the online purchase of CDs, software and books. This online purchase must be performed throughout a Web application. Users must be able to purchase products from every computer with Internet connection and at every time._  
    What takes place in an activity system composed of object, actions and operations, is the constitution of context. Context is constituted through the enactment of an activity involving person (subject) and artefacts. Context is therefore the activity system and the activity system is connected to other activity systems. It is both internal to people involving specific objects and goals, as well as external to people, involving artefacts, other people and specific settings. In activity theory, both external and internal are fused, unified. Context cannot be reduced to an enumeration of people and artefacts.  

    In activity theory, context is not persistent and fixed information. Continuous construction is going on between the components of an activity system. Humans not only use tools, they also continuously renew and develop them either consciously or unconsciously. They not only use rules, but also transform them. In the design, it is important to understand how things get done in a context and why. This is because different contexts impose different practices.  

    To analyse context, we need to know the beliefs, assumptions, models and methods commonly held by the group members, how individuals refer to their experiences in other groups, what tools they found helpful in completing their problem etc.  

    In addition, there are also external or community-driven contexts. These include issues such as:  

    *   What type of limitations placed on the activity by the outside agencies?
    *   How are tasks organized working toward the object?
    *   What is the structure of the social interaction surrounding this activity?
    *   What activities are considered to be critical?
    *   What are the activities, goals and sub goals to be supported by the application?
    *   Who are users involved?
    *   What is the purpose of the activity and actions for the users?
    *   What is the user trying to achieve?
    *   How do the user's activities fit into the objectives of purchasing?
    *   What are the expectations about the outcomes? ([Jonassen & Rohrer-Murphy 1999](#Jonassen99))
2.  **_Analyse the activity system and produce the activity system._** This step involves defining, in depth, the components of the given activity, namely, the subject, object, community, rules and division of labour. This study began by interpreting the various components of the activity triangle (Figure 4) in terms of the situation being examined. The activity system produced for our e-commerce application is shown in Figure 3\. The subjects in the Web system consist of manager, stock controller, customer, Web developers, users etc. The object in this example is an undefined purchase order. The outcome is the purchased product.  

    <div align="center">![Activity system for e-commerce](p340fig4.gif)</div>

    <div align="center">  
    **Figure 4: Activity system for e-commerce**</div>

3.  **_Analyse the activity structure_**. This step involves decomposing each activity into actions and operations. An important key process in analysis is to analyse the activity structure (all of the activities that engage the subject) that defines the purpose of the activity system. The hierarchy of activity, actions and operations describe the activity structure.  

    This step involves defining the activity using questions such as:  

    *   How is work being done in practice?
    *   How has the work (actions and operations) transformed over time?
    *   What historical phases have there been on the work activity?
    *   What are the goal motives of the activity and how are they related to other concurrent goals?
    *   For each activity, what actions can be performed and by whom?
    *   For each action, observe and analyse the operations that the subjects perform.  
    Understanding the use of technology should start with identification of the goals of target actions that are relatively explicit and then extend the scope of analysis both up (to higher level actions and activities) and down (to lower level actions and operations). We consider:  

    *   Who are the people who will use the application?
    *   Goals of target actions.
    *   People involved in the design process.
    *   What are the basic limitations of the current technology?
    *   Are there conflicts between different goals of the users?
    *   Criteria for the success or failure of achieving goals.  
    To capture the requirements of the e-commerce application we must analyse the three levels that activities have: activity, action and operation. To analyse an activity and the actions that compose it we use a hierarchical notation which is traditionally used in the field of task analysis ([Shepherd 2001](#Shepherd01)).

### Analysis of activity and actions

The hierarchical task analysis ([Shepherd 2001](#Shepherd01)) technique is typically used to represent the actions that users perform during an activity. In hierarchical task analysis, the tasks are gradually broken down into subtasks and eventually into actions that will define how the user actually performs the step ([Bolchini and Mylopoulos 2003](#Bolchini03)). To do this, two main types of refinements are used: the structural and the temporal refinements. The structural refinement decomposes a complex task into a set of independent simpler subtasks. The temporal refinement, moreover, provides constraints for ordering subtasks according to the parent task logic. The main advantage of this mode of analysis is that it provides analysts with models for task execution, enabling them to envisage the goals, tasks, subtasks, operations and plans essential to users' activities.

However, although hierarchical task analysis is useful for decomposing complex tasks, it has a narrow view of the task. The underlying theory views tasks in a more abstract sense, as a set of interlinked goals, resources and constraints. The focus is on the system and its properties ([Shepherd 2001](#Shepherd01)). Although it is recognized that the system (or the task) exists in a wider context, which may influence its behavior, little attempt is made to model this context explicitly. Another criticism of task analysis is that although the responsibility of the operator (user) to plan the use of available resources to attain a given goal is recognized, it treats the operator's cognitive processes as a black box: "how behavior is actually organized is a question for cognitive psychology" ([Shepherd 2001: 16](#Shepherd01)). It is crucial to understand the structure of human cognition in order to appropriately support cognitively intensive tasks. Cognition is intimately connected to socio-cultural processes ([Hollan _et al._ 2000](#Hollan00), but hierarchical task analysis provides no systematic way of dealing with the rich social and physical context in which activities are embedded. Hierarchical task analysis also fails to support the components needed to analyse system flows and dynamics. These limitations necessitate the use of additional theoretical structures to develop a more complete understanding of human activity.

To overcome the limitation, we have developed a task model based on activity theory. The purpose of a task model is to create a hierarchical analysis of the task structure or model the mental states and operations of the principle actors. It also describes the interactions between the people and their tools and resources. To analyse how people externalise their work, the task model should describe:

*   the main actors and their activity systems;
*   how the actors employ tools and resources to mediate their interaction and to externalise cognition;
*   methods and techniques that the actors employ;
*   the contexts in which work occurs; and
*   the actors' conception of their work, including sources of difficulty and breakdown in activity and their attitudes towards the Web application.

In this context, although we use a graphical notation based on those used in hierarchical task analysis we re-orient this kind of technique to support the ideas proposed in activity theory. We use the hierarchical decomposition to create a taxonomy which describes the actions that must be performed to achieve an activity. The root of the task taxonomy is considered to be the activity under analysis and the lower levels of the taxonomy are considered to be the different actions that must be performed to achieve the activity. In this way, an activity is decomposed into actions and an action can be decomposed into simpler actions.

The structural refinement (represented by solid lines in Figure 5) is used to decompose an action into a set of individual simpler actions. The temporal refinement (represented by dashed lines in Figure 5) is used to decompose an action into a set of simpler actions that must be performed in a cooperative way. The cooperation is represented by temporal constrains among actions. The temporal constraints used in task analysis techniques such as ([Paternò 1997](#Paterno97)) are also valid for activity analysis. For reasons of brevity, we present only the constraints used in the case study of this paper:

*   A1 >> A2, Enabling: the action A2 must be performed after the action A1 is performed.
*   A1 []>> A2, Enabling with information passing: the action A2 must be performed after the action A1 is performed. In addition, A1 provides a value for A2\.
*   A1 |> A2, Suspend-Resume: The action A1 can be interrupted by the action A2\. When A2 is performed, A1 can be resumed.
*   A1*, iteration: the action can be performed several times.

To hierarchically represent an activity we make customers describe how this activity must be performed. Considering the activity of purchasing products, let us suppose that customers provide us with the following description:

> To purchase products a user must be able to collect products by adding them to the shopping cart. During the process of adding products users must also be able to consult the state of their shopping cart at any time. Once users have finished adding products to the shopping cart, they must formalize the purchase by going through the checkout. To do this, users must first identify themselves as registered clients and then send a purchase order.

From this description we can identify which actions shoppers perform consciously. These actions constitute the hierarchical description. In a next step, we analyse this hierarchical description to identify those operations that users perform for each action without consciousness of them. (This analysis is presented in next section.)

<div align="center">![Hierarchical decomposition of an activity into actions](p340fig5.jpg)</div>

<div align="center">  
**Figure 5: Hierarchical decomposition of an activity into actions**</div>

We briefly describe the taxonomy in Figure 5:

*   The activity we are analysing is the purchase of products. To achieve this activity two actions must be performed Collect Products and Check-out. These actions are two cooperative actions. The temporal constraint defined between both is _enabling with information passing_. First the products should be collected into the shopping cart and then the check-out must be done. The information that needs to be exchanged is the collected products.
*   Collect Products is decomposed into two simpler cooperative actions: Add Product to Shopping Cart (which can be repeated) and Inspect Shopping Cart. The temporal constraint defined between the two actions is suspend-resume, which indicates that Add Product to Shopping Cart can be interrupted at any point by Inspect Shopping Cart. It will be reactivated from the state reached before the interruption once the action Inspect Shopping Cart is performed.
*   The action Add Product to Shopping Cart is decomposed into three individual actions: Add CD, Add Software and Add Book.
*   The action Check-out is decomposed into two simpler cooperative actions: Login and Send Purchase Order. The temporal constraint defined between the two actions is enabling, which indicates order users must identify themselves before sending a purchase order.

Note that temporal constraints are inherited. For instance, in Figure 5, the action Add Book can be suspended by the action Inspect Shopping Cart because the action Add Product to Shopping Cart (parent action of Add Book) has defined this constraint.

Finally, we associate to each action a template that allows us to characterize it in the context of the whole activity. These templates are made up of the following fields (see Figure 6):

*   _Goals_: objectives that must be reached after the action performance.
*   _Users_: The list of kinds of users that can achieve the action.
*   _Additional Information_: information that allow us to understand better the context in which each action must be performed. This information can be related to frequency, performance, security, availability, etc.

<div align="center">![Description of the action Add CD](p340fig6.gif)</div>

<div align="center">  
**Figure 6: Description of the action Add CD**</div>

Figure 6 shows the description of the action _Add CD,_ detected in the running example. According to this description, the goal of the action is for the subjects to add a CD to the shopping cart; the action can be performed by visitors and customers. As an estimate, the action is going to be completed 100 times an hour. No additional constraint is defined.

### Analysis of operations

Once the taxonomy is built, we must analyse the operations that define the actions. We need to analyse only the actions represented by the leave nodes of the taxonomy. Actions represented by intermediate nodes are defined throughout their children actions.

In order to use this analysis for correctly capturing Web application requirements we must consider not only structural and behavioural aspects of a Web application but also navigational ones. To do this, we propose two kinds of operations:

*   **System operations**: These operations are completely performed by the system. They can be: (1) _functional operations_ which change the system state or (2) _search operations_ which only query the system state.
*   **Interaction operations**: These operations represent an interaction between the system and the user. There are two kinds:  

    *   _Information exchange_: which represents an exchange of information between the system and the user. It is a bidirectional interaction operation, meaning that the user can introduce information to the system and the system can provide the user with information.
    *   _Message sending_: which is unidirectional, meaning that only the user can send messages to the system. These messages can be an activation of a system operation (the user indicates the system that performs a specific operation) or an information selection (the user select an specific information in order to obtain a more detailed description about it).

In order to analyse the operations that must be performed to carry out an action we propose the use of Unified Modelling Language activity diagrams ([Object Management Group 2007](#UML07)). This technique also allows us to indicate the sequence in which the operations must be performed.The operations are described by means of activity diagrams in the following way (see Figure 7):

*   System operations are represented by nodes depicted with dashed lines. To represent the type of the system operation these nodes are stereotyped with the keyword _Function_ or _Search_ .
*   Interaction operations are represented as follows:
    *   If it is an information exchange, the operation is represented by nodes depicted with solid lines. These nodes are stereotyped with the keyword _Output_ (if the system provides the user with information) or the keyword _Input_ (if the user introduces information into the system). Furthermore, we indicate in both cases the entity (i.e., any object of the real world that belongs to the system domain (e.g., client, product, invoice, etc) to which the information is related. In the _Output_ case, we also indicate cardinality, i.e., the number of entity instances the system provides. (An instance is the set of data related to each element of this entity (e.g., Name: Joseph, Surname: Elmer, Telephone Number: 9658789). This cardinality can be a specific number of entities or a list defined by an undefined number of entities (indicated by an asterisk)
    *   If it is a message sending, the operation is implicitly represented by the arcs whose source is an interaction operation. In these cases, the user activates a system operation (if the arc target is a system operation) or the user selects information (if the arc target is an information exchange).

Further representation aspects of this technique are (see Figure 7):

*   If the source of an arc is a system operation it just represents a node sequence.
*   The information that the user introduces into the system is used to perform a system operation. Thus, the interaction operation that represents the introduction of this information (a solid node stereotyped with the keyword input) depends on the system operation that will use the information. In order to graphically represent this dependency, both elements (interaction operation and system operation) are encapsulated in dashed squares.

<div align="center">![Operation analysis of the action Add CD](p340fig7.jpg)</div>

<div align="center">  
**Figure 7: Operation analysis of the action Add CD**</div>

Figure 7 shows the analysis of the operations that must be performed to carry out the action Add CD(the shaded numbers are not part of the notation). These operations must be performed as follows:

*   First, an interaction operation is performed (<span style="background: silver">1</span>). This operation indicates that the system provides the user with information (_Output_). This information is a list (cardinality*) of music categories (entity).  

*   From this list, the user can select a category (<span style="background: silver">2a</span> or <span style="background: silver">2b</span>).  

*   If the category has subcategories, the system provides again the user with a list of (sub) categories (<span style="background: silver">2b</span>) by means of the previous interaction operation (<span style="background: silver">1</span>).  

*   If the selected category does not have subcategories (<span style="background: silver">2a</span>) the system informs the user about the list of CDs that belong to the selected category by means of an interaction operation (<span style="background: silver">3</span>).  

*   If the interaction operation depicted as <span style="background: silver">3</span> is performed, the user can after that:  

    *   Select a CD (<span style="background: silver">4a</span>). Then, an interaction operation is performed. This operation (<span style="background: silver">5a</span>) represents that the system (_Output_) provides the user with a description (cardinality 1) of the selected CD (entity).  

    *   Activate a system operation (<span style="background: silver">4b</span>). This system operation searches (search stereotype) for the CDs (<span style="background: silver">5b1</span>). To do this, the user must introduce the search criterion that is an artist. This criterion is introduced by means of an interaction operation(_Input_) (<span style="background: silver">5b2</span>). In order to represent that this interaction operation exclusively depends on the system operation they are encapsulated in a dashed square.  
        If the search returns only one CD, the system provides the user with its detailed description (<span style="background: silver">6b1</span>). Otherwise, the system provides the user with a set of CDs (<span style="background: silver">6b2</span>).  

*   When the user has obtained a CD description (<span style="background: silver">5a</span>), s/he can activate a system operation (<span style="background: silver">6a</span>). It is a system operation which adds the selected CD to the shopping cart (<span style="background: silver">7a</span>). In this case, the state of the system is changed by the operation and it then becomes _Function_.

### Dynamic transformations between levels

As we have commented above (in the activity theory review section), activities may be automated and frozen when carried out repeatedly under similar circumstances, making conscious control unnecessary, thus transforming the acts into operational constituents of an action. Furthermore, this transformation may also work the other way, making a living, dynamic structure ([Baerentsen and Trettvik 2002](#Baerentsen02)). For instance, when people drive a lot they usually change gear without a conscious action and then this act is an operation. However, when people are learning to drive, the change of gear is a conscious action that they do in order to perform the activity of driving. This act is then an action. In the same way, and considering the running example, when less expert users of the Internet buy products they may need conscious control over operations such as the access to product descriptions or search of CDs (see Figure 7). In this case, these operations should be defined in the hierarchical description of activities.

In this context different descriptions can be obtained for a same application depending on the expertise of users in performing activities (see figure 8). An act that may be an action for less expert users becomes an operation for more expert users. The technique that we propose in this work facilitates the management of this type of description since both actions and operations are defined in different diagrams. If the subject needs consciously to control a specific act we represent it as an action in the hierarchy. If the subject does not have consciousness of this act we represent it as an operation of an action. For instance, Figure 8 shows two different representations of the activity analysis for the running example. The representation at the left side of the figure corresponds to the description provided by a less expert user. In this case, users explicitly represent as actions the acts of selecting a music category, selecting a CD and adding it to the shopping cart. The representation at the right side of the figure corresponds to the description provided by a more expert user. In this case, the previously introduced acts are performed without consciousness by users when they add a CD to the shopping cart. In this case, these acts are represented as operations of the action 'Add CD'.

<div align="center">[![Little_figure_8](p340fig8a.gif)](javascript: bigfigure())</div>

<div align="center">  
**Figure 8\. Dynamic transformations between levels** [Click for full-sized figure]</div>

Using the structures proposed above to represent activities, actions and operations are also a valuable mechanism that allows us to extract information related to navigation from requirements. Next, we analyse this aspect.

### Extracting navigational semantics from activity descriptions

The analysis of the activities that users must perform by interacting with a Web application can be used to derive which navigational structure should present this Web application. This navigational structure must be that which properly support users in the performance of the activities.

In this context, descriptions of Web applications performed by means of the technique presented above can be used to systematically derive the navigational structure of Web applications. The navigational structure of a Web application is defined from the mechanisms that allow user to navigate the information. These mechanisms are basically Web pages, links and access information facilities such as search engines. In order to derive these elements from activity descriptions we have defined a set of guidelines. We present here the following as a representative example:

*   **Guideline 1.** Exchange operations represent acts in which the system provides the user with information or vice versa. In a Web application these exchanges of information are performed throughout Web pages. Thus, we can derive a Web page for each information exchange operation that is defined in an action description.
*   **Guideline 2.** In the same way, if two information exchange operations are performed sequentially we can infer that the corresponding Web pages must be connected throughout a link. This link allows users to access one page from the other and thus provides support to the sequence of information exchanges defined in the action description.
*   **Guideline 3.** Search system operations are those performed by the system to query the system state. However, these operations are activated by users through a message. Thus, we can derive from these operations search engines that allow users to start a search for information.
*   **Guideline 4.** We can also derive navigational information from the temporal relationship defined between actions. For instance, if users can suspend the action _Collect Product_ in order to perform the action _Inspect Shopping Cart_ we can infer that Web pages derived from the operations of the first action must provide access to the Web pages provided by the operations of the second actions, and vice versa.

Figure 9 shows the navigational structure that is obtained when these guidelines are applied to the action Add CD seen in Figure 7:

*   Three Web pages are derived by applying the guideline (one page for each exchange operation): page A provides users with a list of Music Categories; page B provides users with a list of CDs; and page C provides users with a CD description.
*   Notice how these Web pages are connected by means of links according to the arcs defined between exchange operations (guideline 2). By selecting a music category in page A we access page B where the CDs that belong to the selected music category are shown; by selecting a CD in page B users access page C where a description of the selected CD is shown.
*   The search system operation has been developed into a search engine when guideline 3 is applied. This search engine can be accessed from page B.
*   Finally, notice how the shopping cart is available from the three pages. This link is derived from the temporal relationship _Suspend/Resume_ defined between the actions _Add Product to Shopping Cart_ and _Inspect Shopping Cart_. This temporal relationship indicates that users must be always able to perform the action _Inspect Shopping Cart_ while they are performing the action _Add Product to the Shopping Cart_ (or any of its sub-actions such as _Add CD_).

<div align="center">![Navigational Structure derived from Activity Analysis](p340fig9.gif)</div>

<div align="center">  
**Figure 9: Navigational structure derived from activity analysis**</div>

### Understanding the social and cultural aspects of users is important

In activity theory, all practice is seen as being re-formed and shaped by historical development. Consequently, it is important to understand how tools are used not only in a laboratory setting, but also over a period of time. In that period of time, development may occur to make the tool more useful and efficient than might occur in a single laboratory experiment.

History is the basis of classification. This means that the activity system and its components shall be understood historically. An activity is not a homogeneous entity. It is comprised of a variety of disparate elements, voices and viewpoints ([Engeström 1999](#Engestrom99)). The multiplicity can be understood in terms of historical layers. Activities are not static or rigid, they are constantly evolving. To understand a phenomenon means to know how it is developed into its existing form ([Kaptelinin 1996](#Kaptelinin96)). This applies to all the elements of an activity. The current relationship between subject and object includes a condensation of the historical development of that relationship ([Kuutti 1996](#Kuutti96)). This means we need to know where the users came from, as well as their beliefs and assumptions about the use of the application.

Relations between elements of an activity are not directed, but mediated. The principle of tool mediation plays a central role in activity theory. Tools shape the way human beings interact with reality. Shaping external activities results in shaping internal ones. Tools usually reflect the experience of other people who tried to solve similar problems. Tools can all be seen as artefacts for the activity: they are made by humans and they mediate the relations among human beings or between people and the material or product in different stages. Artefacts are there for us when we are introduced into a certain activity, but they are also a product of our activity and as such they are constantly changed through the activity.

In our case study, the online shopping made it more difficult, in one sense, for the subjects purchasing products, because the tools have changed from primarily purchasing products in a store or shop to online shopping. The tool-subject relation allowed us to see many affordances and constraints that must be taken into account in the analysis of the application.

The object is more than raw stimuli. It is a culturally-formed object with a history, however short or long. The object or focus of activity implies an overall direction of that activity, a (provisionally) shared purpose or **motive**. In our case study, the motive is, officially, to own the products. Of course the direction or motive of an activity system and its object may be understood differently or even contested, as participants bring many motives to a collective interaction and as conditions change. Clashes, resistance, conflicts and deep contradictions are constantly produced in activity systems.

However, initially, the object and motive for novice users (unexpectedly for the researchers) would be to use the Internet, not the information content. What was expected to be a mediational tool, the computer interface (Amazon.com), became instead the object and motive.

Users participate in multiple activity systems within their local and global contexts including purchasing products. Purchasing product is also an activity system that is embedded within its broader institutional, geographical and historical contexts. The users engaged in one activity system are also simultaneously influenced by other activity systems in which they participate. These influences are both horizontal, occurring across communities and also vertical as social actions that are also embedded within history, culture and inequitable power relations that are both influencing the meaning production and shaping human activities in important ways.

Activity theory makes the assumption that human identity (our beliefs, values and attitudes, our ways of thinking, talking and behaving) is located and formed through our everyday practice or interaction with our environment through social and cultural contact. We do not act and interact in isolation. Our practice is mediated and embedded in a wider social matrix comprising of cultural and historical artefacts and rules that govern and guide our actions and relationships. Human societies and human individuals are mutually constitutive. All of these should be taken into considerations when analysing requirements for Web applications.

## Benefits of activity theory for Web requirements

There are several benefits in using activity theory for Web requirements analysis. First, activity theory enables us to shift the focus from the interaction between isolated and stand-alone computers to a larger, more ecologically and valid interaction between human beings and their environments. It sensitises us to the dynamic and evolving nature of human-computer interaction and information system design and evaluation as well as highlighting the rich, multifaceted reality of strips of computer-mediated activity in situ ([Spasser 1999](#Spasser99)). activity theory also provides us with adequate period of time for understanding users' behaviour and their motivation.

Secondly, activity theory describes activities as hierarchical in nature and provides a model for decomposing activities into actions and operations. However, although current research has focused on these actions and operations, it has failed to address the real intention of the user in carrying out those actions and so has failed to understand the needs of the user at a higher level. Thirdly, activity theory insists that all activity is mediated by physical or mental tools. Tools affect the user and are themselves affected by the user. Fourthly, activity theory views activity not as a simple individual action, but as being culturally and historically located. Thus it is able to address the importance of organizational influence on the use of Web systems.

Activity theory also models people as agents rather than as collections of cognitive attributes. Activities are inherently context sensitive: the purpose of activity theory is to establish a minimal meaningful context for individual actions ([Kuutti 1996](#Kuutti96)). The activity is the context, defined as a form of doing directed to an object. Activities do not exist in isolation, they are under continuous development. Thus their history accumulates and serves to inform their evolution. This is possible because of the presence of artefacts. Artefacts carry culture in the form of historical residue, delivering the lessons of the past to the future, mediating between different elements of an activity and enabling the coordination of complex actions.

Another important aspect of requirements analysis is that of conflicts. Because of the interests and needs of different stakeholders, conflicts are unavoidable. It is important to identify conflicts during requirements analysis, as this helps designers to reflect on possible design strategies accommodating all different requirements, thus fulfilling the stakeholders' objectives and supporting the needs of the users.

Activities in activity theory are not static or given, but are dynamic. They are changing and developing. This development takes place at all levels: new operations are formed from previous actions as a participant's skills increase. Correspondingly, at the action level, the scope of new actions is enlarging. Totally new actions are also enacted, experimented and adapted as responses to new situations or possibilities encountered in the process of transforming the object. At the activity level, the object and motive are also reflected, questioned and perhaps adapted, reacting to larger changes and other activities ([Kuutti 1996](#Kuutti96)).

Because activities are not static but more like nodes crossing hierarchies and networks, they are influenced by other activities and other changes in the environment. External influences change some elements of activities causing imbalances between them ([Kuutti 1996](#Kuutti96)). Contradictions are the terms given to misfits within elements, between elements and between different activities or different developmental phases of the same activity. They manifest themselves as problems, ruptures, breakdowns, clashes etc.

According to Engeström ([1987](#Engestrom87)), any activity system has four levels of contradictions that must be attended to in analysis of a working situation. Level 1 is the primary contradiction. It is the contradiction found within a single node of an activity. This contradiction emerges from tension between use value and exchange value. It permeates every corner of the triangle and is the basic source of instability and development ([Engeström 1987](#Engestrom87)). Primary contradiction can be understood in terms of breakdowns between actions or sets of actions that realise the activity. These actions are poly-motivated. This means that the same action can be executed by different people for different reasons or by the same person as part of two separate activities. This poly-motivation may be at the root of subsequent contradictions.

Secondary contradictions are those that occur between the constituent nodes. For example, between the skills of the subject and the tool s/he is using, or between rules and tools. Tertiary contradictions arise between an existing activity and what is described as a more advanced form of that activity. This may be found when an activity is remodelled to take account of new motives or ways of working. Quaternary contradictions are contradictions between the central activity and the neighbouring activities, (e.g., instrument producing, subject-producing and rule-producing activities).

Activity is bound up with motive and there is no activity without a motive. Just as the concept of motive is related to the concept of activity, the concept of purpose is related to the concept of action ([Leont'ev 1978](#Leont'ev78)). Human activity does not exist except in the form of action or chains of actions. Action has an operational aspect (how, by what means this can be achieved), which is determined not by the goal in itself, but by the objective-object conditions of its achievement ([Wilson 2006](#Wilson06)).

Leont'ev's distinction of activity, action and operation has important implications for analysing tasks in Web requirements engineering. He distinguishes between activity, actions and operations and relates these to motives, goals and the conditions under which the activity is performed. The relationship is expressed as shown in Figure 3 above ([Leont'ev 1978](#Leont'ev78)).

## Conclusions

In this paper, we have presented a requirements engineering approach for Web applications based on activity theory. The theoretical principles provided by activity theory are applied in the analysis of Web applications requirements which allow us to properly consider organizational requirement that capture the cultural, cognitive and social aspects that are related to the requirements engineering activity.

Furthermore, we have used a technique for representing activity analysis that is based on a hierarchical descriptions of actions plus operation descriptions based on Unified Modelling Language activity diagrams. This technique has been developed to take into account the navigational requirements of Web applications. In this context, we have defined a set of guidelines that allow us to derive the navigational structure of Web applications from activity analysis.

This paper can be also considered as a practical example of how activity theory is applied in requirements activities in the development of Web applications. In particular, we have shown how requirements of an e-commerce application are captured through activity analysis.

As it is only a case study, the generalization of the results from the context of this study is limited. However, the strong socio-cultural themes that emerged provide a framework for assisting developers to analyse requirements that take into considerations the social and cultural aspects of the users.

From an activity system perspective, development of the requirements of a Web based application involves understanding the cultural and historic factors that have resulted in the present situation and clarifying the current disturbances in the current form of the system - aspects that are, for example, poorly aligned, inadequate or in opposition and then working to resolve them.

Although activity theory offers benefits for designing analysing Web requirements, it also has limitations. The key limitation of this approach is that the researcher must have a complete understanding of the activity system under observation, including the dynamic interplay of all the units of the activity system and such understanding takes time to acquire. The associated strength, of course, is that once the understanding is attained, it serves as a strong bedrock for the investigation. A second limitation is the difficulty faced by researchers in unravelling activity systems and, finally, there is the difficulty of distinguishing between the levels of activity, actions and operations.

It is the authors' belief that the benefits outweigh these limitations. Using the activity system as its unit of analysis, activity theory avoids simple causal explanation of Web requirements design by describing it as an ensemble of multiple, systematically interacting elements, including social rules, mediating artefacts and division of labour. The process of context and the dynamic transformation of objects into artefacts can be taken into account. This approach also takes into consideration the perspectives of different actors of an activity system. However, further work is still needed for it to be used as a robust design method. To use activity theory effectively for Web-based requirements analysis, it is important that research time be long enough to understand the objects of activity, the changes of those objects over time and their relations to objects in other settings. There should also be commitment to understanding things from the users' viewpoint. This means that there should be a phased approach to the design and evaluation of technology use.

We are continuing to evaluate our approach and aim to develop a framework that will guide developers to analyse Web applications that take into consideration the social and cultural aspects of the users.

## References

*   <a name="Al-Rawas96" id="Al-Rawas96"></a>Al-Rawas, A. & Easterbrook, S. (1996). Communication problems in requirements engineering: a field study. In _Proceedings of the First Westminster Conference on Professional Awareness in Software Engineering, Royal Society, London, 1-2 February 1996._ (pp. 47-60). London: University of Westminster.
*   <a name="Avison90" id="Avison90"></a>Avison,D & Wood-Harper, T. (1990). _Multiview - an exploration in information systems development_. Oxford: Blackwell Scientific Publishers.
*   <a name="Baerentsen02" id="Baerentsen02"></a>Baerentsen, K.B. & Trettvik, J. (2002). An activity theory approach to affordance. _Proceedings of the second Nordic conference on Human-computer interaction table of contents Aarhus, Denmark._ (pp. 51-60). New York, NY: ACM Press.
*   <a name="Bardram98" id="Bardram98"></a>Bardram, J. (1998). [Designing for the dynamics of cooperative work activities.](http://www.webcitation.org/5XiPkhcoo) In, _Proceedings of the 1998 ACM conference on Computer supported cooperative work, Seattle, Washington, USA, November 14-18, 1998._ (pp. 89-98). New York, NY: ACM Press. Retrieved 10 May, 2008 from http://www.daimi.au.dk/PB/536/PB-536.pdf (Archived by WebCite® at http://www.webcitation.org/5XiPkhcoo)
*   <a name="Bodker96" id="Bodker96"></a>Bødker, S. (1996). Applying activity theory to video analysis: how to make sense of video data in HCI. In Nardi, B. (Ed.). _Context and consciousness. Activity theory and human computer interaction_. (pp. 147-174). Cambridge, MA: MIT Press.
*   <a name="Bolchini03" id="Bolchini03"></a>Bolchini, D. & Mylopoulos, J. (2003). From task-oriented to goal-oriented Web requirements analysis. In, _Fourth International Conference on Web Information Systems Engineering Workshops (WISEW'03)_. (p. 166). Washington, DC: IEEE Computer Society.
*   <a name="Burdman99" id="Burdman99"></a>Burdman, J. (1999). _Collaborative Web development_. Reading, MA: Addison-Wesley.
*   <a name="Conklin97" id="Conklin97"></a>Conklin, J. (1987). Hypertext: an introduction and survey. _IEEE Computer_, **20**(9), 17-41.
*   <a name="Constantine99" id="Constantine99"></a>Constantine, L.L & Lockwood L.A.D.(1999). _Software for use: a practical guide to the models and methods of usage-centered design_. Reading, MA: Addison Wesley.
*   <a name="Deshpande02" id="Deshpande02"></a>Deshpande, Y., Murugesan, S., Ginige, A., Hansen, S., Schwabe, D., Gaedke, M. & White, B. (2002). _Journal of Web Engineering_, **1**(1), 003-017\.
*   <a name="DeTroyer03" id="DeTroyer03"></a>De Troyer, O. and Casteleyn, S. (2003). [Modelling complex processes from Web applications using WSDM](http://www.webcitation.org/5XmX2PnGM). In Luis Olsina, Oscar Pastor, Gustavo Rossi & Daniel Schwabe, (Eds.) _Third International Workshop on Web Oriented Software Technologies, Oviedo, Spain, July 15, 2003._. (pp. 1-12). Retrieved 13 May, 2008 from http://www.dsic.upv.es/~west/iwwost03/articles/DeTroyer%20IWWOST%202003.PDF (Archived by WebCite® at http://www.webcitation.org/5XmX2PnGM)
*   <a name="Engestrom87" id="Engestrom87"></a>Engeström, Y. (1987). _Learning by expanding: an activity-theoretical approach to developmental research_. Helsinki: Orienta-Konsultit.
*   <a name="Engestrom99" id="Engestrom99"></a>Engeström, Y. (1999). Expansive visibilization of work: an activity-theoretical perspective. _Computer Supported Cooperative Work (CSCW)_, **8**(1-2), 63-93.
*   <a name="Engestrom01" id="Engestrom01"></a>Engeström, Y. (2001). Expansive learning at work: towards an activity theoretical reconceptualization. _Journal of Education and Work_, **14**(1), 133-156.
*   <a name="England99" id="England99"></a>England, E. & Finney, A. (1999). _Managing multimedia: project management for interactive media_ 2nd ed. Reading, MA: Addison-Wesley.
*   <a name="Escalona04" id="Escalona04"></a>Escalona, M.J. & Koch, N. (2004). Requirements engineering for Web applications: a comparative study. _Journal on Web Engineering_, **2**(3), 193-212\.
*   <a name="Goguen93" id="Goguen93"></a>Goguen, J.A. & Linde, C. (1993). Techniques for requirements elicitation. _Proceedings of the First IEEE International Symposium on Requirements Engineering (RE 1993), San Diego, California, USA, January 1993_. (pp. 152-164). Washington, DC: IEEE Computer Society.
*   <a name="Goguen94" id="Goguen94"></a>Goguen, J. & Jirotka, M. (1994). _Requirements engineering: social and technical issues_. London: Academic Press.
*   <a name="Gomez00" id="Gomez00"></a>Gómez, J., Cachero, C. & Pastor, O. (2000). [Extending an object-oriented conceptual modelling approach to Web application design](http://www.webcitation.org/5XmYNvI9Z). In Benkt Wangler and Lars Bergman, (Eds.). _Proceedings of the 12th International Conference on Advanced Information Systems Engineering, Stockholm, Sweden, 5-9 June, 2000_. (pp. 79-93). Berlin: Springer. Retrieved 13 May, 2008 from http://gplsi.dlsi.ua.es/iwad/ooh_project/papers/ caise00.pdf (Archived by WebCite® at http://www.webcitation.org/5XmYNvI9Z)
*   <a name="Grechenig93" id="Grechenig93"></a>Grechenig, T. & Tscheligi, M. (Eds.). (1993). _Proceedings of the Vienna Conference on Human Computer Interaction_ London: Springer-Verlag
*   <a name="Harmelen01" id="Harmelen01"></a>Harmelen V.M. (2001). _Object modeling and user interface design: designing interactive systems_. Reading, MA: Addison Wesley.
*   <a name="Hofman00" id="Hofman00"></a>Hofman, H.F. (2000). _Requirements engineering: a situated discovery process_. Wiesbaden, Germany: Gabler.
*   <a name="Hollan00" id="Hollan00"></a>Hollan, J., Hutchins, E. & Kirsh, D. (2000). Distributed cognition: toward a new foundation for human-computer interaction research. _ACM Transactions on Computer-Human Interaction_, **7**(2), 174-196\.
*   <a name="Jaaksi98" id="Jaaksi98"></a>Jaaksi, A. (1998). Our cases with use cases. _Journal of Object-Oriented Programming_, **10**(9), 58-65\.
*   <a name="Jonassen99" id="Jonassen99"></a>Jonassen, D.H. & Rohrer-Murphy, L. (1999). Activity theory as a framework for designing constructivist learning environments. _Educational Technology Research and Development_, **47**(1), 62-79.
*   <a name="Kaenampornpan04" id="Kaenampornpan04"></a>Kaenampornpan, M. & O'Neil, E. (2004). Modality context: an activity theory approach. In Panos Markopoulos, Berry Eggen, Emile Aarts and James L. Crowley, (Eds.). _Ambient Intelligence: Second European Symposium (EUSAI 2004), Eindhoven, The Netherlands_. (pp. 367-374). Berlin: Springer
*   <a name="Kaptelinin96" id="Kaptelinin96"></a>Kaptelinin, V. (1996). Activity theory: implications for human-computer interaction. In B. Nardi (ed.), _Context and consciousness: activity theory and human-computer interaction_. (pp. 45-67). Cambridge, MA: MIT press.
*   <a name="Kaptelinin99" id="Kaptelinin99"></a>Kaptelinin, V., Nardi, B.A. & Macaulay, C. (1999). The activity checklist: a tool for representing the space of context. _Interactions Magazine_, **6**(4), 27-39\.
*   <a name="Kaptelinin00" id="Kaptelinin00"></a>Kaptelinin, V. (2000). _The didactics of the Web: understanding activity transformations in business and administration._ Paper presented at the Workshop on Distributed Cognition and Distributed Knowledge: Key issues in Design for e-commerce and E-government, Sharding, Australia, June 14-16, 2000.
*   <a name="Koch00" id="Koch00"></a>Koch, N. (2000). _Software engineering for adaptive hypermedia applications_. Unpublished doctoral dissertation, Ludwig-Maximilians-University, Munich, Germany.
*   <a name="Kuutti96" id="Kuutti96"></a>Kuutti, K. (1996). Activity theory as a potential framework for human-computer interaction research. In B. Nardi (Ed.), _Context and consciousness: activity theory and human-computer interaction_. (pp. 17-44). Cambridge, MA: MIT press.
*   <a name="Leite98" id="Leite98"></a>Leite, J.C., Rossi, G., Balaguer, F., Maiorana, V., Kaplan, G., Hadad, G. & Oliveros A. (1998). Enhancing a requirements baseline with scenarios. _Requirements Engineering_, **1**(4), 184-198.
*   <a name="Leont78" id="Leont78"></a>Leont'ev, A.N. (1978). _Activity, consciousness and personality_. Englewood Cliffs, NJ: Prentice-Hall.
*   <a name="Leontev81" id="Leontev81"></a>Leont'ev, A.N. (1981). _Problems of the development of mind_. Moscow: Progress.
*   <a name="Lowe03" id="Lowe03"></a>Lowe, D. (2003). Web system requirements: an overview. _International Journal on Requirements Engineering_, **8**(2), 102-113.
*   <a name="McDonald01" id="McDonald01"></a>McDonald, A. & Welland, R. (2001). [Web Engineering in Practice](http://www.webcitation.org/5Xmbb14NW). In _Proceedings of the 4th Workshop on Web Engineering (in conjunction with 10th International Conference on WWW), Hong Kong, May 21-30, 2001._. Retrieved 10 May, 2008 from http://www.dcs.gla.ac.uk/~andrew/webe2001.pdf (Archived by WebCite® at http://www.webcitation.org/5Xmbb14NW)
*   <a name="Mwanza01" id="Mwanza01"></a>Mwanza, D. (2001). [Where theory meets practice: a case for an activity theory based methodology to guide computer system design](http://www.webcitation.org/5Xmd3Mc0Y). In Michitaka Hirose (Ed), _Proceedings of the 13th International Conference on Human-Computer Interaction, Tokyo, Japan, July 9-13, 2001_. (pp. 342-349) Amsterdam: IOS Press. Retrieved 10 May, 2008 from http://tinyurl.com/49ezz9 (Archived by WebCite® at http://www.webcitation.org/5Xmd3Mc0Y)
*   <a name="Nunes00" id="Nunes00"></a>Nunes, N. & Cunha, J. (2000). Wisdom: a software engineering method for small software development companies. _IEEE Software_, **17**(5), 113-119\.
*   <a name="UML07" id="UML07"></a>Object Management Group, Inc. (2007). _[Unified Modelling Language 2.1.1—Infrastructure](http://www.webcitation.org/5Xmpccgsr)_. Needham, MA: Object Management Group, Inc. Retrieved 13 May, 2008 from http://www.omg.org/docs/formal/07-02-06.pdf (Archived by WebCite® at http://www.webcitation.org/5Xmpccgsr)
*   <a name="Overmyer00" id="Overmyer00"></a>Overmyer, S.P. (2000). What's different about requirements engineering for Web sites?. _International Journal on Requirements Engineering_, **5**(1), 62-65.
*   <a name="Paterno97" id="Paterno97"></a>Paternò, F., Mancini, C. & Meniconi, S. (1997). ConcurTaskTree: a diagrammatic notation for specifying task models. In G.W.M. Rauterberg, M. Menozzi & J. Wesson, (Eds.), _13th International Conference on Human-Computer Interaction, Sydney, Australia, 14-18 July 1997._ (pp. 362-369). Amsterdam: IOS Press
*   <a name="Probert99" id="Probert99"></a>Probert, S.K. (1999). Requirements engineering, soft system methodology and workforce empowerment. _International Journal on Requirements Engineering_, **4**(2), 85-91.
*   <a name="Robert98" id="Robert98"></a>Robert, D., Berry, D., Isensee, S. & Mullaly, J. (1998). _Designing for the user with OVID_. London: MacMillan.
*   <a name="Rosenberg99" id="Rosenberg99"></a>Rosenberg, D. and Scott, K.&nbsp; (1999). _Use case driven object modelling with UML_. Reading, MA: Addison Wesley.
*   <a name="Schwabe96" id="Schwabe96"></a>Schwabe, D., Rossi, G. & Barbosa, S. (1996). Systematic hypermedia design with OOHDM. In _Proceedings of the ACM Conference on Hypertext, Washington, USA, March 1996_. (pp 116 - 128). New York, NY: ACM Press.
*   <a name="Shepherd01" id="Shepherd01"></a>Shepherd, A. (2001). _Hierarchical task analysis_. New York, NY: Taylor & Francis.
*   <a name="Spasser99" id="Spasser99"></a>Spasser, M.A. (1999). Informing information science: the case for activity theory. _Journal of the American Society for Information Science_, **50**(12), 1136-1138.
*   <a name="Uden01" id="Uden01"></a>Uden, L. & Willis, N. (2001). Designing user interfaces using activity theory. In _Proceedings of the 34th Hawaii International Conference on System Sciences, Wailea, Maui, Hawaii, USA._ (pp. 5031-5042). Washington, DC: IEEE Computer Society.
*   <a name="Uden07" id="Uden07"></a>Uden, L. (2007). Context design for mobile learning using activity theory. _International Journal of Mobile Learning and organization_, **1**(1), 81-102\.
*   <a name="Vanderdonckt99" id="Vanderdonckt99"></a>Vanderdonckt, J. & Berquin, P. (1999). Towards a very large model-based approach for UI development. In _Proceedings of the First International Workshop on User Interfaces to Data Intensive Systems, Edinburg, 5-6 September 1999_. (pp. 76-85). Washington, DC: IEEE Computer Society.
*   <a name="Vygotsky78" id="Vygotsky78"></a>Vygotsky, L.S. (1978). _Mind and society_. Cambridge MA: Harvard University Press.
*   <a name="Wilson06" id="Wilson06"></a>Wilson, T.D. (2006). [A re-examination of information seeking behaviour in the context of activity theory](http://InformationR.net/ir/11-4/paper260.html). _Information Research_, **11**(4) paper 260\. Retrieved 10 May, 2008 from http://InformationR.net/ir/11-4/paper260.html

