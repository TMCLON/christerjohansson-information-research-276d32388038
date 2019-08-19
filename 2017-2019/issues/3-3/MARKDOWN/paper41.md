####  Vol. 3 No. 3, January 1998

# An Internet information system for GPs

#### M. P. Bradley & J. S. Briggs

Department of Information Science, University of Portsmouth, UK

#### Abstract

> A large organisation like the British National Health Service needs to use technology to improve its efficiency and efficacy. The Internet is a relatively new technology that may prove to be useful. One application where this might be useful is in providing up to date information about hospital consultants to general practitioners. This would aid them in referring patients to the most appropriate specialist. We describe a prototype GP information system using Internet technologies that shows that such an application is feasible. The system is implemented in the Java programming language, so making it easier for new versions of the software to be distributed.

## Introduction

The efficiency and efficacy of an organisation as big as the British National Health Service (NHS) rests heavily on the use of appropriate technologies by its staff, both clinical and non-clinical. Computer technology, in particular, can be used to do routine jobs that would otherwise require more manpower and, as we illustrate here, make information available more widely to the benefit of those who need to use it. Of particular interest to us is how the Internet, the so-called Information Super-highway that is now becoming prevalent in both the home and workplace, could be used to benefit doctors and their patients.

The NHS is based on a primary health care model. Patients requiring treatment first visit their General Practitioner, a clinician with a wide range of expertise. If the GP feels unable to treat the patient, he or she will refer the patient to a consultant specialising in the relevant area of medicine. The normal mechanism for doing this is for the GP to write a letter (called a referral letter) to the consultant. How does the GP choose the consultant?

Firstly, there may be several consultants for any given specialty at one hospital, or there may not be any at all. Frequently within a specialty, individual consultants will have particular interests or experience. For example, one orthopaedist might have particular interest in hands while another is interested in feet. It would be beneficial to both patient and consultant if an appropriate referral could be made.

Secondly, the funding structure of the NHS limits spending by limiting the supply of health care. Waiting lists build up for non-emergency treatments, particularly outpatient consultations with consultants. These waiting lists can vary greatly from consultant to consultant for the same treatment. While there is some debate over what a short waiting list indicates, this is information that the GP might wish to use in deciding which consultant to choose.

Our work started from the hypothesis that GPs _would_ like more accurate and more timely information about waiting lists when referring patients to consultants, and that Internet technology might be a suitable way of delivering that information. The latter is a realistic proposition since virtually all GPs have some sort of computer system in their surgery and, while only a few are at present connected to the Internet, the equipment and software necessary to do so is relatively cheap and easy to install. Our aim was to develop a prototype of a system to show the validity of the concept, after talking to GPs and hospitals to establish what was feasible and what was required.

## Information that GPs wanted from the system

