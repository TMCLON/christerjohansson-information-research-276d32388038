####  Vol. 10 No. 3, April 2005



# The case of the news search engine: an exploratory empirical analysis of _Google News_

#### [Sandeep Krishnamurthy](mailto:sandeep@u.washington.edu) and Elaine Taniguchi  
The University of Washington  
Bothell, WA 98011, USA



#### Abstract

> **Introduction.** News search engines crawl the living Web of news sources to collect, group and distribute timely content. They look at fewer sources than traditional search engines and visit these sources more often. News search engines dynamically group content to create a Web page.  
> **Method.** In this paper, we study one news search engine, _Google News_ We analyse and classify the sources used by this engine. We also conducted an analysis of two randomly chosen American states, Washington and Kansas, to ascertain the proportion of newspaper Websites featured on _Google News_.  
> **Results.** We find that _Google News_ is biased towards newspapers in the USA: 73.24% of the sources are American. The top five countries, USA, UK, Canada, Australia and India, account for 91.95% of the sources. The top ten countries account for 94.04% of sources. A total of sixty-five countries contributed 121 sources, which accounted for 2.69% of all sources. '.com' was the most common domain extension with 78.95% of sites using it. Deep linking was used by only 5.46% of sites. Only 41.30% of Washington newspaper Websites and 52.78% of Kansas newspaper Websites were included in _Google News_. This indicates that regional and local news sources may be represented to a lower degree than is widely believed.



## Introduction

