#### Vol. 11 No. 2, January 2006



# Some features of _alt_ texts associated with images in Web pages

#### [Timothy C. Craven](mailto:craven@uwo.ca)  
Faculty of Information and Media Studies  
The University of Western Ontario  
London, Ontario N6A 5B7,Canada  


#### Abstract

> **Introduction**. This paper extends a series on summaries of Web objects, in this case, the <var>alt</var> attribute of image files.  
> **Method.** Data were logged from 1894 pages from Yahoo!'s random page service and 4703 pages from the Google directory; an _img_ tag was extracted randomly from each where present; its _alt_ attribute, if any, was recorded; and the header for the corresponding image file was retrieved if possible.  
> **Analysis.** Associations were measured between image type and use of null _alt_ values, image type and image file size, image file size and _alt_ text length, and _alt_ text length and number of images on the page.  
> **Results.** 16.6% and 17.3% of pages respectively showed no _img_ elements. Of 1579 and 3888 _img_ tags randomly selected from the remainder, 47.7% and 49.4% had _alt_ texts, of which 26.3% and 27.5% were null. Of the 1316 and 3384 images for which headers could be retrieved, 71.2% and 74.2% were GIF, 28.1% and 20.5%, JPEG; and 0.8% and 0.8% PNG. GIF images were more commonly assigned null _alt_ texts than JPEG images, and GIF files tended to be shorter than JPEG files. Weak positive correlations were observed between image file size and _alt_ text length, except for JPEG files in the Yahoo! set. _Alt_ texts for images from pages containing more images tended to be slightly shorter.  
> **Conclusion.** Possible explanations for the results include GIF files' being more suited to decorative images and the likelihood that many images on image-rich pages are content-poor.


## Introduction