A number of GPs located in the South of England were interviewed in the summer of 1996 to find what they would like to see in an information system that provided them with up-to-date information from hospitals ([Bradley, 1996](#brad)). The process was one of eliciting requirements for the system rather than a statistical study of referral patterns.

The GPs described the factors that affected their decision as to which consultant to refer a patient. The factors identified were:

*   locality to patient;
*   waiting time for treatment;
*   patient preference;
*   knowledge of the consultant;
*   the consultant’s special interests;
*   the performance of the consultant or unit; and
*   the cost of the treatment.

Each GP ranked the factors they had identified in order of importance. The differences were considerable. For example, one ranked performance indicators as being very important, another dismissed them as being too crude to merit consideration.

All of the GPs agreed that they would like more information that was more up to date than they presently receive. Information about waiting list times came at best monthly by post, and was out of date as soon as it was printed. Knowledge of consultants and their specialities was normally by personal contact or personal accumulation of experience by the GP. There was no catalogue of consultants’ particular interests so that patients could be referred to the appropriate person. Consultants sometimes publish "protocols" - documents describing the way that they like patients to be managed before they are referred to an outpatient clinic. One GP said that he would like an information system to provide him with these protocol documents so that he could manage patients in the way preferred by the particular consultant. Consultants might be more enthusiastic about writing the documents if they knew that they would be easily available to (and used by) their target audience

The GPs were enthusiastic about a system that could deliver up-to-date information about waiting lists, consultants’ interests and other information to them as they made their referral decisions.

## Hospitals’ willingness and ability to provide information

The IT managers of two hospital trusts on the south coast of England were interviewed later in the summer of 1996\. Both hospitals welcomed the concept of providing GPs with more information about the services they offer, particularly information about waiting list times and the special interests of consultants.

One IT manager described the proposed system as providing an additional window onto the hospital’s information. It has an open link to its proprietary hospital information system that it can use to create new applications, including an application such as this. The hospital already has most of the hardware and software that it would need for the application. The manager thought that it would not be too difficult to implement the hospital end of the system.

Between them, the hospitals identified a number of issues that would need to be addressed before the system could be fully implemented. Firstly, there are no standard measures for waiting list times. Each hospital measures the time a patient must wait for an appointment in a different way - the discrepancies normally arising from different ways of calculating the start of the wait. This could be when the GP writes the referral letter or when the patient is sent a letter telling him or her about their appointment.

The second problem arises from the definition of urgency. The seriousness of a patient’s condition will determine the time the patient must wait for an appointment. Consultants manage their diaries to accommodate this: they have different slots for different grades of urgency. Each consultant, however, will have different levels of urgency - "urgent" might mean "within 7 days" to one, "within 21 days" to another. GPs need some standard way of comparing like with like.

## Functionality of the GP application

We designed the GP application to query hospitals for information and display the information they return to the user. The prototype application is limited to outpatient appointment information, but could be extended to provide other forms of query. The user specifies the specialty - such as "general medicine" - and the urgency - such as "routine".

<div>![](p41f01.gif)</div>

<div>Figure 1 - The query interface</div>

When the query command is invoked, the application requests information from different hospitals and displays it appropriately to the user. The prototype application displays the information as a table, each hospital having a number of consultants and each consultant offering a number of clinics, etc.

As the user moves the mouse over the rows for a particular consultant, a box at the bottom of the screen gives a brief description of the consultant’s interests. (In Figure 2, Dr Virchov is shown to have a special interest in cystic fibrosis.) Hospitals, consultants and treatments can have World Wide Web (WWW) pages associated with them, either in Hypertext Mark-up Language (HTML) format or otherwise. The information returned by a hospital includes the Uniform Resource Locator (URL) for it if one is available. If the user clicks on any of these, the application launches a web browser showing the appropriate page.

The presentation of the information in the prototype application is basic. A more refined version might use tree views instead of a table, and allow the user to make comparisons between different treatments at different hospitals.

<div>![](p41f02.gif)</div>

<div>Figure 2 - Results of the query</div>

## Architecture of the system

### Overall architecture

The system is designed with a client-server architecture (Figure 3). Each user application (the client) makes its own network connections to hospital servers to request information about treatments. Each hospital may operate a web server to provide WWW documents to users on its network. The system integrates tightly with any such web pages that may be available.

<div><a name="_926513688"></a>![](p41f03.gif)</div>

<div><a name="_Ref389642981">Figure</a> 3 - Architecture of the system</div>

Communication takes place via the TCP/IP group of protocols. The aim of the design was to be as independent as possible of the particular type of computer the GP and hospital would be using, to cater for the wide range of software and hardware used in the NHS.

### Implementation

The prototype user application is a Java applet ([Arnold & Gosling, 1996](#arno)). A Java applet is a small application that can run inside a Java-enabled web browser such as **Netscape Navigator** or **Internet Explorer**. A special HTML tag instructs the browser to download and execute the application. Thus each time the user wishes to start the application, a new version of the software is downloaded. Problems of installing the latest version of applications on individual users’ workstations are all but eliminated.

Writing the application in Java brings other benefits apart from being able to run the application as an applet. Web browsers are able to run Java applets by implementing a Java virtual machine (as defined by Sun Microsystems)([Lindholm & Yellin, 1996](#lind)). Wherever the Java virtual machine is implemented, a Java application will run. Java applications are compiled to machine-independent bytecodes interpreted by the virtual machine (Figure 4). The Java virtual machine has been implemented and is available on many platforms including Windows, OS/2, many flavours of UNIX, AS400s and MVS. It is also possible to write compilers for languages other than Java that compile to Java bytecodes - one such compiler has been written for Ada.

<div><a name="_Ref389627471"></a>![](p41f04.gif)</div>

<div><a name="_Ref389643124">Figure</a> 4 - Java machine independence</div>

If a text based (rather than graphical) user interface were written ([Collins, 1995](#coll)), the system could run on any machine that had a Java virtual machine implementation. The application would be a program rather than an applet, however, so the bytecode files would need to be available on local disk storage rather than be dynamically downloaded via a web browser.

### Format of data

In our system, hospitals return information to the GP application in a format defined in Structured General Mark-up Language (SGML)([Goldfarb, 1995](#gold)). SGML is a platform-neutral notation for the specification of a data structure. The definition of a data structure is contained in a Document Type Definition. Data is broken down into entities. Entities can have child entities - in our case, hospitals have consultants, consultants have treatments and treatments have performance indicators.

Data in SGML format is entirely text based, making it particularly appropriate for an application that is seeking to avoid any reliance on particular platforms. The SGML definition for the hospitals’ data is relatively simple, so as to minimise the effort required for a hospital to offer information to GPs in this way.

## Issues not addressed

The GPs interviewed all thought that as well as getting extra information about treatments, they would like to be able to make a booking on-line. The IT managers of the hospitals were not unreceptive to this idea, but thought that the consultants working in the hospital might resist the change from a consultant-led to a GP-led booking process. An intermediate stage might be for the GP to be able to email the referral letter to the hospital, and for them to print it out and deal with it in the conventional way. The prototype system does not at present allow GPs to make online bookings.

This work does not consider the security of the system. If the system is limited to providing information about treatments, patient confidentiality is not compromised. Hospitals might, however, wish to restrict access to their information to authorised individuals. If this were the case, some kind of authentication of users would be necessary. If the system were expanded to any kind of booking functionality, patient details would need to be kept secure. It is likely that an application of this kind would run on the NHS’s private network and use encryption techniques, thereby reducing the risk of private individuals gaining access to confidential information.

It would be necessary to provide a web server from which the applet could be downloaded by web browsers running on users’ workstations. If desired, this web server could support many users: perhaps all of the GPs in a city. The same machine might also provide the service of specifying suitable hospitals for the applet to query.

## Conclusions

This work has shown that GPs want more information and that hospitals are broadly willing and able to provide it. We have shown how Internet technology could provide a cheap, manageable and timely means of delivering the information to the GP's surgery. That this provides a higher level of service for the patient is for others to judge, but we believe we have shown that the technology is there to make it possible.

## Acknowledgements

The work was carried out in collaboration with Integrated Media Systems, Southsea. We would like to record our appreciation of the help given by GPs and hospital trusts towards the success of this project. M P Bradley held an EPSRC studentship during the period of the work. He now works for The Object People.

## References

*   <a name="arno"></a>Arnold, K. & Gosling, J. _The Java programming language._ Reading, MA: Addison-Wesley, 1996.
*   <a name="brad"></a>Bradley, M.P. _GP Internet Booking System._ (MSc Dissertation) Portsmouth: University of Portsmouth, 1996.
*   <a name="coll"></a>Collins, D. _Designing object oriented user interfaces._ Benjamin-Cummins, 1995.
*   <a name="gold"></a>Goldfarb, C.F. _The SGML handbook._ Oxford: Oxford University Press, 1995.
*   <a name="lind"></a>Lindholm, T. & Yellin, F. _The Java virtual machine specification._ Reading, MA: Addison-Wesley, 1996.