#### Vol. 11 No. 3, April 2006


# No bad web pages:  reader empowerment and the Web

#### [Terrence A. Brooks](mailto:tabrooks@u.washington.edu)  
Information School, University of Washington  
Seattle, WA 98195 USA  

#### Abstract

> **_Background_**  User scripting heralds a paradigm shift towards web reader empowerment. Powerful web writers of the first decade of the Web needed to be cautioned about usability and accessibility issues. As power shifts to web readers, they become capable of customizing web pages to their own tastes and purposes. This paper describes the development of Greasemonkey extension of the Firefox browser.  
> **_Argument_**   User scripting is a product of the development of the open source browser, and individual developers who wish to change webpages. The Greasemonkey extension of the Firefox browser permits web readers to write JavaScripts that (1) Change the look and feel of Web pages, (2) Change the functionality of web page controls, and (3) Facilitates Web page "mashups", hybrid web presentations composed of content from two or more web pages. The only naturally occurring limit to web page modification may be difficult Web page source code. Tools that shield Web readers from the complexity of HTML are being introduced.  
> **_Conclusion_**  The paradigm shift to Web readers, armed with powerful and easy-to-use tools for customizing Web pages heralds a new era of the Web. It threatens the idea that a Web page has a single look and feel, and emphasizes the trend to design Web pages as mere input to the reading experience, subject to modification of presentation device as well as reader taste and purpose.




## Who controls Web text?

Commentaries on the creation of digital text suggest that there is an asymmetric power relationship between Web readers and writers. Generally, powerless readers must suffer with what they are given, while writers are urged to be sympathetic to readers' needs.

*   Poor documents are so commonplace that deciphering bad writing and bad visual design have become part of the coping skills needed to navigate in the so-called information age. But bad document design is not inevitable. (<span class="ref" onclick="showRef('schriver')">Schriver</span> 1997: xxiii)
*   It will take time and effort to identify the optimum forms of electronic text. Currently, designers lack the expertise and experiences that have evolved with paper text and the present work seeks to contribute to the increased research and development effort on this front. (<span class="ref" onclick="showRef('dillon')">Dillon</span> 1994: 2)
*   This year's list of top problems clearly proves the need to get back to Web design basics. There's much talk about new fancy 'Web 2.0' features on the Internet industry's mailing lists and Websites, as well as at conferences. But users do not care about technology and do not especially want new features. They just want quality improvements in the basics. (<span class="ref" onclick="showRef('nielsen10305')">Nielsen</span> October 3, 2005)

The impression that readers are powerless derives from a book culture where readers were unable to customize ink and paper to suit their individual tastes and purposes. Paper books and Web pages, however, are not technically analogous. Books are products of an industrial process of printing generally beyond the control of readers, while Web pages are digital presentations created by the reader's own Web browser. The moment of publication of a Web page is immediate, and the locus of publication is at hand. By seizing control of the browser running in their own computers, Web readers can modify Web pages. This heralds a paradigm shift of empowered readers who will customize Web pages according to their tastes and purposes.

Customization of Web presentation by user scripting was a product of the development of the open-source browser, which provided pioneering developers a chance to target certain Web pages for customization.


## The browser wars of the 1990s

Netscape Navigator, the first Web browser, appeared in 1994 and was an enormous success. With the rapid growth of the Web, Web browsers appeared to be strategic applications with the potential to direct Web traffic, place advertising and promote the use of proprietary software. Internet Explorer, Microsoft's browser, originally shipped as the Internet Jumpstart Kit in Microsoft Plus! For Windows 95\. (<span class="ref" onclick="showRef('ieHistory')">Internet Explorer history</span> June 30, 2003)

The browser wars during the late 1990s were a struggle between Internet Explorer and Netscape Navigator.

> The wars effectively ended in 1998 when it became clear that Netscape's declining market share trend was irreversible... Netscape responded by open sourcing its product, creating Mozilla... In 2004, Firefox 1.0 was released.    Wikipedia, _<span class="ref" onclick="showRef('wiki_browser')">Web browser</span>_

Open sourcing an application gives it to the Web community where volunteers may continue its development. Open sourcing also reflects the belief that perhaps some creative spirit outside the commercial mainstream may extend the application in new and unexpected directions.


## Writers dominate the top-down Web