This paper represents an extension to a series of research reports on how people and organizations summarize Web pages, especially how they summarize their own Web pages in descriptions and keywords in meta tags (Craven [2004a](#Craven2004a); Craven [2004b](#Craven2004b), Craven [2004c](#Craven2004c); and relevant items cited therein), though also to some extent how they summarize external Web pages (Craven [2002](#Craven2002)). What will be examined here is how people textually summarize images on their Web pages; specifically, their use of the <var>alt</var> attribute of the <var>img</var> tag.

In addition to the work of the author, a few other researchers have also investigated descriptions and keywords in meta tags: Turner and Brackbill ([1998](#Turner)) have reported results of a small experiment that showed that addition of a description did not improve retrievability of Web pages on Infoseek and Altavista; similar results have been reported for the these two search engines and five others by Henshaw and Valauskas ([2001](#Henshaw)); Drott ([2002](#Drott)) has noted the extent to which description and keyword meta tags are used in the sites of sixty Fortune Global 500 companies. Alimohammadi ([2004](#Alimohammadi)) has found that description and keyword meta tags are less common on Iranian Websites than elsewhere on the Web.

External descriptions of Web pages have also been examined by Wheatley and Armstrong ([1997](#Wheatley)), and Amitay ([2001](#Amitay)) developed a tool called SnipIt to extract descriptive passages with URLs from Web pages and another tool called InCommonSense to select from among these the 'best' descriptive passage for each URL.

A widely used model for classifying image descriptions at the conceptual level is the Panofsky/Shatford model which involves twelve facets in a three-by-four matrix, one dimension of which is divided into 'generic', 'specific', and 'about' and the other into 'who', 'what', 'where', and 'when'. Hollink _et al._ ([2004](#Hollink)) found in an experiment that facets in the 'generic' set were most likely to be used in both queries and descriptions, though the frequency of specific terms was higher in queries than in descriptions.

The frequency distribution of image tags on Web pages has been examined by Ajiferuke and Wolfram ([2005](#Ajiferuke)), who found that a generalized inverse Gaussian-Poisson (GIGP) model supplied the best overall fit, though the distributions within individual Websites were multi-modal; the same study also showed .com and .edu sites as having a significantly higher image count per page than .net and .org sites.

Kanungo _et al._ ([2002](#Kanungo)), in a study of text in images (based on the query 'newspapers' on Google), found that 42% of sampled images contained text; 59% of images with text contained at least one word that did not appear in the HTML file; 36% of images with text contained only words also found in the HTML file; 5% of images with text contained 'non-English script' (not otherwise defined). Number of images per page varied from zero to more than 200, in a typical inverse exponential distribution.

### The <var>alt</var> attribute

There are various means by which a Web page creator can disseminate textual information about an image on a page, but by far the most commonly used standardized method is the <var>alt</var> attribute for the <var>img</var> tag, which has been present in HTML since version 2.0 (Berners-Lee [1995](#Berners-Lee); Korpela [2005](#Korpela)) and is considered to be required (Bersvendsen [2004](#Bersvendsen), Clark [2003](#Clark)).

The intended function of the <var>alt</var> attribute is to provide a substitute for the image in cases where the image itself cannot be viewed. Such cases include viewing a page over a low-speed line or from an overloaded server without waiting for the images to download, with image display turned off to improve speed or because of security concerns, or in a text-only browser, such as Lynx; and listening to a page as rendered into speech by screen-scraping assistive software.

Providing 'a text equivalent for every non-text element' (for example, by means of the <var>alt</var> attribute) is a checkpoint in the W3C's Web Content Accessibility Guidelines (W3C [1999c](#W3C1999c)). In a comparison of usability assessment tools, Brajnik ([2002](#Brajnik)) found that [A-Prompt](http://aprompt.snow.utoronto.ca/), [Bobby](http://www.watchfire.com/products/desktop/accessibilitytesting/default.aspx), [Net-Mechanic](Net-Mech), [LinkBot](http://www.watchfire.com/news/releases/01-1-00.aspx), [Dr HTML](http://www2.imagiware.com/RxHTML/), [Web SAT](http://zing.ncsl.nist.gov/WebTools/WebSAT/overview.html), and [LIFT](http://www.usablenet.com/) all checked for presence of the <var>alt</var> attribute, although MacroBot, MetaBot, Web Criteria, and Web Garage did not.

In spite of its apparent usefulness, the <var>alt</var> attribute is often not applied (Lopresti and Zhou [2000](#Lopresti)). Mukherjea _et al._ ([1999](#Mukherjea)) state that most authors do not use it.

### Guidelines

According to the W3C ([1999a](#W3C1999a)), the alternate text should 'serve as content when the element cannot be rendered normally'; two things to avoid are irrelevant and meaningless alternate text;an example given of the former is the text 'red ball' applied to an image of a red ball that functions as a decoration.

The US Access Board ([2004](#USAccessBoard)) specifies that the <var>alt</var> text 'states the purpose of the image' for a navigational image or 'explains the meaning of the image' for an image contributing to page content. It 'should, when possible, communicate the same information as its associated element.'

Slatin states, 'ALT text should do two things: (1) briefly identify the nontextual element to which it is attached, and (2) provide access to the functionality represented by that element.' <var>Alt</var> text need not be a complete substitute for the image, but should be 'succinct, descriptive, and accurate' (Slatin [2001](#Slatin): p. 78). Succinctness would include omission of redundant expressions such as 'picture of' and not using jokes or uninformative placeholders like 'short description of image' or 'loading image' (Clark [2003](#Clark)).

'There is no one right alt text for any particular image. It all depends upon the context and the purpose of the image' (WebAIM [2005](#WebAIM)). Thus, the same image might reasonably be given different <var>alt</var> attributes on different pages.

For an image rich in content, some say that the alternative text should be functionally equivalent. The author should 'think of the text and the image as alternative representations for content' (Flavell [2004](#Flavell)); the <var>alt</var> text 'should be a textual alternative for the meaning of the image. It should convey the same thing as the image' (Hickson [2002](#Hickson)).

Others allow it to be a description of the image. Korpela ([2005](#Korpela)) concedes that 'the meme of regarding _alt_ as a description has become frustratingly common' and so allows it to be either an equivalent or a description. Idocs ([2002](#Idocs)) says that a description may be used if no substitute is possible. To distinguish the two kinds of alternate text, Korpela ([2005](#Korpela)) proposes enclosing the text in brackets when it is a description of, rather than a replacement for, the image.

In any case, 'The most appropriate _alt_ text communicates the purpose of the graphic, not its appearance' (WebAIM [2005](#WebAIM)). McAlpine ([2005](#McAlpine)) does recommend, however, including the size of the image file if this is particularly large; this information could be of assistance to users in deciding whether they wish to download the image or not.

If such an image is merely 'supplemental or interesting', Flavell ([2004](#Flavell)) recommends a 'text that summarises the major feature that you wanted to bring to the reader's attention', while if it is 'critical for understanding the page', it may be that no suitable text can be provided.

Sources also differ somewhat on questions of punctuation and spacing. According to the W3C ([1999b](#W3C1999b)), 'Authors should not declare attribute values with leading or trailing white space'; but Watchfire ([2005](#Watchfire)) recommends including leading or trailing spaces to avoid <var>alt</var> texts' running together; and this is also one of McAlpine ([2005](#McAlpine))'s suggestions. Flavell ([2004](#Flavell)) notes how unpunctuated <var>alt</var> texts in adjacent images can result in 'howlers' such as 'Photo of a bull in the water canoeing', when viewed in certain text browsers. To avoid this conflict, Tobias ([2004](#Tobias)) recommends surrounding texts with square brackets, also a suggestion of McAlpine ([2005](#McAlpine)) along with vertical bars.

Another area of difference is the use of <var>alt</var> attributes with values equal to the empty string. 'Some guides and checkers say that empty _alt_ texts should not be used. However, empty _alt_ texts are perfectly valid and correct when the appropriate textual alternative to an image is an empty string' (Korpela [2005](#Korpela)). An empty <var>alt</var> text has been recommended for graphics included for spacing (U.S. Access Board [2004](#USAccessBoard); Tobias [2004](#Tobias)), purely decorative images (Korpela [2005](#Korpela); Idocs [2002](#Idocs); Bersvendsen [2004](#Bersvendsen); Tobias [2004](#Tobias)), mere illustrations, images in navigational links in which suitable text is already present (Korpela [2005](#Korpela)), or 'graphics which do not convey content' (WebAIM [2005](#WebAIM)). For spacers, however, text consisting of a space has also been recommended (Korpela [2005](#Korpela)). Contrary to the majority opinion, Letourneau and Freed ([2000](#Letourneau)) suggest providing a description for a decorative or incidental image, such as 'Drawing of a house'.

For an image of text, equivalent, if not exactly identical, text has been recommended (Korpela [2005](#Korpela); Letourneau and Freed [2000](#Letourneau)). If the text is a logo, the word 'logo' may be added (Korpela [2005](#Korpela)), or the text may just be the name of the entity represented (Flavell [2004](#Flavell); Idocs [2002](#Idocs); Tobias [2004](#Tobias)). If the image is an initial capital, the substitute text should just be the capital letter (Tobias [2004](#Tobias)).

For an image representing punctuation, such as a bullet, either the punctuation (Korpela [2005](#Korpela); Idocs [2002](#Idocs); Tobias [2004](#Tobias)) or an equivalent expression such as 'item': should be employed (Korpela [2005](#Korpela)), at least if not obtrusive (Flavell [2004](#Flavell)), or even just a space (Flavell [2004](#Flavell)) or an empty string (WatchFire [2005](#Watchfire)). For an image of a symbol, the name of the symbol should be used (Korpela [2005](#Korpela)). Korpela ([2005](#Korpela)) and Idocs ([2002](#Idocs)) deprecate the use of ASCII art, such as '==>' for an arrow, although using a row of hyphens for a horizontal rule seems to be acceptable (Tobias [2004](#Tobias)).

Korpela ([2005](#Korpela)) also states that <var>alt</var> texts should be in normal prose and should be suitable for speech synthesis and hence avoid abbreviations.

For a navigational image, a suitable word should be included, with punctuation (Korpela [2005](#Korpela)); the word may correspond to the destination of the link (Korpela [2005](#Korpela); Letourneau and Freed [2000](#Letourneau)) or briefly describe it (Flavell [2004](#Flavell)), or identify its function (Letourneau and Freed [2000](#Letourneau)).

Since the <var>alt</var> text is intended to be read with the main text, it should generally flow well with it ( [Tobias2004](#Tobias)). More specifically, it should not duplicate the main text ([WebAIM 2005](#WebAIM); [WatchFire 2005](#Watchfire); [Tobias 2004](#Tobias); [McAlpine 2005](#McAlpine)). Clark ([2003](#Clark)) also deprecates text that repeats the filename of the image.

'There is no set limit on the length of an _alt_ text, but... a very long alt may not be fully displayed when image-loading is turned off or when the browser cannot locate the image file. By convention, limit _alt_ texts to 1,024 characters (1 K) or less' ([Clark 2002](#Clark)). Korpela ([2005](#Korpela)) advises that an <var>alt</var> text should be no more than 50 characters. Slatin ([2001](#Slatin)) points out that the JAWS screen reader causes problems with <var>alt</var> text that exceeds 150 characters.

Korpela ([2005](#Korpela)) suggests that the <var>alt</var> text be written first, before the image is selected. More generally, Slatin ([2001](#Slatin)) advocates composing the entire page first as a text, including image <var>alt</var> values, and only then adding the images, forcing the arrangement of the images to follow the logical text order.

Unlike images specified with the <var>img</var> tag, background images are specified in attributes of other tags (chiefly <var>body</var>, and sometimes <var>table</var>) and so cannot themselves have attributes, including <var>alt</var>. For this reason, WebAIM ([2005](#WebAIM)) says, 'Do not put important images in the background'.

Apart from accessibility, the <var>alt</var> attribute can be used to improve retrievability of a site on search engines ([Winters 2005](#Winters)) ([Kovacs 2003](#Kovacs)). Abuse, however, has caused many search engines to ignore the <var>alt</var> text ([Wall 2004](#Wall)). Tobias ([2004](#Tobias)) advises against '[spamdexing](http://en.wikipedia.org/wiki/Spamdexing)' in <var>alt</var> attributes, as does McAlpine ([2005](#McAlpine)).

### Treatment by browsers

Common graphical browsers now treat <var>alt</var> texts as text for hint boxes ('tool tips'), even though it is the <var>title</var> attribute that is intended for this purpose ([Flavell 2004](#Flavell); [Korpela 2005](#Korpela); [Bersvendsen 2004](#Bersvendsen); [Tobias 2004](#Tobias)). Consequently, many page authors, writing to the browsers rather than to the standards, may construct <var>alt</var> texts with the intention of having them appear as hints.

If it is absent, text browsers typically display the filename or a placeholder text such as '[Image]' ([Bersvendsen 2004](#Bersvendsen), [Clark 2003](#Clark), [McAlpine 2005](#McAlpine)), which is probably undesirable. To avoid this problem, a null value ('') may be assigned to the attribute.

### Use in retrieval

The <var>alt</var> attribute has been used in numerous research studies of Web image retrieval. It is given the highest weight in the system of La Cascia _et al._ ([1998](#LaCascia)). It has the second-highest weight, after the 'link string' (the visible text in any a element) in the system described by Lu _et al._ ([2000](#LuY)). Mukherjea _et al._ ([1999](#Mukherjea)) consider query terms that occur in <var>alt</var> texts and image names to be 'very relevant' in ranking images in retrieval. Lu _et al._ ([2001](#LuG)) assign equal weight for retrieval to <var>alt</var> text and to anchor text and image URL, with half that weight being assigned to other textual cues (metadata, title, heading, and other terms).

Other systems that have made use of the <var>alt</var> attribute in combination with other features include those of Shen _et al._ ([2000](#Shen)), Chen _et al._ ([2001](#Chen)), Jayaratne _et al._ ([2003](#Jayaratne2003); [2004](#Jayaratne2004)) and Smith and Chang ([1997](#Smith)).

Some retrieval studies report using other properties of images, such as <var>title</var> (Shen _et al._ [2000](#Shen)) and 'caption' (Yang and Lee [2003](#Yang)) or 'image caption' ( [Shen _et al._ 2000](#Shen); [Jayaratne _et al._ 2003](#Jayaratne2003); [2004](#Jayaratne2004)). (HTML tables may have captions, and images in word processors may have captions, but not images in HTML).

Not all <var>alt</var> attributes are equally useful and not all images are equally worth retrieving. Examples of bad <var>alt</var> text given by Pilgrim ([2002](#Pilgrim)) are any containing HTML tags, filenames, 'alt text', 'Click here', or 'turn images on'. Some studies have accordingly applied filtering techniques to reduce noise.

Paek and Smith ([2003](#Paek)) used occurrences of certain keywords ('bullet', 'button', 'rule', 'line') to categorize images automatically as 'decorative', and of body text words to categorize image labels as 'body text'. Other label-based categories were 'advertisement', 'informational', 'logo', and 'navigation'. Combined with image type (GIF/JPEG), number of images on page, and visual properties (including height and width, number of colours, and various saturation properties), a decision tree was developed that would automatically class images as content or non-content with an overall accuracy of 84% when tested on four sites.

<var>Alt</var> texts are sometimes missing, even from significant images, which Chen _et al._ ([2001](#Chen)) attribute to the fact that 'many editors are too lazy'. Yang and Lee ([2003](#Yang)) consider that images without <var>alt</var> texts may be rejected as less important.

Among text clues in an image retrieval study by Munson and Tsymbolenko ([2001](#Munson)), only the image filename, the title element of the HTML document, and the <var>alt</var> text had significant recall. There was a high level of precision for the <var>alt</var> text; but the recall, though significant, was relatively low, unsurprisingly, in view of previous research showing that more than half of <var>alt</var> values were empty or wrong.

### Hypotheses

The present study aimed, among other things, to test the following hypotheses about author behaviour in assigning, or not assigning, <var>alt</var> texts to Web page images.

1.  GIF images would more commonly be assigned null values than JPEG images because they are more useful for elements with little content, such as minor decorations, punctuation, and the like. As a corollary, GIF image files would tend to be smaller than JPEG image files for the same reason.
2.  Bigger image files would tend to be assigned longer <var>alt</var> texts because they contain more information.
3.  <var>Alt</var> texts for images from pages containing more images would tend to be shorter, because a greater proportion of images on such pages would tend to be small and low on content. As a corollary, shorter image files would tend to be associated more with pages containing more images.

## Research method

An existing personal software package used for data capture in earlier studies in the present series was modified to allow capture, from individual Web pages, of the following data related to a random image on each page: the image URL; the number of images on the page; the <var>alt</var> attribute value for the image, if any; and the <var>Content Type</var> and <var>Content Length</var> of the image file, if its header could be retrieved from the host.

The package was used to attempt to log data from 2048 pages retrieved in June of 2004 from Yahoo!'s [random page service](http://random.yahoo.com/bin/ryl) and 6356 retrieved in May and June of 2002 from the higher levels of [Google's directory](http://directory.google.com/) The package automatically rejected invalid links, including non-responding servers, server errors, and files that did not appear to be HTML. Data were logged for the remaining pages.

## Results

Data were logged from 1894 pages from the Yahoo! set and 4703 pages from the Google set (92.5% and 74.0% respectively).

Number of images on a page varied from 0 to 373 for the Yahoo! set and from 0 to 914 for the Google set, with means of 22.1 and 22.9 and medians of 11 and 10; in the Yahoo! set, 16.6% (315) had no images; 6.0% (114), one image; and 4.8% (91), two; in the Google set, 17.3% (815), no images; 6.7% (317), one image; and 4.5% (211), two (Figure 1).

<div align="center">![figure1](p250fig1.gif)</div>

<div align="center">  
Figure 1: Number of images per page</div>

Of all 1579 image files selected in the Yahoo! set, 47.7% (737) had <var>alt</var> texts; of the 3888 image files from the Google set, 49.4% (1919) had <var>alt</var> texts. Length of <var>alt</var> texts varied from 0 to 255 characters and from 0 to 614 characters respectively, with means of 15.8 and 16.5 and medians of 11 and 10; 26.3% (194) and 27.5% (528) of <var>alt</var> texts were null; 4.1% (30) and 4.3% (82) consisted of a single character; and 0.5% (4) and 0.7% (13), of two characters.

The most common <var>alt</var> texts, apart from "", were as follows.

<table width="456" border="1" cellspacing="0" cellpadding="3" style="background-color: #FDFFDD; font-family: Verdana, Geneva, Arial, Helvetica, sans-serif; font-size: smaller; font-style: normal; border: solid;" align="center"><caption align="bottom">  
**Table 1: Common <var>alt</var> texts**</caption>

<tbody>

<tr>

<th>Text</th>

<th>Yahoo! frequency</th>

<th>Google frequency</th>

<th>Mean proportion</th>

</tr>

<tr>

<td align="right">1</td>

<td align="right">14</td>

<td align="right">25</td>

<td align="right">1.6%</td>

</tr>

<tr>

<td align="right">setstats</td>

<td align="right">5</td>

<td align="right">20</td>

<td align="right">0.9%</td>

</tr>

<tr>

<td align="right">pad</td>

<td align="right">8</td>

<td align="right">7</td>

<td align="right">0.7%</td>

</tr>

<tr>

<td align="right">home</td>

<td align="right">4</td>

<td align="right">13</td>

<td align="right">0.6%</td>

</tr>

<tr>

<td align="right">*</td>

<td align="right">3</td>

<td align="right">14</td>

<td align="right">0.6%</td>

</tr>

<tr>

<td align="right">Google</td>

<td align="right">3</td>

<td align="right">13</td>

<td align="right">0.6%</td>

</tr>

</tbody>

</table>

Common keywords and phrases in <var>alt</var> text were as follows.

<table width="456" border="1" cellspacing="0" cellpadding="3" style="background-color: #FDFFDD; font-family: Verdana, Geneva, Arial, Helvetica, sans-serif; font-size: smaller; font-style: normal; border: solid;" align="center"><caption align="bottom">  
**Table 2: Common keywords and phrases**</caption>

<tbody>

<tr>

<th>Word or phrase</th>

<th>Yahoo! frequency</th>

<th>Google frequency</th>

</tr>

<tr>

<td align="right">bytes</td>

<td align="right">17</td>

<td align="right">49</td>

</tr>

<tr>

<td align="right">click</td>

<td align="right">9</td>

<td align="right">35</td>

</tr>

<tr>

<td align="right">com</td>

<td align="right">22</td>

<td align="right">51</td>

</tr>

<tr>

<td align="right">enter</td>

<td align="right">12</td>

<td align="right">12</td>

</tr>

<tr>

<td align="right">gif</td>

<td align="right">14</td>

<td align="right">37</td>

</tr>

<tr>

<td align="right">home</td>

<td align="right">20</td>

<td align="right">42</td>

</tr>

<tr>

<td align="right">jpg</td>

<td align="right">11</td>

<td align="right">21</td>

</tr>

<tr>

<td align="right">logo</td>

<td align="right">15</td>

<td align="right">39</td>

</tr>

<tr>

<td align="right">online</td>

<td align="right">6</td>

<td align="right">21</td>

</tr>

<tr>

<td align="right">page</td>

<td align="right">11</td>

<td align="right">28</td>

</tr>

<tr>

<td align="right">search</td>

<td align="right">10</td>

<td align="right">24</td>

</tr>

<tr>

<td align="right">site</td>

<td align="right">10</td>

<td align="right">21</td>

</tr>

<tr>

<td align="right">web</td>

<td align="right">9</td>

<td align="right">26</td>

</tr>

</tbody>

</table>

Of these, 'jpg' and 'gif' are file extensions, and 'com' is a top level domain.

Only two texts were observed that used non-Western-European characters, one in the Yahoo! set, where the page coding was Cyrillic (Windows-1251), and the other in the Google set, where the page coding was Central European (ISO-8859-2).

The most common filenames were as follows.

<table width="456" border="1" cellspacing="0" cellpadding="3" style="background-color: #FDFFDD; font-family: Verdana, Geneva, Arial, Helvetica, sans-serif; font-size: smaller; font-style: normal; border: solid;" align="center"><caption align="bottom">  
**Table 3: Common filenames**</caption>

<tbody>

<tr>

<th>Filename</th>

<th>Yahoo! frequency</th>

<th>Google frequency</th>

</tr>

<tr>

<td align="right">arrow.gif</td>

<td align="right">5</td>

<td align="right">9</td>

</tr>

<tr>

<td align="right">blank.gif</td>

<td align="right">10</td>

<td align="right">33</td>

</tr>

<tr>

<td align="right">clear.gif</td>

<td align="right">5</td>

<td align="right">36</td>

</tr>

<tr>

<td align="right">clearpixel gif</td>

<td align="right">5</td>

<td align="right">17</td>

</tr>

<tr>

<td align="right">dot.gif</td>

<td align="right">6</td>

<td align="right">17</td>

</tr>

<tr>

<td align="right">logo.jpg</td>

<td align="right">6</td>

<td align="right">9</td>

</tr>

<tr>

<td align="right">logo.gif</td>

<td align="right">16</td>

<td align="right">33</td>

</tr>

<tr>

<td align="right">pixel.gif</td>

<td align="right">9</td>

<td align="right">35</td>

</tr>

<tr>

<td align="right">s.gif</td>

<td align="right">6</td>

<td align="right">16</td>

</tr>

<tr>

<td align="right">serv</td>

<td align="right">14</td>

<td align="right">25</td>

</tr>

<tr>

<td align="right">shim.gif</td>

<td align="right">7</td>

<td align="right">29</td>

</tr>

<tr>

<td align="right">space.gif</td>

<td align="right">5</td>

<td align="right">20</td>

</tr>

<tr>

<td align="right">spacer.gif</td>

<td align="right">109</td>

<td align="right">208</td>

</tr>

<tr>

<td align="right">trans.gif</td>

<td align="right">7</td>

<td align="right">10</td>

</tr>

<tr>

<td align="right">trans_1x1.gif</td>

<td align="right">8</td>

<td align="right">7</td>

</tr>

<tr>

<td align="right">transparent.gif</td>

<td align="right">9</td>

<td align="right">12</td>

</tr>

<tr>

<td align="right">visit.gif</td>

<td align="right">6</td>

<td align="right">20</td>

</tr>

</tbody>

</table>

Of these, <var>spacer.gif</var> was most usually, where available, a 43-byte GIF file, but there were variants of different sizes, in one case in the Yahoo! set a text file of 14,309 bytes and in one in the Google set a text file of 25,056 bytes; <var>clear.gif</var> and <var>shim.gif</var> were similar; where available, <var>clearpixel.gif</var> was almost always a 43 byte file (two exceptions of 807 bytes in the Google set), as was <var>space.gif</var> (four exceptions of various sizes in the Google set); the <var>logo</var> files all appeared to be different (with the exception of one image where two pages on the same site happened to be selected), as did <var>arrow.gif</var>; the picture was mixed for <var>blank.gif</var>, <var>trans.gif</var>, <var>pixel.gif</var>, and <var>transparent.gif</var>; <var>trans_1x1.gif</var>, at 43 bytes, was a 1x1 Web bug and always occurred in http://us.st1.yimg.com/store1.yimg.com/Img/; finally, <var>serv</var> was always at http://geo.yahoo.com/serv, was also a 1x1 Web bug, and accounted for all instances of the <var>alt</var> text '1' in both sets.

Of all the 114 URLs containing the string 'logo' in the Yahoo! set, only two had texts that included 'logo' as a word, and another three had texts that included the filename; of the 280 'logo' URLs in the Google set, twenty-two had texts that included the word 'logo' and another three had texts that included the filename.

Image content types broke down into 71.2% and 74.2% image/gif, 28.1% and 20.5%, image/jpeg, 0.8% and 0.8% image/png, and the rest other (basically 'text/html', which is, of course, not really an image format, as is discussed further below).

For GIF images, sizes varied from 0 to 405,252 bytes for the Yahoo! set and from 0 to 404,222 bytes for the Google set, with means of 5191.7 and 3565.1 and medians of 654 and 807; there was a concentration near the bottom of the range at 43 bytes (137 images in the Yahoo! set and 353 in the Google set). For JPEG images, sizes varied from 0 to 295,646 bytes and from 0 to 297,798 bytes, with means of 16,858.9 and 15,493.2 and medians of 7446 and 7742\. Plots of the distributions of image sizes for the two file types clearly show GIF images tending to be smaller and JPEG images larger (Figure 2).

<div align="center">![Figure2](p250fig2.gif)</div>

<div align="center">  
**Figure 2: Image sizes**</div>

<var>Alt</var> text was present for 47.3% (=443/997) of GIF files versus 43.8% (=139/317) of JPEG files in the Yahoo! set, and for 50.1% (=1259/2511) of GIF files versus 47.3% (=329/695) of JPEG files for the Google set; the differences in proportion were not statistically significant (chi-squared p=0.2898 and 0.1912). Length of <var>alt</var> text, where present, varied for GIF images from 0 to 255 for the Yahoo! set and from 0 to 614 characters for the Google set; for JPEG images, it varied from 0 to 165 for the Yahoo! set and from 0 to 183 for the Google set (Figure 3).

<div align="center">![Figure 3](p250fig3.gif)</div>

<div align="center">  
**Figure 3: _alt_ text lengths**</div>

Null values were found for 28.4% (=126/443) of GIF file <var>alt</var> texts versus 18.0% (=25/139) of JPEG texts in the Yahoo! set and for 28.4% (=358/1259) of GIF file <var>alt</var> texts and 20.7% (=68/329) of JPEG texts in the Google set; the differences in proportions between the two file types were statistically significant in both sets (chi-squared p=0.0141 for the Yahoo! set and 0.0046 for the Google set).

Correlation between length of <var>alt</var> text and image file size was slightly positive for GIF files in both sets (0.1200 and 0.1024); there was virtually no correlation for JPEG files in the Yahoo! set (-0.0229) and a weak positive correlation in the Google set (0.0720).

Correlations between image count and length of <var>alt</var> text were slightly negative (-0.1120 and -0.1056) and were statistically significant (t=-3.0544, df=735, p < 0.01; t=-4.6545, df=1922, p < 0.01). as can be seen from Figure 4, the relationship was not linear, but rather involved an almost complete exclusion of cases where both image count and <var>alt</var> text length were high, while allowing many instances of simultaneous low image count and low text length. correlations between image count and image size were very slightly negative (-0.0917 and -0.0823) and were also statistically significant (t=-4.0059, df=1892, p < 0.001; t=-5.6583, df=1892, p < 0.01).

<div align="center">![Figure 4](p250fig4.gif)</div>

<div align="center">  
**Figure 4: <var>Alt</var> text length versus image count**</div>

## Discussion

The difference in proportion of valid pages between the two sets was likely mostly a result of time, the Google set having originated two years before the Yahoo! set and neither having been updated in the intervening period.

The mean and median number of images per page were slightly lower than those observed by Ajiferuke and Wolfram ([2005](#Ajiferuke)), which ranged from 25.4 to 36.4 and from 14.0 to 23.0 respectively, depending on top-level domain; a likely explanation is that the present study did not restrict itself explicitly to top-level (home) pages and that lower-level pages tend to have somewhat fewer images.

The results of this study showed a slightly higher proportion of pages using <var>alt</var> texts than reported by Kanungo _et al._ ([2002](#Kanungo)), although it was still marginally true, in accordance with the observation of Mukherjea _et al._ ([1999](#Mukherjea)), that most images sampled did not have them.

The rarity of non-Western-language characters in the <var>alt</var> texts, at least in comparison with the current experience of the Web, has a fairly obvious cause. Both sets were likely strongly biased in favour of English-language materials: the Google set, certainly, was derived from an English-language version of the directory, which appears to list almost exclusively pages in English.

The relative frequency of image formats in this study is quite different from that reported by Security Space ([2005](#SecuritySpace)) of 62.7% GIF, 53.3% JPEG, and 6.2% PNG. This is no doubt largely because Security Space is measuring something different, as is obvious from the fact that its percentages do not add up to 100%: not the proportion of images in a particular format, but the proportion of sites that contain any images in the given format. Most of the images on a page might be small, decorative GIF images, for example, but the same page might contain one large photographic JPEG or PNG image.

The 43-byte size commonly observed for the Web bugs is not actually the minimum possible for a GIF file; for example, both Adobe Photoshop and, with the right settings, GIMP, readily create GIF files of only 35 bytes. Truly minimal GIF files, however, would not be transparent, and thus might be visible to alert readers.

Data on the images may be flawed in some cases because of defects in the header information returned by the servers. The few images reported as having zero size may actually just not have had their sizes specified in the HTTP header; the <var>Content-Length</var> header line is not actually required in HTTP. Misidentification of the Content-Type is also not unheard of, even for commonly used content types. For example, a HEAD request on the URL http://www.fortunecity.com/westwood/karan/21/lairline.gif returned a header that both omitted <var>Content-Length</var> and misidentified a JPEG file as a GIF file (likely because of its having the wrong extension). The relatively few file headers with <var>Content-Type</var> text/html or text/plain are partly simply errors of the kind just mentioned and partly error pages returned by the servers when the image files cannot be found in response to unreferred requests.

In spite of these problems, looking at <var>Content-Length</var> rather than image dimensions served several purposes in comparison to the alternative of taking the product of the image dimensions as the measure of the image's size. Dimensions specified in the HTML code could have been used where available, but, if this were not the case, it would have been necessary to download and analyse the image file itself. Relying on a mixture of the two methods would have been methodologically untidy, while adopting the second alone would have taken still longer. It should also be considered that the dimensions of an image may also be a relatively poor measure of its information content from a theoretical point of view: an image of relatively small dimensions may contain much more detail than another image of greater dimensions. Moreover, a GIF image may be animated, introducing a third dimension that is somewhat difficult to make commensurable with the other two. GIF and JPEG images are both compressed, and compression generally reduces simple images more than complex ones. Thus, file size seems to be a better measure of image size.

## Conclusion

This study confirmed most of the hypothesized relationships, at least to some extent. GIF images were indeed more commonly assigned null <var>alt</var> texts than JPEG images. GIF files also clearly tended to be shorter than JPEG files. A weak positive correlation was observed between image file size and <var>alt</var> text length for GIF files; contrary what had been hypothesized, however, such a correlation was not found for JPEG files in the Yahoo! set. <var>Alt</var> texts for images from pages containing more images did tend to be shorter, but only weakly.

The explanations suggested for the observed relationships doubtless have some strength; but it is also clear from the weaknesses of the correlations observed, and especially from the partial failure of the hypothesis relating length of text to size of image file in the case of JPEG, that there are also other factors at work affecting how Web page creators describe the images on their pages.

Thus, the main implication of the present study is not so much in its having proved any surprising new findings as in, first, confirming some general ideas certain aspects of Web authoring behaviour and, second, in suggesting some future areas for more intensive research.

As one example of more specific research directions, the author has also undertaking a more detailed study of references to image files with commonly used names, such as _arrow_, and with names equal to letters of the alphabet and what kinds of <var>alt</var> values these are assigned. Other areas of investigation might include determining the frequency with which JPEG files are compressed at other than the common ratios provided for in simple software packages like Paint and, if different compressions ratios are found, whether these correlate in any way with use of <var>alt</var> texts.

## References

*   <a name="Ajiferuke" id="Ajiferuke"></a>Ajiferuke, I., & Wolfram, D. (2005). Analysis of Web page image tag distribution characteristics. _Information Processing and Management_, **41** (4), 987-1002.
*   <a name="Alimohammadi" id="Alimohammadi"></a>Alimohammadi, D. (2004). Measurement of the presence of keywords and description meta tags on a selected number of Iranian Web sites. _Online Information Review_, **28** (3), 220-223.
*   <a name="Amitay" id="Amitay"></a>Amitay, E. (2001). [_What lays in the layout_](http://www.ics.mq.edu.au/~einat/thesis/). Doctoral dissertation, Macquarie University, NSW. Retrieved 25 August, 2005 from http://www.ics.mq.edu.au/~einat/thesis/.
*   <a name="Berners-Lee" id="Berners-Lee"></a>Berners-Lee, T. (1995). [Image: IMG](http://www.w3.org/MarkUp/html-spec/html-spec_5.html#SEC5.10). In _Hypertext Markup Language - 2.0 Document structure_. World Wide Web Consortium. Retrieved 25 August, 2005 from http://www.w3.org/MarkUp/html-spec/html-spec_5.html#SEC5.10.
*   <a name="Bersvendsen" id="Bersvendsen"></a>Bersvendsen, A. (2004). [_Virtuelvis: gallery: titles and alternative text for images_](http://virtuelvis.com/gallery/alttext/). Retrieved 25 August, 2005 from http://virtuelvis.com/gallery/alttext/.
*   <a name="Brajnik" id="Brajnik"></a>Brajnik, G. (2002). [_Automatic web usability evaluation: what needs to be done?_](http://www.dimi.uniud.it/~giorgio/papers/hfweb00.html) Paper delivered at the 6th Human Factors and the Web Conference, Austin, Texas, June 2000\. Retrieved 25 August, 2005 from http://www.dimi.uniud.it/~giorgio/papers/hfweb00.html
*   <a name="Chen" id="Chen"></a>Chen, Z., Liu W., Zhang, F, Li, M., & Zhang, H. (2001). Web mining for Web image retrieval. _Journal of the American Society for Information Science and Technology_, **52**(10), 831-839.
*   <a name="Clark" id="Clark"></a>Clark, J. (2002). _Buildling accessible Websites._ Berkeley, CA: New Riders. ([Chapter 6\. The image problem.](http://joeclark.org/book/sashay/serialization/Chapter06.html) Retrieved 26 August, 2005 from http://joeclark.org/book/sashay/serialization/Chapter06.html)
*   <a name="Craven2002" id="Craven2002"></a>Craven, T.C. (2002). External descriptions of Web pages: their features and their relationships to Web page elements. _Libri_, **52**(1), 36-47.
*   <a name="Craven2004a" id="Craven2004a"></a>Craven, T.C. (2004a). Variations in use of meta tag descriptions by Web pages in different languages. _Information Processing & Management_, **40**(3), 479-493.
*   <a name="Craven2004b" id="Craven2004b"></a>Craven, T.C. (2004b). Variations in use of meta tag keywords by web pages in different languages. _Journal of Information Science_, **30**(3), 268-279.
*   <a name="Craven2004c" id="Craven2004c"></a>Craven, T.C. (2004c). Variations in use of meta tag descriptions by Web pages in different subject areas. _Library & Information Science Research_, **26**(4), 448-462.
*   <a name="Drott" id="Drott"></a>Drott, M.C. (2002). Indexing aids at corporate websites: the use of robots.txt and META tags, _Information Processing and Management_, **38**(2), 209-219.
*   <a name="Flavell" id="Flavell"></a>Flavell, AJ. (2004). [_Text-friendly authoring topics: ALT texts in IMG_](http://ppewww.ph.gla.ac.uk/~flavell/alt/alt-text.html). Retrieved 26 August, 2005 from http://ppewww.ph.gla.ac.uk/~flavell/alt/alt-text.html.
*   <a name="Hickson" id="Hickson"></a>Hickson, I. (2002). [_Mini FAQ about the alternate text of images._](http://www.hixie.ch/advocacy/alttext) Retrieved 26 August, 2005 from http://www.hixie.ch/advocacy/alttext.
*   <a name="Henshaw" id="Henshaw"></a>Henshaw, R., & Valauskas, E.J. (2001). Metadata as a catalyst: experiments with metadata and search engines in the Internet journal, First Monday. _Libri_, **51**(2), 86-101.
*   <a name="Hollink" id="Hollink"></a>Hollink, L., Schreiber, A.T., Wielinga, B.J., & Worring, M. (2004). Classification of user image descriptions. _International Journal of Human-Computer Studies_, **61**(5), 601-626.
*   <a name="Idocs" id="Idocs"></a>Idocs (2002). [_Idocs guide to HTML: the rules of ALT_](http://www.idocs.com/tags/images/images_famsupp_85.html). Retrieved 26 August, 2005 from http://www.idocs.com/tags/images/images_famsupp_85.html.
*   <a name="Jayaratne2004" id="Jayaratne2004"></a>Jayaratne, L., Ginige, A., & Jiang, Z.H. (2004). Effective indexing of Web images with keyword positioning. In Jeffrey Xu Yu, Xuemin Lin, Hongjun Lu, Yanchun Zhang (Eds.), _Advanced Web Technologies and Applications: 6th Asia-Pacific Web Conference, APWeb 2004, Hangzhou, China, April 14-17, 2004\. Proceedings._ (pp. 883-886). Berlin: Springer. (Lecture Notes in Computer Science, 3007).
*   <a name="Jayaratne2003" id="Jayaratne2003"></a>Jayaratne, L., Jiang, Z., & Ginige, A. (2003). [_A unified approach to indexing multimedia on the Web_](http://www.research.att.com/~rjana/jayaratne.pdf). Retrieved 26 August, 2005 from http://www.research.att.com/~rjana/jayaratne.pdf.
*   <a name="Kanungo" id="Kanungo"></a>Kanungo, T., Lee, C.H. & Bradford, R. (2002). [What fraction of images on the Web contain text?](http://www.csc.liv.ac.uk/~wda2001/Papers/27_kanungo_wda2001.pdf) In _Proceedings of the First International Workshop on Web Document Analysis (WDA2001), Seattle, Washington, USA, September 8, 2001_. Retrieved 26 August, 2005 from http://www.csc.liv.ac.uk/~wda2001/Papers/27_kanungo_wda2001.pdf.
*   <a name="Korpela" id="Korpela"></a>Korpela, J. (2005). [_Guidelines on ALT texts in IMG elements_](http://www.cs.tut.fi/~jkorpela/html/alt.html). Retrieved 26 August, 2005 from http://www.cs.tut.fi/~jkorpela/html/alt.html.
*   <a name="Kovacs" id="Kovacs"></a>Kovacs, P. (2003). [Optimizing for search indexes](http://isedj.org/1/32/ISEDJ.1(32).Kovacs.pdf). _Information Systems Education Journal_, **1**(32). Retrieved 26 August, 2005 from http://isedj.org/1/32/ISEDJ.1(32).Kovacs.pdf.
*   <a name="LaCascia" id="LaCascia"></a>La Cascia, M., Sethi, S. & Sclaroff, S. (1998). [Combining textual and visual cues for content-based image retrieval on the World Wide Web](http://ieeexplore.ieee.org/iel4/5665/15172/00694480.pdf). In _Proceedings. IEEE Workshop on Content-Based Access of Image and Video Libraries, 1998, 21 June 1998_, 24-28\. Retrieved 26 August, 2005 from http://ieeexplore.ieee.org/iel4/5665/15172/00694480.pdf (Note - requires subscription).
*   <a name="Letourneau" id="Letourneau"></a>Letourneau, C. & Freed, G. (2000). [_Checkpoints for guideline. 1\. Provide equivalent alternatives to auditory and visual content._](http://www.w3.org/WAI/wcag-curric/chk2-0.htm). Retrieved 26 August, 2005 from http://www.w3.org/WAI/wcag-curric/chk2-0.htm.
*   <a name="Lopresti" id="Lopresti"></a>Lopresti, D. P., & Zhou, J. (2000). Locating and recognizing text in WWW images. _Information Retrieval_, **2**(2/3), 177-206.
*   <a name="LuG" id="LuG"></a>Lu, G, Williams, B, & You, C. (2001). An effective World Wide Web image search engine. _Journal of Information Science_, **27**(1), 27-37.
*   <a name="LuY" id="LuY"></a>Lu, Y., Hu, C., Zhu, X., Zhang, H., & Yang, Q. (2000). A unified framework for semantics and feature based relevance feedback in image retrieval systems. In _Proceedings of the eighth ACM international conference on Multimedia 2000, Marina del Rey, California, United States._ (pp. 31-37). New York, NY: ACM Press.
*   <a name="McAlpine" id="McAlpine"></a>McAlpine, R. (2005). [_Writing ALT-text for images_](http://www.webpagecontent.com/arc_archive/66/5/). Retrieved 26 August, 2005 from http://www.webpagecontent.com/arc_archive/66/5/.
*   <a name="Mukherjea" id="Mukherjea"></a>Mukherjea, S., Hirata, K., & Hara, Y. (1999). AMORE: a World Wide Web image retrieval engine. _World Wide Web_, **2**(3), 115-132.
*   <a name="Munson" id="Munson"></a>Munson, E.V., & Tsymbalenko, Y. (2001). [To search for images on the Web, look at the text, then look at the images](http://www.csc.liv.ac.uk/~wda2001/Papers/25_munson_wda2001.pdf). In _Proceedings of the First International Workshop on Web Document Analysis (WDA2001) Seattle, Washington, USA September 8, 2001_. Retrieved 26 August, 2005 from http://www.csc.liv.ac.uk/~wda2001/Papers/25_munson_wda2001.pdf.
*   <a name="Paek" id="Paek"></a>Paek, S., & Smith, J.R. (2003). [Detecting image purpose in World-Wide Web documents](http://www.it.kmutt.ac.th/CS_LectureNote/CSC496/2003/Paper2.pdf). In _Proceedings of the IS&T/SPIE Symposium on Electronic Imaging: Science and Technology—Document Recognition, San Jose, CA, Jan. 1998_. Retrieved 26 August, 2005 from http://www.it.kmutt.ac.th/CS_LectureNote/CSC496/2003/Paper2.pdf.
*   <a name="Pilgrim" id="Pilgrim"></a>Pilgrim, M. (2002). [_Day 23: Providing text equivalents for images - dive into accessibility_](http://diveintoaccessibility.org/day_23_providing_text_equivalents_for_images.html). Retrieved 26 August, 2005 from http://diveintoaccessibility.org/day_23_providing_text_equivalents_for_images.html.
*   <a name="SecuritySpace" id="SecuritySpace"></a>Security Space. (2005). [_Technology penetration report._](http://www.securityspace.com/s_survey/data/man.200504/techpen.html). Retrieved 26 August, 2005 from http://www.securityspace.com/s_survey/data/man.200504/techpen.html.
*   <a name="Shen" id="Shen"></a>Shen, H.T., Ooi, B.C., & Tan, K.-L. (2000). Finding semantically related images in the WWW. In _Proceedings of the eighth ACM international conference on Multimedia 2000, Marina del Rey, California, United States._ (pp. 491-492). New York, NY: ACM Press.
*   <a name="Slatin" id="Slatin"></a>Slatin, J.M. (2001). The art of ALT: toward a more accessible Web. _Computers and Composition_, **18**(1), 73-81.
*   <a name="Smith" id="Smith"></a>Smith, J.R., & Chang, S.F. (1997). Visually searching the Web for content. _IEEE Multimedia_, **4**(3), 12-20.
*   <a name="Tobias" id="Tobias"></a>Tobias, D.R. (2004). [ALT Text](http://webtips.dan.info/images.html#ALT). _Dan's Web tips: images_. Retrieved 26 August, 2005 from http://webtips.dan.info/images.html#ALT.
*   <a name="Turner" id="Turner"></a>Turner, T.P., & Brackbill, L. (1998). Rising to the top: evaluating the use of the HTML meta tag to improve retrieval of World Wide Web documents through Internet search engines. _Library Resources and Technical Services_, **42**(4), 258-271.
*   <a name="USAccessBoard" id="USAccessBoard"></a>U.S. Access Board (2004). [_Web-based Intranet and Internet information and applications (1194.22): (a) A text equivalent for every non-text element shall be provided (e.g., via 'alt', 'longdesc', or in element content)_](http://www.access-board.gov/sec508/guide/1194.22.htm#(a)). . Retrieved 26 August, 2005 from http://www.access-board.gov/sec508/guide/1194.22.htm#(a).
*   <a name="W3C1999a" id="W3C1999a"></a>W3C (1999a). [_HTML 4.01 specification: 13.8 How to specify alternate text_](http://www.w3.org/TR/html4/struct/objects.html#h-13.8). Retrieved 26 August, 2005 from http://www.w3.org/TR/html4/struct/objects.html#h-13.8\.
*   <a name="W3C1999b" id="W3C1999b"></a>W3C (1999b). [HTML 4.01 specification: 6.2 SGML basic types](http://www.w3.org/TR/html4/types.html#type-cdata). Retrieved 26 August, 2005 from http://www.w3.org/TR/html4/types.html#type-cdata.
*   <a name="W3C1999c" id="W3C1999c"></a>W3C (1999c). [_Web content accessibility guidelines 1.0_](http://www.w3.org/TR/WAI-WEBCONTENT/). Retrieved 26 August, 2005 from http://www.w3.org/TR/WAI-WEBCONTENT/.
*   <a name="Wall" id="Wall"></a>Wall, A. (2004). [_Image ALT tags (IMG ALT)_](http://www.search-marketing.info/organic-listings/img-alt.htm). Retrieved 26 August, 2005 from http://www.search-marketing.info/organic-listings/img-alt.htm.
*   <a name="Watchfire" id="Watchfire"></a>Watchfire (2005). [_Provide alternative text for all images_](http://webxact.watchfire.com/themes/standard-en-us/help/HIDD_WDContent_G9.html). Retrieved 26 August, 2005 from http://webxact.watchfire.com/themes/standard-en-us/help/HIDD_WDContent_G9.html.
*   <a name="WebAIM" id="WebAIM"></a>WebAIM (2005). [_Creating accessible images. Part 5: Effective Alt text_](http://www.webaim.org/techniques/images/5). Retrieved 26 August, 2005 from http://www.webaim.org/techniques/images/5.
*   <a name="Wheatley" id="Wheatley"></a>Wheatley, A., & Armstrong, C.J. (1997). Metadata, recall, and abstracts: can abstracts ever be reliable indicators of document value? _Aslib Proceedings_, **49**(8), 206-21.
*   <a name="Winters" id="Winters"></a>Winters, B. (2005). [_How to create 'doorway' pages to increase your traffic_](http://www.creationsmedimage.com/imageexport/articles/How%20to%20create.htm). _Wordtracker articles_. Retrieved 26 August, 2005 from http://www.wordtracker.com/articles/doorway_pages.html?sid=d8306a86ea4fec47a0bfa07f9ec32be5.
*   <a name="Yang" id="Yang"></a>Yang, H.-C., & Lee, C.-H. (2003). Mining environmental texts of images in Web pages for image retrieval. In _Foundations of intelligent systems._ (pp. 334-338). Berlin: Springer. (Lecture notes in computer science, 2871).

