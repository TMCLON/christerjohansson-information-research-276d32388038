#### Information Research, Vol. 2 No. 3, December 1996

* * *

# Molecular diversity techniques for chemical databases

#### Peter Willett, Ph.D.  
Department of Information Studies  
University of Sheffield, U.K

<div align="center">**Abstract**</div>

> There is much current interest in computer-based methods for selecting structurally diverse subsets of chemical databases, _e.g._, for inclusion in biological screening programme or for the construction of combinatorial libraries. This paper summarises recent work in Sheffield on _dissimilarity-based compound selection_, which seeks to identify a maximally-dissimilar subset of the molecules in the database. More realistically, this approach seeks to identify a _near_ maximally dissimilar subset, since the identification of the _most_ dissimilar subset requires the use of a combinatorial algorithm that considers all possible subsets of a given dataset.

## Introduction

There is much current interest in computer-based methods for selecting structurally diverse subsets of chemical databases, _e.g._, for inclusion in biological screening programme or for the construction of combinatorial libraries ([Willett, 1987](#wil87); [Martin _et al._, 1995](#mar95); [Shemetulskis _et al._, 1995](#she95)). This paper summarises recent work in Sheffield on _dissimilarity-based compound selection_, which seeks to identify a maximally-dissimilar subset of the molecules in the database ([Bawden, 1993](#baw93); [Lajiness, 1990](#laj90); [Holliday _et al._, 1996](#hol96a); [Holliday & Willett, 1996](#hol96b); [Turner _et al._, 1997](#tur97)). More realistically, this approach seeks to identify a _near_ maximally dissimilar subset, since the identification of the _most_ dissimilar subset requires the use of a combinatorial algorithm that considers all possible subsets of a given dataset. For example, the identification of the maximally-diverse subset of size _n_ molecules from a dataset of size _N_ molecules (where, typically, _n_ << _N_) requires consideration of up to

<div align="center">![](Image39.gif)</div>

possible subsets. Practical considerations hence dictate a simpler form of optimisation such as that illustrated in Figure 1, which is based on work by Bawden ([1993](#baw93)) and by Lajiness ([1990](#laj90)) and which has an expected time complexity of order _O_(_n_�_N_).

The Bawden-Lajiness algorithm is very simple in concept but raises two questions:

*   how does one define the concept of �most dissimilar� in Step 2 of the algorithm?
*   how can it be implemented sufficiently rapidly for use on large datasets?

This paper describes recent work in Sheffield that addresses these two questions ([Holliday _et al._, 1996](#hol96a); [Holliday & Willett, 1996](#hol96b); [Turner _et al._, 1997](#tur97)) .

## Definitions of dissimilarity

As written, Step 2 of Figure 1 is not sufficiently detailed to allow an implementation, in that several different criteria could be used to select since the "most dissimilar" molecule from among the _N-m_ molecules in _Database_ to add to the _m_ molecules that have already been selected for inclusion in _Subset_. This situation is analogous to the selection of a fusion criterion in hierarchical agglomerative clustering methods ([Everitt, 1993](#eve93)), which involves the fusion of those two existing objects, or clusters of objects, that are least dissimilar to each other at each stage in the generation of an hierarchic classification. The various hierarchic agglomerative clustering methods differ only in the precise definition of �least dissimilar� that is used but it is known that they differ substantially in their ability to cluster databases of chemical structures ([Willett, 1987](#wil87); [Brown & Martin, 1996](#bro96)).

<table align="center" bgcolor="#FBFFAA" border="" width="600"><caption align="bottom">**Figure 1** Selection of (near-)maximally dissimilar molecules. The algorithm assumes that molecules are selected from _Database_ (which initially contains _N_ molecules) and placed in _Subset_ (which finally contains _n_ molecules).</caption>

<tbody>

<tr>

<td>

*   1\. Select a molecule at random from _Database_ and place it in _Subset_.
*   2\. Identify that molecule in _Database_ that is most dissimilar to the molecules already in _Subset_ and add that molecule to _Subset_.
*   3\. Repeat Step 2 a total of _n_-2 times.

</td>

</tr>

</tbody>

</table>

Consider the algorithm shown in Figure 1\. Assume that _m_ molecules have already been selected for inclusion in _Subset_ and that we are currently considering the _i_-th of the _N-m_ molecules in _Database_to determine whether it should be added to _Subset_; specifically, we need to calculate the dissimilarity _di,Subset_. Let _dij_ be the dissimilarity between the _i_-th molecule in _Database_ and the _j_-th molecule in _Subset_. Then possible functions from which we can obtain a value for _di,Subset_ include (but are not restricted to) the minimum, the maximum, the median and the sum of the set of _dij_ values, _i.e._, MIN<font face="Symbol">{</font> _dij<font face="Symbol">}</font>_ , MAX<font face="Symbol">{</font> _dij<font face="Symbol">}</font>_ , MED<font face="Symbol">{</font> _dij<font face="Symbol">}</font>_ and SUM<font face="Symbol">{</font> _dij<font face="Symbol">}</font>_ . Once all of the _N-m_ such dissimilarities have been obtained using the chosen function, that molecule is selected for inclusion in _Subset_ that has the largest calculated value for _di,Subset_.

The Bawden-Lajiness algorithm has been implemented using each of the four definitions of dissimilarity given above. To ensure consistency in the results, the same molecule was used on each occasion to provide the initial seed for _Subset_ in Step 1 of the algorithm (rather than selecting a molecule at random); in all of the experiments reported here, the initial molecule was that for which the sum of its dissimilarities to each of the other molecules in _Database_ was a maximum. The experiments reported here (others are discussed by Holliday and Willett ([1996](#hol96b))) used five 1000-compound subsets chosen at random from the Starlist database, which contains the 9518 molecules for which a log _P_oct value has been collected by the Pomona College Medicinal Chemistry Project. Each of the selected molecules was characterised by a 1124-member fragment bit-string, and the dissimilarities between pairs of molecules (one in _Database_ and one in _Subset_) were calculated using the Tanimoto coefficient (Willett, 1987). The resulting values were subtracted from unity to give the _dij_ values that were then used to identify which new molecule should be added to _Subset_ at each stage of the algorithm.

The four dissimilarity definitions were each used to create a subset of _n_ molecules from one of the datasets, and the effectiveness of the definitions were compared by means of the diversity of the subsets resulting from their use. We have quantified the concept of �diversity� in three different ways:

*   Given the inter-molecular dissimilarity matrix for a set of compounds, calculate the sum of the pairwise dissimilarities.
*   Sort the matrix into decreasing dissimilarity order and then take the median dissimilarity.
*   Identify the number of bits that are set in the union of the bit-strings representing the _n_ molecules: the more diverse a set of compounds, the greater the number of bits that are set in the resulting union bit-string.

<table align="center" border="" cellspacing="2" cellpadding="9" width="309" bgcolor="#FBFFAA"><caption align="bottom">Table 1 Sums of dissimilarities for 100-molecule subsets selected from five different files of 1000 Starlist molecules.</caption>

<tbody>

<tr>

<td width="22%" valign="TOP">

Dataset

</td>

<td width="20%" valign="TOP">

MIN

</td>

<td width="20%" valign="TOP">

MAX

</td>

<td width="20%" valign="TOP">

MED

</td>

<td width="20%" valign="TOP">

SUM

</td>

</tr>

<tr>

<td width="22%" valign="TOP">

1

</td>

<td width="20%" valign="TOP">

4398.8

</td>

<td width="20%" valign="TOP">

4249.0

</td>

<td width="20%" valign="TOP">

4424.1

</td>

<td width="20%" valign="TOP">

4540.6

</td>

</tr>

<tr>

<td width="22%" valign="TOP">

2

</td>

<td width="20%" valign="TOP">

4386.4

</td>

<td width="20%" valign="TOP">

4161.7

</td>

<td width="20%" valign="TOP">

4342.1

</td>

<td width="20%" valign="TOP">

4530.5

</td>

</tr>

<tr>

<td width="22%" valign="TOP">

3

</td>

<td width="20%" valign="TOP">

4381.0

</td>

<td width="20%" valign="TOP">

4177.9

</td>

<td width="20%" valign="TOP">

4393.1

</td>

<td width="20%" valign="TOP">

4527.6

</td>

</tr>

<tr>

<td width="22%" valign="TOP">

4

</td>

<td width="20%" valign="TOP">

4396.9

</td>

<td width="20%" valign="TOP">

4068.5

</td>

<td width="20%" valign="TOP">

4438.6

</td>

<td width="20%" valign="TOP">

4533.3

</td>

</tr>

<tr>

<td width="22%" valign="TOP">

5

</td>

<td width="20%" valign="TOP">

4392.3

</td>

<td width="20%" valign="TOP">

4175.0

</td>

<td width="20%" valign="TOP">

4295.1

</td>

<td width="20%" valign="TOP">

4529.1

</td>

</tr>

</tbody>

</table>

Table 1 lists the sums of dissimilarities that were obtained on selecting 100-member subsets from the five different 1000-compound subsets of the Starlist file. The Kendall Coefficient of Concordance, _W_, was used to test whether or not the four definitions could be ranked in a statistically significant order of effectiveness. The value of _W_ expresses the degree of agreement between a set of _k_ judges (in this case the five different datasets) on the ranking of _N_ objects (in this case the four different definitions of dissimilarity), with a value of zero (or unity) indicating complete disagreement (or complete agreement) between the _k_ rankings ([Siegel, 1956](#sie56)). The calculated value for _W_ for the data in Table 1 is 0.904 (_p <font face="Symbol">£</font>_ 0.01). Since a significant measure of agreement has been obtained, it is possible to assign an overall ranking of the definitions in order of decreasing effectiveness ([Siegel, 1956](#sie56)): this order is

SUM <font face="Symbol">></font> MED <font face="Symbol">></font> MIN <font face="Symbol">></font> MAX.

<table align="center" border="" cellspacing="2" cellpadding="9" width="305" bgcolor="#FBFFAA"><caption align="bottom">Table 2 Median values for the _n_(_n_-1)/2 pairwise dissimilarity measures for 100-molecule subsets selected from five different files of 1000 Starlist molecules.</caption>

<tbody>

<tr>

<td width="22%" valign="TOP">

Dataset

</td>

<td width="19%" valign="TOP">

MIN

</td>

<td width="20%" valign="TOP">

MAX

</td>

<td width="20%" valign="TOP">

MED

</td>

<td width="20%" valign="TOP">

SUM

</td>

</tr>

<tr>

<td width="22%" valign="TOP">

1

</td>

<td width="19%" valign="TOP">

0.902

</td>

<td width="20%" valign="TOP">

0.923

</td>

<td width="20%" valign="TOP">

0.957

</td>

<td width="20%" valign="TOP">

0.944

</td>

</tr>

<tr>

<td width="22%" valign="TOP">

2

</td>

<td width="19%" valign="TOP">

0.899

</td>

<td width="20%" valign="TOP">

0.898

</td>

<td width="20%" valign="TOP">

0.957

</td>

<td width="20%" valign="TOP">

0.942

</td>

</tr>

<tr>

<td width="22%" valign="TOP">

3

</td>

<td width="19%" valign="TOP">

0.898

</td>

<td width="20%" valign="TOP">

0.874

</td>

<td width="20%" valign="TOP">

0.952

</td>

<td width="20%" valign="TOP">

0.939

</td>

</tr>

<tr>

<td width="22%" valign="TOP">

4

</td>

<td width="19%" valign="TOP">

0.902

</td>

<td width="20%" valign="TOP">

0.833

</td>

<td width="20%" valign="TOP">

0.952

</td>

<td width="20%" valign="TOP">

0.944

</td>

</tr>

<tr>

<td width="22%" valign="TOP">

5

</td>

<td width="19%" valign="TOP">

0.900

</td>

<td width="20%" valign="TOP">

0.880

</td>

<td width="20%" valign="TOP">

0.953

</td>

<td width="20%" valign="TOP">

0.941

</td>

</tr>

</tbody>

</table>

A different ordering of the four criteria is obtained when the diversity is quantified by means of the median dissimilarity, as shown in Table 2\. Analysis of these values using the Kendall test shows a coefficient of concordance of 0.936 (_p_ <font face="Symbol">£</font> 0.01), this corresponding to the order

MED <font face="Symbol">></font> SUM <font face="Symbol">></font> MIN <font face="Symbol">></font> MAX.

<table align="center" border="" cellspacing="2" cellpadding="9" width="300" bgcolor="#FBFFAA"><caption align="bottom">Table 3 Numbers of non-zero bits for 100-molecule subsets selected from five different files of 1000 Starlist molecules.</caption>

<tbody>

<tr>

<td width="23%" valign="TOP">

Dataset

</td>

<td width="20%" valign="TOP">

MIN

</td>

<td width="20%" valign="TOP">

MAX

</td>

<td width="18%" valign="TOP">

MED

</td>

<td width="19%" valign="TOP">

SUM

</td>

</tr>

<tr>

<td width="23%" valign="TOP">

1

</td>

<td width="20%" valign="TOP">

722

</td>

<td width="20%" valign="TOP">

667

</td>

<td width="18%" valign="TOP">

531

</td>

<td width="19%" valign="TOP">

679

</td>

</tr>

<tr>

<td width="23%" valign="TOP">

2

</td>

<td width="20%" valign="TOP">

729

</td>

<td width="20%" valign="TOP">

704

</td>

<td width="18%" valign="TOP">

570

</td>

<td width="19%" valign="TOP">

703

</td>

</tr>

<tr>

<td width="23%" valign="TOP">

3

</td>

<td width="20%" valign="TOP">

720

</td>

<td width="20%" valign="TOP">

696

</td>

<td width="18%" valign="TOP">

580

</td>

<td width="19%" valign="TOP">

677

</td>

</tr>

<tr>

<td width="23%" valign="TOP">

4

</td>

<td width="20%" valign="TOP">

728

</td>

<td width="20%" valign="TOP">

644

</td>

<td width="18%" valign="TOP">

501

</td>

<td width="19%" valign="TOP">

645

</td>

</tr>

<tr>

<td width="23%" valign="TOP">

5

</td>

<td width="20%" valign="TOP">

735

</td>

<td width="20%" valign="TOP">

678

</td>

<td width="18%" valign="TOP">

421

</td>

<td width="19%" valign="TOP">

663

</td>

</tr>

</tbody>

</table>

Finally, Table 3 lists the numbers of non-zero elements in the union bit-strings. Here, the calculated value for _W_ in the Kendall test is again 0.904 (_p <font face="Symbol">£</font>_ 0.01), this corresponding to the order

MIN <font face="Symbol">></font> MAX <font face="Symbol">></font> SUM <font face="Symbol">></font> MED.

Thus far, we have considered only gross characteristics of the subsets, without any account being taken of their actual compositions. In the final set of experiments, we compared the constituent molecules of the subsets resulting from the use of each of the four definitions of dissimilarity. Molecules which were common to pairs of the subsets, to triples of the subsets, and to all four of the subsets were identified by combining subsets accordingly. An analysis of the resulting common molecules showed clearly ([Holliday & Willett, 1996](#hol96b)) that the four definitions result in very different groups of molecules, even though these subsets may result in a similar level of performance using the various criteria discussed previously

When this work started, our expectation had been that it would serve to identify the best definition of dissimilarity for use in compound selection, in much the same way as previous studies have resulted in unequivocal conclusions as to the relative merits of different hierarchic agglomerative clustering methods for cluster-based compound selection ([Willett, 1987](#wil87); [Brown & Martin, 1996](#bro96)). If this had been the case here, then the three different performance measures we have used might have been expected to yield consistent rankings of the four definitions. However, this is clearly not the case, and we thus conclude that there is no significant difference in the effectiveness of the four definitions, despite the fact that the subsets resulting from the four definitions are markedly different in content. This in turn leads us to conclude that any of the four definitions can be used as the basis for a compound selection programme (although an inspection of the rankings for the three sets of experiments does suggest that the MAX definition is often inferior to the other three definitions).

**<font size="4">

A Fast Algorithm For Dissimilarity-Based Compound Selection

</font>**

We have recently developed a fast implementation of the Bawden-Lajiness algorithm shown in Figure 1, drawing on previous work by Voorhees ([1986](#voo86)) on the implementation of the group-average method for clustering document databases. This clustering method involves the fusion of pairs of clusters of objects on the basis of the average of the inter-object similarities, where one object is in one cluster of the pair and the other object is in the other cluster. Voorhees described an efficient algorithm for the group-average method that is appropriate for all similarity measures where the mean similarity between the objects in two sets is equal to the similarity between the mean objects of each of the two sets. However, the basic idea is applicable to any environment where sums of similarities, rather than the individual similarities, are required, and we have used this characteristic of the approach to provide a fast implementation of dissimilarity-based compound selection when the SUM criterion described above is used.

Let us assume that one wishes to investigate the similarities between each of the molecules in two separate groups, _A_ and _B_. Next, assume that each molecule, _J_, in these groups is represented by a vector in which the _I_-th element, _M_(_J,I_), represents the weight of the _I_-th feature in _M_(_J_), _e.g._, a one or zero denoting the presence or absence of a particular fragment or a numeric value denoting some physical property. Let _AC_ be the linear combination, or _centroid_, of the individual molecule vectors _M_(_J_) (1 <= _J_ <= _N_(_A_)), where _N_(_A_) is the number of molecules in the first group) with _W_(_J_) being the weight of the _J_-th vector in _A_. The _I_-th element of _AC_, _AC(I)_, is thus given by

<div align="center">![](Image40.gif).</div>

The vector _BC_, which denotes the centroid of the second group, is similarly defined in terms of its _N_(_B_) constituent molecules.

Voorhees showed that the dot product of the two centroids is numerically equal to the sum of the of the pairwise similarities when the cosine coefficient ([Willett, 1987](#wil87); [Holliday _et al._, 1996a](#hol96a)) is used as the measure of inter-molecular dissimilarity, _i.e.,_ that

<div align="center">_AC_�_BC_ ![](Image41.gif)</div>

if, and only if, the weights _W_(_J_) are given by

<div align="center">_W(J)_ = ![](Image42.gif)</div>

_i.e.,_ the reciprocal square root of the squared elements of the vector _M_(_J_), and similarly for _W_(_K_)_._ Thus, if this weighting scheme is used, the sum of all of the _N_(_A_)<font face="Symbol">´</font> _N_(_B_) inter-molecular cosine similarities can be obtained by calculating the dot product of the two vector centroids.

It is simple to apply this equivalence to the selection of _n_ compounds from a database, _D,_ using the algorithm shown in Figure 1\. In this case _A_ denotes a single molecule, _J_, from _Database_ and _B_ denotes all of the molecules that have already been selected, _i.e_., _Subset_. It is possible to calculate the sum of the similarities between _J_ and all of the molecules in subset using the equivalence above, which we refer to subsequently as _the centroid algorithm_, by means of just a single similarity calculation (that between _J_ and the centroid of _Subset_), rather than by _m_-1 similarity calculations (between _J_ and each separate molecule in _Subset_). The centroid algorithm thus provides an extremely efficient way of implementing Step 2 of the Bawden-Lajiness algorithm when the SUM definition of dissimilarity is used. Indeed, a complexity analysis of the resulting algorithm shows that it has an expected time complexity of _O_(_nN_), thus enabling dissimilarity-based compound selection to be carried out on very large files of compounds, subject only to:

*   the use of the cosine coefficient for the calculation of the inter-molecular similarities (the appropriateness of this coefficient is discussed in detail by Holliday _et al_. ([1996a](#hol96a))); and
*   the representation of each of the molecules by a vector of attribute values (such as physical properties, chemical fragments or topological indices).

In addition to its use for selecting a diverse subset of an existing database, we have recently applied the centroid algorithm to a related problem, that of selecting a set of external compounds that are as different as possible from an existing database ([Turner _et al._, 1997](#tur97)). The rationale for this work is the interest that exists in techniques that can augment a corporate database by increasing the diversity of the molecules that are available for biological testing. Additional molecules can come from a range of sources, including publicly-available commercial databases, collaborations with academic synthetic groups, combinatorial chemistry and _de novo_ design programmes, folk medicine, specialist synthetic organisations and compound-exchange agreements with other organisations. In what follows, we shall refer to any set of structures that are possible additions to a company�s existing corporate database as an _external dataset_.

Following the previous work on comparing definitions of dissimilarity, we suggest that the diversity, _D(A)_, of a database, _A_, containing _N_(_A)_ molecules, should be defined to be the mean pairwise inter-molecular dissimilarity. This measure of diversity can be calculated very rapidly using a simple modification of the centroid algorithm described above. Specifically, we are interested here in the cosine coefficients, _COS_(_J,K_), for the similarity between all pairs the molecules, _J_ and _K ,_ in _A_ and thus in the vector dot product of the centroid of _A_ with itself_, i.e., DOTPROD_(_A<sub>C</sub>, A<sub>C</sub>_)_._ Writing

<div align="center">![](Image43.gif).</div>

we can hence calculate the sum of all of the pairwise cosine similarities for the molecules in _A_ if the individual molecule vectors are weighted using the reciprocal square-root weighting scheme. The diversity, _D_(_A_), is then obtained by dividing this dot product by _N_(_A_)� to give the mean similarity when averaged over all pairs of the molecules in _A_, and subtracting the result from one, _i.e._,

<div align="center">![](Image44.gif).</div>

The centroid procedure thus provides a very fast way of calculating all of the pairwise similarities between the molecules within a given database and hence of calculating the diversity of that database.

The same approach can also be used to quantify the change in diversity that occurs when an external dataset _X_, containing _N_(_X_) molecules and with a centroid _XC_, is added to an existing database, _A_, to yield a new, merged database, _AX_ containing _N_(_A_)+_N_(_X_) molecules and with a centroid _AXC_. The diversities of _A_, _X_ and _AX_ are

<div align="center">![](Image45.gif), ![](Image46.gif), and ![](Image47.gif),</div>

respectively. The change in diversity of _A_ as a result of adding _X_ , <font face="Symbol">δ</font> (_A_), is hence

<div align="center">![](Image48.gif).</div>

Now

![](Image49.gif). Substituting this value for ![](Image50.gif) into the equation above for <font face="Symbol">δ</font> (_A_), it is possible to calculate the change in diversity that will take place given just a knowledge of the centroids of, and the numbers of molecules in, the external dataset and the original database. This assumes that _A_ and _X_ are disjoint, _i.e._, that they do not have any molecules in common, since this would result in the size of the merged database being less than _N_(_A_)+_N_(_X_), but this is not a problem since duplicate molecules can be identified extremely rapidly by dictionary look-up prior to the calculation of <font face="Symbol">δ</font> (_A_).

If several external datasets, _X1_, _X2_ _etc_. are available, the calculation above can be carried out for each such dataset, thus enabling the identification of that which will best serve to increase the structural diversity of the existing corporate database. The centroid algorithm can hence be used to provide a rapid way of screening several external datasets to identify some small number that can then be analysed by more discriminating measures of diversity that take account of factors such as cost, sample availability and synthetic feasibility ([Turner, _et al._, 1997](#tur97)).

## References

*   <a name="baw93">Bawden, D.</a>(1993) Molecular dissimilarity in chemical information systems. _In_ Warr, W.A. (editor) _Chemical Structures 2_. pp. 383-388\. Heidelberg: Springer Verlag.
*   <a name="bro96">Brown, R.D. & Martin, Y.C.</a>(1996) Use of structure-activity data to compare structure-based clustering methods and descriptors for use in compound selection. _Journal of Chemical Information and Computer Sciences_, **36**,572-584.
*   <a name="eve93">Everitt, B.S.</a>(1993). _Cluster Analysis_, 3rd ed. London: Edward Arnold, .
*   <a name="hol96a">Holliday, J.D., Ranade, S.S. & Willett, P. </a>(1996) A fast algorithm for selecting sets of dissimilar structures from large chemical databases. _Quantitative Structure-Activity Relationships_, **14**, 501-506.
*   <a name="hol96b">Holliday, J.D. & Willett, P. </a>(1996) Definitions of �dissimilarity� for dissimilarity-based compound selection. _Journal of Biomolecular Screening_, **1,** 145-151
*   <a name="laj90">Lajiness, M. </a>(1990) Molecular similarity-based methods for selecting compounds for screening. _In_ Rouvray, D.H. (editor) _Computational Chemical Graph Theory_. pp. 299-316\. New York, NY:: Nova Science Publishers.
*   <a name="mar95">Martin, E.J., Blaney, J.M., Siani, M.A., Spellmeyer, D.C., Wong, A.K. & Moos, W. H.</a>(1995) Measuring diversity: experimental design of combinatorial libraries for drug discovery. _Journal of Medicinal Chemistry_, **38**, 1431-1436.
*   <a name="she95">Shemetulskis, N.E., Dunbar, J.B., Dunbar, B.W., Moreland, D.W. and Humblet, C. </a>(1995) Enhancing the diversity of a corporate database using chemical database clustering and analysis. _Journal of Computer-Aided Molecular Design_, **9**, 1995, 407-416.
*   <a name="sie56">>Siegel, S.</a>(1956) _Nonparametric Statistics for the Behavioural Sciences_. Tokyo: McGraw-Hill.
*   <a name="tur97">Turner, D.B., Tyrrell, S.M. & Willett, P. </a>(1997) Rapid quantification of molecular diversity for selective database acquisition. _Journal of Chemical Information and Computer Sciences_, **37**, 18-22
*   <a name="voo86">Voorhees, E.M.</a> (1986) Implementing agglomerative hierarchic clustering algorithms for use in document retrieval. _Information Processing and Management_, **22**, 465-476.
*   <a name="wil87">Willett, P.</a> (1987) _Similarity and Clustering in Chemical Information Systems._ : Letchworth: Research Studies Press.