Controlling the Web browser is valuable if the Web is a publishing or advertising channel that can reliably place content before potential consumers. In long-established publishing and advertising channels, such as magazines, radio and television, readers have little control over the information placed before them. For example, the reader of a magazine has no power to modify or block an advertisement that s/he might happen upon by turning a page. Web readers in the 1990s were in a similarly weak position, armed with only modest browser modifications such as changing font size, background color or resizing the browser window.

The pop-up controversy in the early 2000s illustrates the asymmetrical power relationship between writers and readers in the top-down Web (e.g. <span class="ref" onclick="showRef('onlineAds')">Online ads get in your face</span> June 13, 2001). With a decline in advertising revenue from banner advertisements, Web pages began to feature pop-ups and pop-unders to produce a higher click rate (Wikipedia, _"<span class="ref" onclick="showRef('wiki_popUp')">Pop-up ad</span>"_). Pop-ups are designed to react to reader events such as opening a window, closing a window, returning to an earlier Web page, and so on. Carried to an abusive extreme by some pornography Websites, Web readers could be trapped by a seemingly infinite series of pop-ups, effectively anchoring them to a Website despite their efforts to escape. The outcry against such reader abuse resulted in a number of add-ons to Web browsers that blocked pop-ups. In 2004 Microsoft added pop-up blocking to Internet Explorer.

The emergence of 'usability' as one of the signature issues of the top-down Web indicates that Web readers had little power to block content or modify the functionality of Web pages, but had to rely on caring Web writers:

*   _Usability_. A considerable literature counselled Web writers how to write Web pages useful to Web readers. Jakob Nielsen reflected on the meaning of usability: 'On the one hand, it's a quality assurance methodology that tells you what works and what doesn't work in the field of user experience. On the other hand, usability is a belief system that aims to ensure human mastery of the constructed environment'. (<span class="ref" onclick="showRef('nielsen2705')">Nielsen</span> June 27, 2005). This last comment could be interpreted as an admonition to Web writers to create Web pages that fostered the belief that _they_ -- the Web readers -- were masters of the Web content placed before them.
*   _Accessibility_: The World Wide Web Consortium sponsors a [Web Accessibility Initiative](http://www.w3.org/WAI/) to promote accessibility of the Web for readers regardless of disabilities such as color blindness, and so on.



## The architectural irony of the top-down Web

It is an irony that all Web pages, even the ones with repugnant content or coersive behaviour that readers would otherwise seek to avoid, are constructed on the Web readers' own machines. Common parlance suggests that a Web server sends 'Web pages' to a client browser as if these were inviolable containers of information that the reader's browser can only passively present. In reality, the Web server sends a variety of Web-page components such as hypertext markup files, image files, sound files, style sheet files, JavaScript files, and so on to the browser. The layout engine of the browser parses the hypertext markup, applies style sheets, and runs any scripts to create the artifact that readers recognize as a Web page.

> Basically, a layout engine takes content (such as HTML, XML, image files, applets, and so on) and formatting information (such as Cascading Style Sheets, hard-code HTML tags, etc.) and displays the formatted content on the screen. It 'paints' the browser's content area, which is the blank area inside the browser window's 'chrome'.  <span class="ref" onclick="showRef('mozilla')">FAQ, nglayout project/gecko layout engine</span>

The fundamental enabler of Web-reader empowerment is the local construction of Web pages. By seizing control of the Web-page construction process running inside their own machines, Web readers can redress the power inequity of the top-down Web.



## The development of an extensible browser

In 2004 Mozilla Firefox 1.0 was released. Firefox is an open-source Web browser designed to be extended by its development community.

> Extensions are small add-ons that add new functionality to Firefox. They can add anything from a toolbar button to a completely new feature. They allow the application to be customized to fit the personal needs of each user if they need additional features, while keeping Firefox small to download.   _<span class="ref" onclick="showRef('FF_extensions')">Firefox extensions</span>_

Eventually the personal needs of a member of the Firefox development community would include changing the look and feel of a specific Web site.

On July 19, 2004 Adrian Holovaty posted <span class="ref" onclick="showRef('holovaty_7192004')">Site-specific browser extension: All Music Guide</span>. His extension modified the look and feel of the [All Music Guide](http://www.allmusic.com/) Website in his Firefox browser. An annoying Flash widget was hidden and the links on the Web page were changed. He reflected on the ability to arbitrarily change the appearance and functionality of Websites:

> To my knowledge, using browser extensions to 'fix' Web sites, or add extra functionality, is unexplored territory. There's a huge potential here. Site-specific Firefox extensions are an elegant, one-click-install solution to the problem of, well, lousy Web interfaces—a problem Web users have had to shut up and deal with for as long as the Web has been around.  <span class="ref" onclick="showRef('holovaty_7192004')">Adrian Holovaty</span> July 19, 2004

Changeable presentation of content has been a continuing interest since the establishment of the Web. Lie and Bos (<span class="ref" onclick="showRef('lieBos')">1999</span>) highlight this ambition in their history of cascading style sheets. Korpela refers to 'presentation control by readers' as an ideal in his analysis of Web writing (<span class="ref" onclick="showRef('korpela')">Korpela</span> 1997). In 2001 Turner suggested 'active browsing' as a model for Web browsers (<span class="ref" onclick="showRef('turner2001')">Turner</span> 2001). Browsers under development, such as [Flock](http://www.flock.com/home/), describe "moving back to the original vision of Tim Berners-Lee, that the Web should be a two-way experience" (<span class="ref" onclick="showRef('macintyre')">MacIntyre</span> September 14, 2005) between readers and writers.


## Lowering the barrier of technical difficulty

Using a Firefox extension may be an elegant one-click-install solution for some people, but the average Web reader would find writing an extension for the Firefox browser a non-trivial task. [achfiend.com's](http://roachfiend.com/archives/2004/12/08/how-to-create-firefox-extensions/) tutorial, for example, involves creating an XPI file, modifying a RDF file and an XUL file, creating a globally unique identifier and writing a JavaScript extension. Technical challenges like these would daunt most Web readers and limit the popularity of modifying Web pages.

On December 6, 2004, Aaron Boodman announced the release of [Greasemonkey](http://greasemonkey.mozdev.org/), a Firefox extension that reduces the technical challenge to writing your own site-specific script in JavaScript.

> Greasemonkey is a Firefox extension which lets you to add bits of DHTML ('user scripts') to any Webpage to change its behaviour. In much the same way that user CSS lets you take control of a Webpage's style, user scripts let you easily control any aspect of a Webpage's design or interaction.  <span class="ref" onclick="showRef('aaron_1262004')">Aaron Boodman</span>

Lowering the barrier of user scripting to writing a JavaScript immediately empowers the large existing community of JavaScripters. [Tutorials](http://www.w3schools.com/dhtml/default.asp) already exist for Dynamic HyperText Markup Language (DHTML), there is an active literature (e.g., "[DHTML Utopia: Modern Web Design Using JavaScript & DOM](http://www.sitepoint.com/books/dhtml1/)") promoting its role in Web page design, and it has an established relationship with the World Wide Web Consortium's definition of the DOM (Document Object Model). The DOM models a Web page as a tree-like structure, which permits an addressing strategy that branches from root to leaf node in identifying each element of a Web page.

> Dynamic HTML (DHTML) is a term used by some vendors to describe the combination of HTML, style sheets and scripts that allows documents to be animated. The scripting interfaces provided in DHTML have a significant overlap with the DOM, particularly with the HTML module. Compatibility with DHTML was a motivating factor in the development of the DOM.    <span class="ref" onclick="showRef('w3c')">Document Object Model FAQ</span>

_Technical background note:_  

**Why is the link between DOM and DHTML important?**  

To change a Webpage one must be able to focus on specific elements of the HTML source code of the Webpage. A Web browser such as Firefox constructs a tree-like representation of the HTML source code called a Document Object Model (DOM). A Greasemonkey script is composed of JavaScript that manipulates elements of the DOM. Using JavaScript to manipulate the DOM to enhance Web page design already has a considerable literature. Aligning Greasemonkey with DHTML and DOM permits scripters to leverage this literature.



## Hacking Web pages made easy

Greasemonkey reduces, but does not eliminate the technical difficulty of modifying Web pages. Writing JavaScript still involves programming code. As illustrated by Mark Pilgrim's [Dive into Greasemonkey](http://diveintogreasemonkey.org/), the essential Greasemonkey online text, user scripting is enhanced by another powerful technology, [XPath](http://www.w3.org/TR/xpath), that is used to target elements of the DOM. Thus the scripter's toolbox includes a number of sophisticated tools:

*   **JavaScript**: One can write standard programming constructs such as _if-then_ decisions, _for_ loops, subroutines, and so on.
*   **DOM**: The Document Object Model builds a tree-like structure of all the HTML elements of the Web page.
*   **DHTML methods**: One can target HTML elements by their id attributes using a method such as _getElementById("address")_.
*   **XPath**: One can target HTML elements in terms of their position in the DOM structure. For example, the second table in the DOM has an XPath such as _//table[2]_.

Getting all these powerful tools working together properly may be tricky, but my own experience tells me that a big challenge of modifying Web pages is revealed when would-be scripters examine the HTML code written by their friends in the Web community. The Web is a democratic information experiment, which really means that practically anyone can hack together a Web page. As a result, the Web has many excellent examples of bricolage: inconsistent, sloppy messes created by amateurs. Web pages may include both a CSS file and some inline CSS code, have HTML element names in both upper and lower case, specify colours with both words and hex codes, lack id attributes and so on. Many Web pages are constructed by embedding tables within tables within tables, _ad infinitum_. In short, bewildering HTML code may turn out to be a naturally occurring upper limit on the wide application of do-it-yourself user scripting.



The revolution of user scripting awaits the development of WYSIWYG (What you see is you what you get) tools that shield the scripter from the messy details. A current example is [Platypus](http://platypus.mozdev.org/index.html), a Firefox extension created by Scott Turner that automates the creation of Greasemonkey scripts.

> Platypus is a Firefox extension which lets you modify a Web page from your browser—'What You See Is What You Get'—and then save those changes as a Greasemonkey script so that they'll be repeated the next time you visit the page.

The following snippet from the Platypus toolbar (version 0.5) indicates the sorts of tasks that can be accomplished with Platypus.

<div class="centerImage">![Platypus toolbar](paper257_files/platypus.JPG)</div>

The challenge of writing user scripts is also an opportunity for entrepreneurs such as [Custom Greasemonkey Userscripts](http://overstimulate.com/articles/2005/04/23/custom-greasemonkey-userscripts).



## An example Greasemonkey application

Perhaps more interesting than the technical details of user scripts is Greasemonkey's potential for placing usability issues in Web readers' hands and giving them a new tool for personal information management.

These issues can be illustrated by my script that changes the homepage of the [Information School](http://www.ischool.washington.edu/) at the University of Washington, my academic home. The top half of this Web page looked like this in July 2005:

<div class="centerImage">![Information School](paper257_files/iSchool.JPG)</div>

**Attention!** The following description of how and why I script against this Web page reflects my own travails of information management and is not my recommendation of how you might script against this Web page or any other Web page. This script reflects my _personal_ strategy for managing information resources.



My script helps me because

*   **Link excavation:** I use the geography consumed by the "iSchool News" centre column to place the links that would be otherwise buried under the pull-downs such as 'Programs' and 'Courses'. Instead of having to hunt up and down somebody else's term hierarchy, I have simplified my Web experience to 'point and click'... the stuff I need is right there in front of me when I land on this Web page. (See 'A' below).
*   **Link association:** I am also burdened with links that are associated with the Information School, but that are not integral parts of its Web page. My personal strategy for remembering these links is to place them in a significant location that is associated with their use, i.e., the iSchool homepage. Painful experience has taught me that I will lose links like these in the hierarchy of my Favorites or Bookmarks lists, or in the hierarchy of my e-mail folders. Once again, my personal information strategy succeeds when I transform my Web experience into 'point and click'... the links that I associate with the iSchool are right there in front of me when I land on this Web page. (See 'B' below)
*   **Quality-of-life issues:** I treat myself to a picture of lovely flowers. (See 'C' below)

My version of the Information School page looks like this:

<div class="centerImage">![My version of the Information School](paper257_files/myIschool.JPG)</div>



Moving between the official version of the Information School Web page and my version is simply done by toggling my Greasemonkey script on and off.

<input value="Show My Information School Script" onclick="showJavascript()" type="button">   <input value="Hide" onclick="hideJavascript()" type="button">

<div id="javascript" style="display: none;">  

[Download](http://www.ischool.washington.edu/tabrooks/GreaseMonkey/myScripts/ischoolFlowers.htm) the latest version of this script

<pre style="text-align: left;">// ==UserScript==
// @name             iNews
// @author           Terry Brooks
// @date             July 12, 2005 
// @namespace        http://faculty.washington.edu/tabrooks
// @include          http://www.ischool.washington.edu/
// @exclude          http://faculty.washington.edu/tabrooks/ 
// ==/UserScript==

(function()
{
// Put my own flower picture
var myFlowers, theirPic;

myFlowers = "http://www.ischool.washington.edu/tabrooks/
             GreaseMonkey/myScripts/whiteFlowers.jpg";
theirPic = document.evaluate(
	"//TABLE[2]//TD[3]/TABLE//IMG",
	document,
	null,
	XPathResult.UNORDERED_NODE_SNAPSHOT_TYPE,
	null);

theirPic.snapshotItem(0).src = myFlowers;

// Put my own news
var allNewstitles, thisNewstitle;

allNewstitles = document.evaluate(
	"//TD[@class='newsitem']",
	document,
	null,
	XPathResult.UNORDERED_NODE_SNAPSHOT_TYPE,
	null);	

for (var i = 0; i < allNewstitles.snapshotLength; i++) 
{
	thisNewstitle = allNewstitles.snapshotItem(i);

	if ( i == 0 ) 
	{
		thisNewstitle.style.backgroundColor = "white";
		thisNewstitle.style.paddingLeft = "10px";
		thisNewstitle.innerHTML = 
		"<a href='http://www.ischool.washington.edu/courses/descriptions.aspx' 
		style='color:black'>Course descriptions</a><br>" +
		"<a href='http://www.ischool.washington.edu/courses/schedules.aspx'
		style='color:black'>Course schedules</a><br>"  +
		"<a href='http://www.ischool.washington.edu/courses/courseWebs.aspx'
		style='color:black'>Course Web pages</a><br>"  +
		"<a href='http://help.ischool.washington.edu/faqs/' 
		style='color:black'>Technology FAQS</a><br>" +
		"<a href='http://msdn.e-academy.com/washington_is/' 
		style='color:black'>E-Academy software</a>" +
		"<br><br>" +
		"<a href='https://www.ischool.washington.edu/Webadmin/
		programs/informatics/viewapplications.aspx' 
		style='color:black'>Informatics Admission Database</a><br>" +
		"<a href='http://ecampus.ischool.washington.edu/evals-archive.asp'
		style='color:black'>Distance course evaluations</a>" ;
	} 
	else
	{
		thisNewstitle.style.display = "none";
	}

}
}) ();

</pre>

</div>



## Readers create the bottom-up Web

In the top-down Web, writers had to be reminded constantly of usability and accessibility issues, but these concerns fade in the bottom-up Web where the focus shifts to the many ways readers will transform Web pages to suit themselves. In the bottom-up Web, there are no 'bad' Web pages _per se_, merely Web pages you have yet to modify according to your tastes.

<span class="ref" onclick="showRef('dodds')">Leigh Dodds</span> (2005, April 4) has speculated on how users will change Web pages and suggests the following categories:

*   **Action**: As a Web page loads, it is transformed to address concerns of both usability and accessibility. For example, Web page elements are modified, resized, re-coloured, forms filled in, annotations added, and so on. My iSchool script is an example. Scripts can also customize Web applications. An example is the addition of persistent searches to Gmail. 'While one doesn't normally think of Web apps as having such advanced power user features, it recently occurred to me that it should be possible to add persistent searches to Gmail' (<span class="ref" onclick="showRef('mp')">Parparita</span> March 2005).
*   **Trigger**: A script reacts to a user event. For example, the nine-year old son of Prakash Kailasa, a Greasemonkey developer, was preparing for a spelling bee. Using a dictionary Web site, the young speller had to click a microphone icon to hear a word pronounced. Prakash wrote a Greasemonkey user script ("[Webster-say-word](http://kailasa.net/prakash/moz/greasemonkey/Webster-say-word.user.js)") that changed the functionality of the Web page so that the pronunciation was triggered by a simple mouse over.
*   **Mash-ups**: Two or more Web pages are _mashed_ together in new and unexpected ways. In the top-down Web, Web writers resisted submerging their work with other writers and sought to distinguish their Web pages from others. Web readers, on the other hand, often recognize that the information of one Web page can be enhanced by combining it with the information of another Web page. For example, both [Amazon.com](http://www.amazon.com/gp/browse.html/102-1490336-3097768?%5Fencoding=UTF8&node=3435361) and [Google Maps](http://www.google.com/apis/maps/) have been extensively mashed. Both provide an API (Application Programming Interface) to facilitate linkages with other Web pages. [Book Burro](http://overstimulate.com/articles/2005/04/24/greasemonkey-book-burro-find-cheap-books) mashes together prices from several online book sellers. 'Marrying maps to data for a new Web service' (<span class="ref" onclick="showRef('markoff')">Markoff</span> July 18, 2005) details how Google maps has been utilized by dozens of Web pages.



The Greasemonkey community script archive lists hundreds of scripts designed for [all Web pages](http://dunck.us/collab/GreaseMonkeyUserScriptsGeneric) and [specific Websites](http://dunck.us/collab/GreaseMonkeyUserScriptsSpecific). A number of Websites have been extensively scripted so far (this list probably reflects the interests of the members of the Greasemonkey development community):

*   [Bloglines](http://www.bloglines.com/),
*   [del.icio.us](http://del.icio.us/),
*   [eBay](http://www.ebay.com/),
*   [Flickr](http://www.flickr.com/),
*   [LiveJournal](http://www.livejournal.com/),
*   [Netflix](http://www.netflix.com/Default),
*   [New York Times](http://www.nytimes.com/), and
*   [Slashdot](http://slashdot.org/).

Google services such as Adwords, Alerts, Blogger, Gmail, History, Images, Maps, and Yahoo services such as Mail, Maps, Music, and Groups have all attracted a large number of scripts. There may be a corporate strategy at work here of embedding services as extensively as possible in other Web applications.

There is a notable sub-species of mash-ups that link Amazon.com with library digital catalogues. Scripts have been written that alert the Amazon shopper if an item already exists in the collection of the Seattle Public Library, Peninsula Library System (California) or Markham Public Library (Ontario, Canada).

As the number of public scripts increases, finding scripts and evaluating scripts become problems. Two current resources are [Last public marks](http://blogmarks.net/tag/greasemonkey+user.js) and [Userscripts](http://userscripts.org/)



## Other browsers introduce scripting

Web reader empowerment is spreading to other browsers. Each may have unique technical implementations, but there seems to be a general convergence towards the Greasemonkey model.

*   **Opera 8.0**  "[Take control with user JavaScript](http://www.opera.com/support/tutorials/userjs/)" introduces user scripting for the Opera browser. Opera supports Greasemonkey scripts and features, as well, a special _window.opera_ object. The Opera development community is beginning to compile user scripts and techniques: '[User JavaScript](http://people.opera.com/rijk/opera/userjs.html)' and '[Opera 8 beta 3 introduces User JavaScript](http://my.opera.com/hallvors/journal/44)'
*   **Safari**  [PithHelmet](http://culater.net/software/PithHelmet/PithHelmet.php) is an extended site preferences and advertisement blocking plugin for Apple's Safai browser. In contrast to Greasemonkey's focus on the DOM, PithHelmet focuses on string parsing.
*   **Internet Explorer**  [Turnabout](http://www.reifysoft.com/turnabout.php) generally supports Greasemonkey scripts with some minor JavaScript engine and CSS differences. There is limited XPath support. [Trixie](http://www.bhelpuri.net/Trixie/Trixie.htm) is a scripting add-on for Internet Explorer that is no longer under development.

As an example of the future is the following blog posting by [Rafael Rivera](http://www.extended64.com/blogs/rafael/archive/2005/07/27/1026.aspx) on July 27, 2005\. He wrote a user script in [Trixie](http://www.bhelpuri.net/Trixie/Trixie.htm)to simplify the Windows Genuine Advantage logon. Note the ecumenical approach to other browsers indicating that user scripting is no longer limited to one type of browser:

<div class="centerImage">![Blog posting of Rafael Rivera](paper257_files/wga.JPG)</div>


## Broken scripts and breaking scripts

It is probably salutary for would-be scripters to remind themselves that Web pages are short-lived phenomena; therefore, user scripts will probably frequently break. At one extreme, Web page content could be churned at every request, which would create an impossibly fast changing scripting target. On average, however, Web pages refresh content every 100 days (<span class="ref" onclick="showRef('brewington')">Brewington and Cybenko</span> 2000). My own experience indicates that scripts targeting specific words or phrases are short-lived, while scripts targeting Web page structure are more robust.

There has also been some concern that Web writers will defend their Web pages by instigating a [script war](http://greaseblog.blogspot.com/2005/03/user-script-arms-race-has-begun.html). A script war presumes that scripters would have made their scripts public, and the Web writer would have both the time and interest to change his Web page to defeat scripts. Cost-effective defense of a Web page becomes more problematical if scripts are private, there are many active scripters and different aspects of a Web page are under attack. In this situation, successful defense of a Web page's presentation is not so clear. Defense becomes even more expensive if scripting is occurring with several different types of browsers. Facing these disadvantages, Web writers are unlikely to succeed in script warfare.

Essentially, the architecture of request/response of the Web means that Web servers lose control of the Web page when they send it to the browser. Instead of warring with scripters, however, Web writers might co-opt them as volunteer Web-page usability consultants in order to refine Web-page design.



## Web design co-evolution

The greatest effect of user scripting will be in changing the culture of the Web. The top-down Web considered Web pages as containers of information placed before passive readers. The bottom-up Web considers Web pages as mere input to the reading experience. The culture of the Web will evolve so that reading a Web page will be like assembling a scrapbook where you can cut and paste, shift things about, mix together interesting pieces from various sources, and create something wholly unique for your purposes. User scripting permits the personalization of Web pages.

Web writers have much to gain from user scripting. By studying how readers change Web pages, Web writers can improve Web page designs. User scripting is, in effect, free usability testing and free product development (<span class="ref" onclick="showRef('holovaty')">Holovaty</span>, 2005, April 12). For example, Neil Kandalgaonkar scripted against [Flickr](http://www.flickr.com/), a Website for storing and sharing photographs. An early version of Flickr used Flash, which Neil's script, [Lickr](http://brevity.org/code/mozilla/greasemonkey/lickr/) disabled. The result was a evolution in the Flickr Website:

<div class="centerImage">![Lickr Web page post](paper257_files/lickr.JPG)</div>



User scripting represents one further step in the evolution of the Web as a democratic information utility. Widespread user scripting will create a virtuous feedback loop to change the Web faster.

> The key to survival will be going meta: design for the bright kids. Create a flexible, modular set of APIs and a well-documented example UI or two that shows how they are used. Learn from Amazon and release your grip on the end-user experience. <span class="ref" onclick="showRef('sindikkaeshin')">Sindikkaeshin</span> (2005, February 2)

Consider [Jonas Galvez](mailto:jonasgalvez@gmail.com) as a bellwether of the future of distributed digital content. He has reduced his [blog](http://jonasgalvez.com/br/blog/) to its essentials making it as easy as possible to write personalized Greasemonkey skins. His readers has responded and customized his blog to their tastes and purposes.

> Date: Fri, 09 Sep 2005 05:44:23 -0300  
> From: Jonas Galvez <jonasgalvez@gmail.com>  
> Subject: [Greasemonkey] Greasemonkey-based Website skins  
>   
> Has anyone thought of implementing this already? I'm running a contest right now on my blog (in Brazilian Portuguese) in which I'll give a copy of 'Greasemonkey Hacks' (due in November, right?) to the authors of the 3 best skins for my blog.  
> My idea is simple: I've stripped down my blog layout to the simplest thing possible, making it easy to create GM-based skins. If users don't like the basic layout they can install a local script that dynamically skins the blog. Saves bandwidth and gives more power to the user.  
> I know it won't really catch on but I really like the idea, and it's been well received by my readers. 24 hours after I launched the contest, I received the first entry (which looks like a winner):  
> http://jonasgalvez.com/br/blog/ (this is the blog, unstyled) http://tinyurl.com/827mv (this is the GM-based skin) http://tinyurl.com/95n9o (screenshot of the skin applied)  
> I'm fascinated.  
> The author even loaded my del.icio.us links on a sidebar (and said he's working in a solution to cache them in cookies, too).  
>   
> **Greasemonkey Digest, Vol 10, Issue 29** 

## Acknowledgements

The author wishes to acknowledge the contributions of Aaron Boodman, Mark Pilgrim, Scott Barker, Scott Turner and the suggestions of the anonymous referees.



## References

*   Boodman, A. (2004, December 6). [Happy to announce](http://www.youngpup.net/2004/1214110251). Retrieved 15 July, 2005 from http://www.youngpup.net/2004/1214110251
*   Brewington, B.E. & Cybenko, G. (2000). "[How dynamic is the Web?](http://www9.org/w9cdrom/264/264.html) In _Conference Proceedings. 9th International World Wide Web Conference, Amsterdam, May 15-19 2000._ Retrieved 22 July, 2005 from http://www9.org/w9cdrom/264/264.html
*   Dillon, A. (1994). _Designing usable electronic text: ergonomic aspects of human information usage_. London: Taylor and Francis.
*   Dodds, L. (2005, April 4). [Patterns of intermediation](http://www.ldodds.com/projects/patterns/patterns_of_intermediation.html). Retrieved 15 July, 2005 from http://www.ldodds.com/projects/patterns/patterns_of_intermediation.html
*   Gertner, M. (2005, March 15). [Greasemonkeys and obfuscators](http://www.allpeers.com/blog/?p=62). Retrieved 21 July, 2005 from http://www.allpeers.com/blog/?p=62
*   Holovaty, A. (2004, July 19). [Site-specific browser extension: All Music Guide](http://holovaty.com/blog/archive/2004/07/19/2210). Retrieved 6 July, 2005 from http://holovaty.com/blog/archive/2004/07/19/2210
*   Holovaty, A. (2005, April 12). [Why Greasemonkey is good for publishers](http://holovaty.com/blog/archive/2005/04/12/1126) Retrieved 26 July, 2005 from http://holovaty.com/blog/archive/2005/04/12/1126
*   Korpela, J. (1997). [Publishing on the Web is different](http://www.cs.tut.fi/%7Ejkorpela/webpub.html) Retrieved 4 October, 2005 from http://www.cs.tut.fi/~jkorpela/webpub.html
*   Lie, H.W. & Bos, B. (1999). [The CSS saga](http://www.w3.org/Style/LieBos2e/history/) In _Cascading style sheets, designing for the Web_, (pp. 355-360) New York, NY: Addison Wesley. Retrieved 4 October, 2005 from http://www.w3.org/Style/LieBos2e/history/
*   MacIntyre, J. (2005, September 14). [Killer buzz flocks to new browser](http://www.wired.com/news/technology/0,1282,68823,00.html). _Wired news._ Retrieved 5 October, 2005 from http://www.wired.com/news/technology/0,1282,68823,00.html
*   Markoff, J. (2005, July 18). Marrying maps to data for a new Web service. _New York Times_, Section C, p. 1,8.
*   Microsoft Corporation. (2003, June 30). [Windows history, Internet Explorer history](http://www.microsoft.com/windows/WinHistoryIE.mspx). Retrieved 4 October, 2005 from http://www.microsoft.com/windows/WinHistoryIE.mspx
*   Mozilla. (n.d.). [nglayout project/gecko layout engine](http://www.mozilla.org/newlayout/faq.html). Retrieved 20 July, 2005 from http://www.mozilla.org/newlayout/faq.html
*   Mozilla Update. (n.d.). [Firefox extensions](https://addons.mozilla.org/extensions/?application=firefox). Retrieved 10 July, 2005 from https://addons.mozilla.org/extensions/?application=firefox
*   News.Com. (2001, June 13). [Online ads get in your face](http://news.com.com/2100-1023-268365.html?legacy=cnet). Retrieved 28 July, 2005 from http://news.com.com/2100-1023-268365.html?legacy=cnet
*   Nielsen, J. (2005, June 27). [Usability: empiricism or ideology?](http://www.useit.com/alertbox/20050627.html) Retrieved 5 July, 2005 from http://www.useit.com/alertbox/20050627.html
*   Nielsen, J. (2005, October 3). [Top ten Web design mistakes of 2005](http://www.useit.com/alertbox/designmistakes.html) Retrieved 3October , 2005 from http://www.useit.com/alertbox/designmistakes.html
*   Parparita, M. (2005, March). [Adding persistent searches to Gmail](http://persistent.info/archives/2005/03/01/gmail-searches). Retrieved 5 October, 2005 from http://persistent.info/archives/2005/03/01/gmail-searches
*   Schriver, K.A. (1997). Dynamics in document design: creating text for readers. New York, NY: John Wiley.
*   Sindikkaeshin. (2005, February 2). [Greasemonkey stole your job (and your business model)](http://dream.sims.berkeley.edu/%7Eryanshaw/wordpress/2005/02/18/greasemonkey-stole-your-job-and-your-business-model/). Retrieved 14 July, 2005 from http://dream.sims.berkeley.edu/~ryanshaw/wordpress/2005/02/18/ greasemonkey-stole-your-job-and-your-business-model/
*   Turner, S. (2001). Active Browsing, _Proceedings of the IASTED International Conference Internet and Multimedia Systems and Applications_ (Honolulu, HI, August 13–16, 2001), pp. 181–186.
*   Wikipedia. (n.d.). _[Pop-up ad](http://en.wikipedia.org/wiki/Popup_ads)._ Retrieved 5 July, 2005 from http://en.wikipedia.org/wiki/Popups_ads
*   Wikipedia. (n.d.)._[Web browser](http://en.wikipedia.org/wiki/Web_browser)._ Retrieved 3 July, 2005 from http://en.wikipedia.org/wiki/Web_browser
*   W3C. (n.d.).[Document Object Model FAQ](http://www.w3.org/DOM/faq.html#Webpages). Retrieved 20 July , 2005 from http://www.w3.org/DOM/faq.html#Webpages