The news search engine seeks to replace the human editor with a computer algorithm. These search engines collect, group and present content from news sources on the World Wide Web. Examples of such engines include [_Google News_](http://news.google.com/), [_RocketNews_](http://www.rocketnews.com/search/index.html), [_Yahoo! News_](http://news.yahoo.com/), [_DayPop_](http://www.<em>DayPop</em>.com/), [_AllTheWeb News_](http://www.alltheWeb.com/?avkw=fogg&cat=news&cs=utf-8&q=&_sb_lang=pref) and [_Ananova_](http://www.ananova.com/). Two arguments have been proposed in favour of having such search engines: information processing and potential diversity.

The first argument is that a search engine is able to process a vast quantity of information in comparison to a human editor. The World Wide Web is a vast repository of information and it is not possible even for an expert to be able to pay attention to a wide variety of sources. As the number of sources grows, the potential advantage of using an algorithm as an aggregator grows as well. The founder of _Google News_, Krishna Bharat, explains:

> ...we get 100,000 articles a day. A human editor couldn't read that many. We have people who try to create an aggregate of what's been done in the media on a given topic and they write a report about it. Journalists do that all the time, and they do an extremely good job. But imagine doing that for every story in the world, every time. We want to give you speed in addition to timeliness. ([Kramer, 2003](#Kramer))

The second argument in favor of news search engines is that they could potentially provide access to more diverse opinions. Once again, the words of the founder of _Google News_ are instructive:

> I want this to be a force for a democracy. I want us to be an honest broker, and I want newspapers featured on our site to get traffic from us. There's never been a more controversial time on the planet. I think it's great to be a news source at this point because there's so much hunger for news. You see a lot more diversity in the news coverage on our site than on others. I think the diversity is a mirror to the diversity of opinion there is worldwide. One of the things that makes us objective is we show all points of view. Even if you disagree with one, we give you both -- the majority and the minority point of view. The ones you don't agree with are education. It's nice to know what the other side is thinking. You'll see left-leaning ones as much as much as you see right-leaning ones. Frankly, the software doesn't know the difference between left and right, which is good.([Kramer 2003](#Kramer))

Our interest here is in the second argument. Clearly, the value of the news search engine as an intermediary in the content distribution process hinges on the diversity of the content. If the content is diverse, the news search engine is perceived as a legitimate aggregator. If the content is not diverse, the results will appear biased to an interested reader leading to an erosion of credibility. In our view, the diversity of sources directly correlates with diversity of content. Imagine a news search engine that aggregates information from all news sources. Such an engine could potentially become the broker that Bharat envisions. However, if a news search engine simply focuses on a bounded subset of sources(e.g. only college newspapers), the news is likely to be skewed.

Two recent papers, [Gerhart(2003)](#Gerhart) and <a ref="#Hindman">Hindman, _et al._ (2003)</a>, have argued that search engines may _<u>reduce</u>_ diversity. Gerhart demonstrates that for controversial topics, search engines are likely to present 'the sunny side' more often, thus, potentially suppressing controversy. Views that not part of the mainstream are not well represented. Hindman, _et al._ argue that, while all Web pages are potentially retrievable, only a few well-linked sites are visible when a user queries a search engine. As a result, they expect that search engines will aid in the creation of a winner-take-all traffic structure with a few sites dominating. This is consistent with the work of Huberman and colleagues; see, for example, Adamic and Huberman ([2000](#AdamicH)). These papers have already drawn some criticism for over-stating the case for diversity and monopoly power. For instance, Brooks ([2004](#Brooks2004)) has argued that these papers, '_expect Google to be something other than Google_'. While acknowledging this criticism, it is our position that as information brokers become more pervasive, the mechanism they adopt to generate content deserves academic scrutiny.

Therefore, our goal in this paper is to examine the extent of diversity among the sources used by one news search engine: News.google.com. Google closely guards its list of 4,500 sources for business reasons. Our request for the list of sources was politely declined. Therefore, in this paper, we manually identify, classify and analyse these sources.

Exploratory findings are presented. While at least ninety-three countries are represented in _Google News_, the content is highly US-centred: 73.24% of the sources were American sites. Moreover, sources from a few countries dominate. Sites from five countries: USA, UK, Canada, Australia and India, make up 91.95% of the sources. The vast majority of sources (74.39%) had a .com extension. Moreover, local newspapers are not as well represented as may have been previously thought; only 41.30% of newspaper Websites in Washington state and 52.78% of newspaper Websites in Kansas were represented on _Google News_.

## Understanding news search engines

News search engines conduct four types of activities: crawling, indexing, grouping and distribution. The first two steps are similar to other search engines. News search engines crawl several sites to collect information. This information is then added to an index.

News search engines excel at grouping of information. The information in the index is re-organized into sub-categories such as World, Business, Technology and Sports and placed on a Website. _DayPop_ places news information into the categories, Top News, Word Bursts (stories are grouped by key words in this section) and News Bursts (stories are grouped by story words in this section).

The distribution of the information from the news search engine to the consumer takes place through many channels. Users could visit the Website of the news search engine and peruse it just like any other news Website. They could also search the index for stories, of course. News search engines do not cache content and typically store content for a short period (e.g., _Google News_ retains stories that are thirty days old or less). Alternatively, users could sign up for e-mail alerts in specific categories. For instance, a user could choose to follow all stories that mention the words 'Tiger Woods'. The search engine would then send them an e-mail when there is a new story that mentions these words. News search engines are different from traditional search engines in the following ways:

*   Such engines scan a limited number of sources. As an example, _News.google.com_ scans 4,500 sources while _Google.com_ indexes over four billion pages. At the time of writing, _DayPop_ seems to look at the largest number of sources with 59,000, including Weblogs, however. _DayPop_ has coined the term _the living Web_ to describe this subset of the Web; i.e., the portion that is updated once or more a day.
*   News search engines scan their sources multiple times a day in contrast to search engines who may visit a page as infrequently as once a month. The lead story on _news.google.com_ changes every fifteen minutes([Kramer 2003](#Kramer)). __DayPop__ crawls major news sites such as CNN once every three hours and the minor sites once every twenty-four hours ([DayPop 2004](#<DayPop)). As a result, news search engines are excellent ways of searching for information about current events ([Sullivan 2003](#Sullivan)).
*   Unlike traditional search engines, news search engines are not simple aggregators of information. They add value by grouping information on a much higher scale. The grouping process is closely analogous to the editorial process. These processes try to emulate the rules a human editor may use. The grouping algorithm decides which story deserves to be on the front page at any given time. .

## Our focus

For the purpose of this paper, we focus on _Google News_, the news search engine of _Google.com_. This service scans about 4,500 news sources regularly to gather and organize content. We chose to study this news search engine for the following reasons:

*   The place of Google in our culture is on the ascendancy. [Googling](http://www.wordspy.com/words/google.asp) has become a verb. Wired magazine recently published an [entire issue on Googlemania](http://wired.com/wired/archive/12.03/google.html). A [parody of News.Google.com](http://www.davidmccandless.com/funny/goodle.htm) now exists.
*   Other news search engines scan a limited number of sources while News.google.com has a sufficiently large number. For instance, _Yahoo! News_ uses ten sources: AP, Reuters, Agence France Presse (AFP), washingtonpost.com, USATODAY.com, Los Angeles Times, Chicago Tribune, U.S. News & World Report, National Public Radio(NPR) and Reuters Features. _AltaVista News_ places a high degree of emphasis on NYTimes.com.
*   _Google News_ is an award-winning Website. It won the 2003 [Webby award](http://www.webbyawards.com/) in the news category.
*   _Google News_ is a very popular site. In August 2004, it attracted 5.8 million visitors placing it at number 14 in the list of most popular sites on the Web for current events and global news ([Lasica 2004](#Lasica)).
*   News.google.com groups stories based on the content and also places them in categories such as World, Sports and Technology. Moreover, it decides on the relative placement of stories on the Website.
*   The increased interest in Google among scholars, e.g., [Brooks (2004)](#Brooks2004), [Galitsky and Levine (2004)](#Galitsky), [Gerhart (2003)](#Gerhart) and [Hindman, _et al._ (2003)](#Hindman), allows us to place our work in context.

## _Google News_: a case study

At first glance, news.google.com, the Website of _Google News_, appears to be just another news site. In actuality, it is a complicated technological endeavor that seeks to simulate a news Website by gathering information from 4,500 news sources.

The _Google News_ Website describes itself as follows:

> _Google News_ presents information culled from approximately 4,500 news sources worldwide and automatically arranged to present the most relevant news first. Topics are updated continuously throughout the day, so you will see new stories each time you check the page. Google has developed an automated grouping process for _Google News_ that pulls together related headlines and photos from thousands of sources worldwide—enabling you to see how different news organizations are reporting the same story. ([_Google News_, 2004](#Google))

How does a news source make it to _Google News_? First, a team of reviewers decides which site to crawl([Kramer 2003](#Kramer)). Second, sites are able to opt-out of this process. This process requires specific language in a file titled robots.txt. Google will respect the specific meta-tag in this file and not crawl anybody who does not wish to be crawled. As the founder of _Google News_ put it:

> We are only able to crawl sites that allow us to crawl. Any news search that tries to link you to new content is going to come up against a barrier—either they specify that robots are not allowed to access this site, or they put the content behind registration that the machine cannot get by. This is a fundamental issue. It has to do with how people monetize their content. The news community needs to figure out how they're going to get traffic from us. The _New York Times_ has a nice solution. They allow us to connect to the content and send traffic to one page. If people want to browse beyond that then they have to register. If people are really happy with the content they'll register. I think that's a great model. ([Kramer 2003](#Kramer))

It may seem strange that publishers are willing and eager to have __Google News__ crawl their Websites and collect data several times a day. In contrast to Google.com, at this time, _Google News_ does not cache stories. Users are directed to the original Website. Thus, _Google News_ directly contributes to the traffic of sites making it an attractive proposition for publishers. Therefore, publishers view the site as beneficial since it increases traffic to their sites.

In addition to the main site, _Google News_ runs five country editions for Australia, Canada, France, Germany, India, Italy, New Zealand, Spain, United Kingdom and United States. _Google News_ is multi-lingual, the France, Spain, Germany and Italy editions are in French, Spanish, German and Italian respectively. Interestingly, the front page of each edition does not focus on stories exclusively from that country. Rather, it is a mix of sources.

## Method

As indicated earlier, Google closely guards its list of news sources for business reasons. Therefore, to gain access to the list of sources, and identified the name and Website of the sources. Data collection started on July 1, 2003 and ended on September 21, 2003\. All information was entered into a spreadsheet. As new names were added, we took care to make sure that there was no duplication. As a result of this process, we were able to create a spreadsheet with 4,499 sources. This formed the basis of our analysis.

## Results

### Country-level analysis

Table 1 provides the number of sources classified by country. The USA tops the list with 73.24% of the sources. The top 5 countries, USA, UK, Canada, Australia and India, account for 91.95% of the sources. The top 10 countries account for 94.04% of sources. The top 28 countries (each of these countries had at least five sources) account for 96.78% of sources. A total of 65 countries contribute 121 sources which account for 2.69% of all sources.

<div align="center">![](p233tab1.jpg)</div>

<div align="center">  
**Table 1: Number of sources, by country**</div>

This clearly demonstrates the highly concentrated nature of the distribution of sources across countries. To examine this further, we mapped the distribution of sources across countries on a log-log scale after sorting them on the number of sources ([Adamic 2000](#Adamic2000)). If the distribution follows the power-law distribution, the expected result will be straight line on this chart (a chart without the log transformation leads to a L-shaped result). The results are shown in Figure 1\. This is a typical power-law distribution.

<div align="center">![fig1](p233fig1.jpg)</div>

<div align="center">  
**Figure 1: Power-law distribution of sources, by country**</div>

We also classified sources by geographical region, with the result shown in Table 2\. North America has a clear lead over other regions. North America and Europe jointly account for 90.62% of all sources.

![](p233tab2.jpg)

**Table 2: Number of sources, by region**

### Domain-level analysis

Table 3 provides an analysis of the domain extensions of the news sources used on _Google News_. '.com' was the most common domain extension with 74.39%. We have used the convention '.com/' to indicate deep linking. If this is added, the popularity of '.com' rises to 78.95%. Country-specific domains such as '.co.uk', 'co.au' and 'co.za' were also popular.

![](p233tab3.jpg)

**Table 3: Summary of domain extensions**

Finally, we look at the deep linking practices of _Google News_ in Table 4\. A total of 244 news sources or 5.44% were deep-linked and '.com/' was the most common deep-linked domain with 4.56%.

![](p233tab5.jpg)

**Table 4: Overview of deep linking practices**

### State newspaper analysis

To understand the proportion of the news universe captured by _Google News_, we procured a list of regional and local newspapers Washington State. This list was obtained from the [Newspaper Association of America](http://www.naa.org/)'s Website. A total of forty-six newspapers was listed for [Washington State](http://www.newspaperlinks.com/newspaperlist.cfm?sid=wa). Every newspaper in this list had a Website and, therefore, was a potential candidate for _Google News_.

The results of our analysis is shown in Table 5\. Only 41.30% of newspapers was listed on _Google News_. This was a surprise to us since we expected almost the entire list of newspapers to be represented.

![](p233tab6.jpg)

**Table 5: Washington State Newspapers**

We found that 52.78% of newspapers was included. Data for this are shown in Table 6\.

![](p233tab7.jpg)

**Table 6: Kansas state newspapers**

## Conclusion

In this paper, we present an empirical analysis of a news search engine, _Google News_. Our results show that, while there is some evidence for diversity among news sources, _Google News_ is US-centred. Most of the sources have a '.com' extension. To our surprise, we found that only 41.30% of Washington and 52.78% of Kansas newspaper Websites were represented.

As news search engines become more popular, their claims of diversity and objectivity deserve careful scrutiny. Our work suggests that _Google News_ may not be as diverse as previously thought. _Google News_ is sure to expand its list of sources as it grows. Future research must examine how content is grouped and the impact of grouping algorithms on diversity.

Some readers may look at our findings and conclude that _Google News_ is as diverse as it should be. Is it reasonable to expect a news search engine to capture the universe of sources for a defined set (e.g., all local newspaper Websites in the US)? Perhaps there is a minimum level of diversity one would expect from an impartial broker.

Much is unknown about how exactly Google groups content on _Google News_. Therefore, simply making it to the list of 4,500 sources will not be adequate to shine.

## Acknowledgements

The author wishes to thank his student, Karen Tellevik, for her contributions, the suggestions of the anonymous referees.

## References

*   <a name="Adamic" id="Adamic"></a>Adamic, L.(2000). [_Zipf, power-laws, and Pareto-a ranking tutorial._](http://www.hpl.hp.com/shl/papers/ranking/ranking.html) Retrieved 18 March, 2004 from http://www.hpl.hp.com/shl/papers/ranking/ranking.html.
*   <a name="AdamicH" id="AdamicH"></a>Adamic, L. & Huberman, B. (2000), The nature of markets in the World Wide Web. _Quarterly Journal of Electronic Commerce_, **1**(1), 5-12\.
*   <a name="Brooks2003" id="Brooks2003"></a>Brooks, T.A. (2003). [Web search: how the Web has changed information retrieval.](http://informationr.net/ir/8-3/paper154.html) _Information Research_, **8**(3), paper 154\. Retrieved 18 March, 2004 from http://informationr.net/ir/8-3/paper154.html.
*   <a name="Brooks2004" id="Brooks2004"></a>Brooks, T.A. (2004), [The nature of meaning in the age of Google.](http://informationr.net/ir/9-3/paper180.html) _Information Research_, **9**(3), paper 180\. Retrieved 18th April, 2005 from http://informationr.net/ir/9-3/paper180.html
*   <a name="<em>DayPop</em>" id="<em>DayPop</em>"></a>_DayPop_ (2004). [_DayPop technology in detail_](http://www.<em>DayPop</em>.com/info/technology.htm). Retrieved March 18, 2004 from http://www.DayPop.com/info/technology.htm
*   <a name="Galitsky" id="Galitsky"></a>Galitsky, B. & Levene, M. (2004). [On the economy of Web links: simulating the exchange process](http://www.firstmonday.org/issues/issue9_1/galitsky/index.html). _First Monday_, **9**(1). Retrieved 18 March, 2004 from http://firstmonday.org/issues/issue9_1/galitsky/index.html.
*   <a name="Gerhart" id="Gerhart"></a>Gerhart, S.L. (2004). [Do Web search engines suppress controversy?](http://firstmonday.org/issues/issue9_1/gerhart/index.html) _First Monday_, **9**(1). Retrieved 18 March, 2004 from http://firstmonday.org/issues/issue9_1/gerhart/index.html.
*   <a name="Glaser" id="Glaser"></a>Glaser, M. (2003, September 3). [_Google News_ finally makes the grade](http://www.ojr.org/ojr/glaser/1062114819.php), _Online Journalism Review_. Retrieved 18 March, 2004 from http://www.ojr.org/ojr/glaser/1062114819.php.
*   <a name="Google" id="Google"></a>_Google News_ (2004). [_A novel approach to news_](http://news.google.com/intl/en_us/about_google_news.html). Retrieved 18 March, 2004 from http://news.google.com/intl/en_us/about_google_news.html.
*   <a name="Hindman" id="Hindman"></a>Hindman, M., Tsioutsiouliklis, K. & Johnson, J.A. (2003). ['Googlearchy': how a few heavily-linked sites dominate politics on the Web](http://www.princeton.edu/~mhindman/googlearchy--hindman.pdf). Paper presented at the Annual Meeting of the Midwest Political Science Association, Chicago, IL., April 4, 2003\. Retrieved March 18, 2004 from http://www.princeton.edu/~mhindman/googlearchy--hindman.pdf.
*   <a name="Kramer" id="Kramer"></a>Kramer, S.D. (2003, September 25). [_Google News_ creator watches portal quiet critics with 'Best News' webby](http://www.ojr.org/ojr/kramer/1064449044.php), _Online Journalism Review_, Retrieved March 18, 2004 from http://www.ojr.org/ojr/kramer/1064449044.php.
*   <a name="Lasica" id="Lasica"></a>Lasica, J.D. (2004, September 24). [Balancing act: how news sites serve up political stories](http://www.ojr.org/ojr/technology/1095977436.php). _Online Journalism Review_. Retreived 11 November, 2004 from http://www.ojr.org/ojr/technology/1095977436.php.
*   <a name="Sullivan" id="Sullivan"></a>Sullivan, D. (2003, September 10). [News search engines](http://searchenginewatch.com/links/article.php/2156261). _Search Engine Watch_. Retrieved March 18, 2004 from http://searchenginewatch.com/links/article.php/2156261.



