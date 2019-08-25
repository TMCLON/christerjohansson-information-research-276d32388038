####  Vol. 11 No. 3, April 2006



# Metodologías para el desarrollo de interfaces visuales de recuperación de información: análisis y comparación

#### [Víctor Herrero-Solana](mailto:victorhs@ugr.es) y [Yusef Hassan](mailto:yusef@nosolousabilidad.com)  
Grupo [SCImago](http://www.scimago.es), Universidad de Granada  
Facultad de Biblioteconomía y Documentación  
Colegio Máximo de Cartuja s.n., 18071 Granada, España.


#### Resumen

> **Introducción**. Con el advenimiento de la web a principios de los años 90, el volumen de información electrónica ha experimentado un crecimiento exponencial sin precedentes. Este fenómeno introdujo muchas ventajas en relación con la posibilidad de intercambio, difusión y transferencia de datos pero, sin embargo, acarreó igualmente muchos problemas en relación con el acceso, búsqueda, localización y recuperación de la información relevante dentro de grandes volúmenes de datos.  
> **Objetivo**. El presente trabajo realiza una revisión exhaustiva de los diferentes modelos, métodos y algoritmos existentes para la generación de Interfaces Visuales de Recuperación de Información (VIRIs, Visual Interfaces for Information Retrieval), clasificados según la etapa del proceso en la que intervienen: análisis y transformación de los datos, aplicación de los algoritmos de clasificación y distribución visual, y aplicación de técnicas de transformación visual.  
> **Metodología**. En base a su análisis, se comparan los diferentes métodos a emplear en cada etapa del proceso de producción, así como se determinan qué combinaciones entre métodos y algoritmos de diferentes etapas resultan más adecuadas.  
> **Resultados**. En la primer sección, análisis y transformación de datos, se analiza la minería de contenidos, de estructura y de uso. En la segunda sección, algoritmos de clasificación y distribución visual, se muestran las representaciones jerárquicas, de redes, de dispersión y mapas. Finalmente, entre las técnicas de transformación visual se presentan las técnicas no orientadas a la distorsión visual y las orientadas a la distorsión (Focus+Context).  
> **Conclusiones**. Los resultados pretenden servir a otros investigadores como herramienta para la elección de una u otra combinación metodológica en el desarrollo de propuestas específicas de VIRIs, además de sugerir implicaciones a tener en cuenta en la necesaria investigación sobre nuevas técnicas de transformación visual.



## Introducción

Con el advenimiento de la World Wide Web a principios de los años 90, el volumen de información electrónica ha experimentado un crecimiento exponencial sin precedentes. Este fenómeno introdujo muchas ventajas en relación con la posibilidad de intercambio, difusión y transferencia de datos pero, sin embargo, acarreó igualmente muchos problemas en relación con el acceso, búsqueda, localización y recuperación de la información relevante dentro de grandes volúmenes de datos.

La investigación en técnicas de recuperación de información ha abordado esta problemática dividiéndola para su estudio en dos grandes estrategias: el _querying_ (interrogación) y el _browsing_ (exploración).

En las estrategias de búsqueda basadas en _querying_ , el usuario introduce una serie de palabras clave que expresen sus necesidades de información, con lo que el sistema tras realizar una equiparación entre consulta y espacio documental, devolverá al usuario una lista de resultados pertinentes para la consulta introducida. Se trata por tanto de una estrategia de búsqueda consciente, que requiere del usuario una formalización previa de sus necesidades de información.

Es los sistemas basados en _querying_ , se debe distinguir entre sistemas de recuperación de datos y recuperación de información ([Rijsbergen](#rijsbergen) 1975). Esta diferenciación está motivada principalmente por la técnica que emplean para la equiparación entre consulta y espacio documental, denominadas equiparación exacta y equiparación parcial respectivamente.

La equiparación exacta es un método determinista de comparación entre consulta y conjunto documental, en el que únicamente se resuelven como resultados válidos aquellos documentos que cumplen completamente con las necesidades expresadas en la consulta. En otras palabras, sólo se devolverían como resultados aquellos documentos donde aparecieran todos y cada uno de los términos introducidos en la consulta, aparición que es contabilizada de forma binaria (presencia o ausencia).

En cambio, la equiparación parcial es un método que posibilita tanto la obtención de resultados parcialmente válidos o pertinentes, como la ordenación de estos resultados en función de su grado de relevancia para la consulta introducida. Para ello, el sistema debería hacer uso de algún modelo que proporcione:

*   Un método para transformar los documentos textuales a representaciones numéricas y computables.
*   Un método que, sobre esta representación de los datos, realice una ponderación automática de los términos que conforman cada documento.
*   Un método de equiparación entre consulta y documento que determine en qué grado el documento es relevante para la consulta, en base al peso de cada uno de los términos en el documento.

Entre los diferentes modelos propuestos que cumplen con estos requisitos podemos señalar: Modelo del espacio vectorial, Modelo probabilístico y Modelo de conjuntos difusos.

De estos modelos, el Modelo del espacio vectorial, originalmente propuesto por Salton ([1989](#salton)), es el que ha tenido un mayor éxito. Como indica Moya-Anegón ([1994](#moya)), el probabilístico tiene unos fundamentos muy similares pero una implementación más compleja, y el de conjuntos difusos aún se encuentra poco desarrollado.

En el Modelo de espacio vectorial, la representación de los datos se obtiene mediante la vectorización del conjunto documental: cada documento _d_ se representa por un vector _V_ de términos _t_, generando una matriz - o espacio - multidimensional con tantas columnas como términos, y filas como documentos.

Partiendo de la premisa de que los términos de un documento representan su contenido ([Luhn](#luhn) 1958), la ponderación de cada uno de sus términos se realiza a través de la función _tf · idf_, donde la frecuencia del término (_tf_ = _term frequency_) determina la capacidad de representación de un término para un documento dado, y la inversa de la frecuencia del término en todo el conjunto documental (_idf_ = _inverse document frequency_) determina su capacidad de discriminación.

Como vemos, este método de ponderación permite detectar los términos más significativos para cada documento, un paso necesario para realizar la indización automática del contenido del documento.

Una vez representado numéricamente el conjunto documental y ponderado de forma automática cada uno de los términos de cada documento, la equiparación parcial se obtiene comparando, mediante el uso de funciones de similaridad, la representación vectorizada de la consulta con las de los documentos.

Las funciones de similaridad, como indica Moya-Anegón ([1994](#moya)), son aportaciones que en el campo de la matemática aplicada se habían hecho anteriormente, y que han sido aplicadas al campo de la recuperación de información. Funciones de similaridad hay muchas, pero las que mejores resultados ofrecen son las que se basan en el producto escalar: la del coseno (también llamada de Salton), la de Dice y la de Jaccard.

Estas funciones, aplicadas sobre dos vectores, devuelven como resultado un valor que indica en qué grado se parecen dichos vectores. Por tanto, al ser aplicadas sobre el vector de la consulta y el de cada uno de los documentos, podemos obtener una medida del grado de relevancia que para esa consulta tienen cada uno de los documentos en un repositorio documental determinado.

Como vemos, la mayor ventaja que implica el empleo de técnicas de equiparación parcial, y por tanto el modelo de espacio vectorial, es que posibilitan la ordenación de los resultados en función del grado de certidumbre de que sean relevantes para las necesidades del usuario. Por el contrario, la equiparación exacta únicamente puede determinar si un resultado es válido para una consulta dada, pero no en qué grado, imposibilitando la ordenación de resultados por relevancia. Como sucedáneo la ordenación podría hacerse, no obstante, en base a atributos menos útiles como podría ser la fecha de creación, nombre del autor, etc.

Aunque el _querying_ es la estrategia de acceso a la información actualmente más extendida en la Web y más estudiada en la literatura científica, no siempre resulta suficiente para satisfacer las necesidades del usuario. Cuando el usuario no tiene completamente claro qué está buscando o cuando es incapaz o tiene dificultades para formalizar sus necesidades de información a través del lenguaje de consulta, se requiere de un modelo alternativo o complementario que posibilite al usuario otra vía de acceso a la información.

En la estrategia de búsqueda por _bowsing_ , en oposición al _querying_ , el usuario explora o inspecciona el conjunto documental, sin necesidad de tener que expresar de forma previa cuáles son sus necesidades de información. Esta es una estrategia que usamos en numerosas situaciones de nuestra vida cotidiana (como cuando exploramos las estanterías de una biblioteca o librería en busca de un libro), pero si nos circunscribimos al medio digital, el mejor ejemplo de búsqueda por browsing es la actividad de navegación hipertextual, donde el usuario explora visual y 'espacialmente' el conjunto hiperdocumental con el objetivo de encontrar o localizar información de su interés.

Entre los sistemas de recuperación de información que ofrecen la posibilidad de búsqueda por _browsing_ , cabe destacar aquellos que proveen de un medio específico para realizar _browsing_ gráfico, en forma de representaciones visuales e interactivas resultado de la abstracción gráfica del conjunto documental.

En la tipología de estas representaciones gráficas o visuales, una primera diferenciación que podemos realizar tiene como base el método utilizado para generarlas, distinguiendo así entre representaciones basadas en técnicas artesanales o manuales, y las basadas en técnicas automáticas. Las primeras presentan varios problemas, ya que no reflejan la estructura real de los datos a representar sino una visión subjetiva que de éstos tiene una determinada persona o grupo de personas. Además, presentan problemas relacionados con su escalabilidad y coste de realización. Por estas razones, en este trabajo solo se tendrán en cuenta aquellas generadas de forma automática.

Una de las áreas de investigación más prometedoras basadas en este modelo de _browsing_ gráfico es aquella representada por los estudios en Visualización de Información o Visualización Científica, distinción terminológica condicionada a la naturaleza de los datos a representar ([Polanco & Zartl](#polanco) 2002), más concretamente los estudios enfocados al diseño de Interfaces Visuales para la recuperación de información o VIRIs (Visual Interfaces for Information Retrieval).

El concepto de visualización, según el diccionario de la [Real Academia de la Lengua](http://www.rae.es/), hace referencia a la acción y efecto tanto de formar en la mente una imagen visual de un concepto abstracto, como de representar mediante imágenes ópticas fenómenos de otro carácter. Aplicado al contexto de la Visualización de Información (VI), el término describiría tanto el hecho de generar una representación visual de un conjunto complejo de datos, como el fenómeno de percepción y comprensión de dicha representación por el usuario final. En palabras de Dürsteler ([2002](#Dursteler)), la VI es un _proceso de interiorización del conocimiento mediante la percepción de información, construcción mental que va más allá de la simple percepción sensorial_.

Una definición de VI aplicada al diseño de 'Visual Interfaces for Information Retrieval' nos la ofrece Eick ([2001](#eick)), al afirmar que la es 'el área de investigación enfocada a la creación de interfaces visualmente ricas para ayudar al usuario a comprender y navegar a través de espacios de información complejos'.

En base a esta definición podemos distinguir claramente dos funciones de cualquier VIRI:

*   Ayudar al usuario a comprender, proporcionándole una 'gran imagen general' de todo el conjunto documental.
*   Ayudar al usuario a navegar, posibilitándole localizar y recuperar aquellos documentos que satisfagan sus necesidades de información a través de la exploración visual y la interacción con la interfaz.

Aunque el _browsing_ como estrategia de acceso a la información presenta algunos inconvenientes, entre otros la posibilidad de ocasionar en el usuario distracción respecto a su objetivo inicial ([Marchionini 1995](#marchionini)), como indica Herrero-Solana ([2000](#herrero)) los sistemas basados en _browsing_ no parecen ser sustituibles por otro tipo de técnicas basadas en el _querying_ .

Esto es debido a que, al mismo tiempo, presentan ventajas para la recuperación de información exclusivas en estas interfaces ([Lin 1997](#lin)):

*   La posibilidad de representar una gran cantidad de información en un espacio (visual) limitado
*   La capacidad de revelar relaciones semánticas entre documentos y términos
*   La facilitación de la exploración visual y la inferencia perceptiva de la interfaz

Además de estas ventajas, como sugiere Marcos-Mora ([2004](#marcos)), el browsing resulta cómodo de usar porque es natural y similar a la forma de buscar objetos en el mundo físico, y porque también propicia el hallazgo de información de interés de manera fortuita.

## Objetivos y trabajos relacionados

En el trabajo de Börner, _et al._ ([2003](#borner)), los autores realizan una revisión exhaustiva de las diferentes etapas, técnicas y algoritmos para la producción de 'Visual Interfaces for Information Retrieval', sentando unas bases teóricas y metodológicas de amplia aceptación por parte de la comunidad científica dedicada a la VI. Igualmente, tanto Herrero-Solana ([2000](#herrero)) como Marcos-Mora ([2004](#marcos)) han llevado a cabo revisiones metodológicas similares, realizando un recorrido analítico de los diferentes 'Visual Interfaces for Information Retrieval' propuestos en la literatura científica, así como de las metodologías empleadas para su desarrollo.

El objetivo propuesto en el presente trabajo consiste en indagar en los métodos, técnicas y algoritmos recogidos en la literatura científica para la producción y desarrollo de 'Visual Interfaces for Information Retrieval'. Se pretende, en base a su análisis, comparar las diferentes técnicas a emplear en cada etapa del proceso de producción, así como las combinaciones más adecuadas entre técnicas de diferentes etapas. A diferencia de otros trabajos similares, se indagará más exhaustivamente en las técnicas de transformación y distorsión visual, que hasta la fecha no han recibido la atención que se merecen en la literatura sobre producción de 'Visual Interfaces for Information Retrieval'.

Este trabajo se ha estructurado en tres secciones correspondientes a las tres etapas o fases principales que conforman la mayoría de esquemas metodológicos propuestos para la producción automatizada de 'Visual Interfaces for Information Retrieval' ([Chung, _et al._ 2003](#chung); [Polanco & Zartl 2002](#polanco); [Turetken & Sharda 2003](#turetken) y [Börner _et al._ 2003](#borner)):

*   Análisis y transformación de los datos
*   Aplicación de los algoritmos de clasificación y distribución visual
*   Aplicación de técnicas de transformación visual

## Análisis y transformación de los datos

El primer paso para visualizar espacios complejos de información es la indización automática del conjunto de documentos electrónicos, que al igual que en sistemas basados en _querying_ normalmente se realiza en base al modelo de espacio vectorial originalmente propuesto por Salton ([1989](#salton)) .

Si por un lado el objetivo de este modelo de representación de datos en sistemas basados en _querying_ consiste en posibilitar la equiparación parcial entre consulta y conjunto documental; en los sistemas basados en _browsing_ gráfico el objetivo es posibilitar tanto la clasificación automática del conjunto documental como el descubrimiento de relaciones estructurales subyacentes.

Cuando los documentos electrónicos a indizar contienen información complementaria, como hiperenlaces o etiquetas de marcado que estructuren su contenido, ésta también puede ser vectorizada para su posterior aprovechamiento.

Una vez vectorizado el conjunto documental, sobre este espacio vectorial se pueden llevar a cabo una serie de análisis con el objetivo de descubrir relaciones semánticas entre documentos, así como entre términos. Se obtiene de esta forma una matriz de distancias N x N, siendo N el número de documentos o de términos.

Estas técnicas pueden ser englobadas bajo la categoría de Minería de Datos, que es definido como un proceso de descubrimiento de conocimiento (a priori desconocido) sobre repositorios de datos complejos, mediante la extracción de información 'oculta' y potencialmente útil en forma de patrones globales y relaciones estructurales implícitas entre datos ([Kopanakis & Theodoulidis 2003](#kopanakis)).

Dentro de las técnicas de Minería de Datos encontramos tres tipos distintos: minería de contenido, minería de estructura y minería de uso ([Berendt _et al._ 2002](#berendt); [Baeza-Yates 2004](#baeza)).

### Minería de contenido

Si partimos de la premisa de que los términos de un documento representan su contenido, la co-ocurrencia de un mismo término en dos documentos diferentes establecería una relación semántica entre éstos. Si asumimos este hecho es posible calcular la similaridad entre dos documentos comparando los vectores de cada documento mediante - cómo comentábamos en la introducción - funciones de similaridad. Igualmente es posible calcular la similaridad entre términos, teniendo en cuenta que la aparición de dos términos en un mismo documento implicaría una relación semántica entre éstos.

Para asegurar la fiabilidad y consistencia de la indización automática de textos en lenguaje natural y reducir el número de términos diferentes, antes de contabilizar frecuencias de co-ocurrencia, en muchas ocasiones es prerrequisito llevar a cabo un control terminológico. Entre las técnicas a aplicar podemos señalar:

*   Eliminación sobre el conjunto de términos a indizar de aquellos de uso común, mediante su comparación con una lista de palabras vacías previamente definida.
*   Uso de procedimientos de _stemming_ para reducir el conjunto de términos a indizar a su raiz, eliminando de esta forma también duplicados, variantes de género, número, etc.
*   Eliminación sobre el conjunto de términos a indizar de aquellos con frecuencias muy altas o excesivamente bajas.

### Minería de estructura

La minería de estructura no se refiere a la estructura propia de cada documento de forma aislada, sino a la estructura del espacio documental definida por los hiperenlaces entre sus documentos.

Cuando un documento hipervincula a otro documento, este enlace expresa una relación estructural explícita entre los dos documentos. Pero a través del análisis de estos hiperenlaces, también es posible descubrir estructuras implícitas y subyacentes de relación semántica entre documentos.

Este es el caso del análisis de la _co-sitación,_ término que se refiere a la co-citación aplicada a los hiperenlaces o '_sitas_' entre _web sites._ En este análisis que desde un mismo documento se enlace una pareja de documentos conjuntamente establece una relación semántica entre los documentos _co-sitados_.

<div align="center">![](p258fig1.gif)</div>

<div align="center">  
**Figura 1: Esquema _cositación_ entre documentos**</div>

Igualmente, se podría aplicar el análisis de los enlaces comunes (que en Bibliometría se suele denominar _bibliographic coupling_) para descubrir estructuras de similaridad subyacentes, en el que el hecho de que dos documentos enlacen a un mismo tercer documento establece una relación semántica implícita entre los documentos _sitantes._

<div align="center">![](p258fig2.gif)</div>

<div align="center">  
**Figura 2: Esquema enlaces comunes (_bibliographic coupling_) entre documentos**</div>

### Minería de uso

Cuando el espacio documental se encuentra accesible al público y visitado diariamente, la información recogida por el servidor en forma de ficheros de sesión (_log files_) puede aportarnos información adicional acerca de las relaciones semánticas entre el conjunto de documentos.

Por ejemplo, que un mismo usuario co-visite o co-acceda a dos documentos diferentes, establece una relación semántica entre los documentos, mayor cuanto mayor sea la frecuencia de este patrón de uso. Así mismo se podrían llevar a cabo análisis más complejos, teniendo en cuenta en qué orden secuencial son visitados los documentos.

<div align="center">![](p258fig3.gif)</div>

<div align="center">  
**Figura 3: Esquema co-acceso entre documentos**</div>

Este análisis nos puede ofrecer información imposible de descubrir a través de la minería de contenido y de estructura, ya que dos documentos frecuentemente co-visitados puede que no se enlacen entre ellos, que no _co-siten_ ni sean _co-sitados_, e incluso que no presenten co-ocurrencias de términos con una frecuencia relevante.

### Comparación de los métodos

Los diferentes tipos de análisis indicados nos ofrecen una herramienta para revelar las relaciones semánticas de similaridad entre documentos, incluso entre términos, en base a nuestro espacio documental vectorizado. La información que ofrecen es complementaria, ya que como indicábamos, con un tipo de análisis es posible revelar información semántica que no hubiera podido ser descubierta mediante la única utilización del resto.

Por ello, aunque estos análisis pueden ser utilizados independientemente, su utilización conjunta aumentaría su capacidad para revelar información 'oculta'. En este sentido, Chen ([1997, 1998](#chen)) propone un modelo genérico para estructurar y visualizar espacios de información hipertextuales, denominado GSA (Generalised Similarity Análisis). Este modelo ofrece un esquema metodológico para la extracción de las relaciones semánticas entre documentos en base a tres tipos de medidas de similaridad - enlaces hipertextuales, similaridad de contenido y patrones de uso - unificadas bajo una única función, que el autor denomina de meta-similaridad.

## Aplicación de los algoritmos de clasificación y distribución visual

En su tesis doctoral, Herrero-Solana ([2000](#herrero)) propone una clasificación de los diferentes 'Visual Interfaces for Information Retrieval' en función de la estructura explícita de los datos a representar: jerárquicas, en red, de búsqueda, en líneas de tiempo y multidimensionales.

Cuando el 'Visual Interface for Information Retrieval'destinado a generar utilizará una metáfora visual fiel reflejo de la propia estructura de los datos, no resulta necesaria la aplicación de técnicas de clasificación y distribución visual, ni por tanto el paso metodológico que describimos a continuación.

Únicamente en 'Visual Interfaces for Information Retrieval' basados en estructuras de datos multidimensionales será imprescindible el empleo de éstas técnicas, que de forma automática produzcan una abstracción gráfica resultado de la reducción de este espacio _n_ -dimensional a un número de dimensiones comprensibles y perceptibles por el ojo humano (1D, 2D ó 3D).

En este trabajo la clasificación de los diferentes tipos de técnicas y algoritmos se hará en función de la metáfora visual perseguida, y no de la propia estructura de los datos, ya que se entiende que siempre serán estructuras multidimensionales que necesitan ser reducidas o simplificadas.

Siguiendo el esquema propuesto por Lin ([1997](#lin)), podemos diferenciar entre los siguientes tipos de metáforas visuales: jerárquicas, de redes, de dispersión y mapas.

### Representaciones jerárquicas

Este tipo de representación visual - donde los elementos se presentan en diferentes niveles, ramas o agrupaciones, que descienden de un nodo raíz - es la más común cuando la propia naturaleza del conjunto de datos a visualizar es jerárquica, como por ejemplo en la visualización de estructuras complejas de directorios y ficheros de sistemas informáticos.

En el caso de la visualización de estructuras de datos multidimensionales, donde no están definidas de forma explícita las relaciones jerárquicas entre estos, este tipo de visualización es consecuencia de la aplicación de técnicas de clasificación o agrupación.

Este es el caso de las técnicas estadísticas de _clustering_ o análisis de conglomerados, que a través de un proceso iterativo van agrupando los diferentes elementos en función de su similaridad, así como agrupando los diferentes grupos en ramas o niveles jerárquicos.

Entre las técnicas de _clustering_ podemos diferenciar alrededor de 150 tipos diferentes en base a las reglas de aglomeración utilizadas. Dentro de las reglas de aglomeración más comunes encontramos: encadenamiento simple (_single link_), también denominado método del vecino más cercano; encadenamiento completo (_complete link_), o método del vecino más lejano; encadenamiento promedio; y el método de Ward o método de la suma de cuadrados ([Herrero-Solana 2000](#herrero)).

<div align="center">![](p258fig4.gif)</div>

<div align="center">  
**Figura 4: Dendrograma basado en el método de Ward ([Herrero-Solana, Moya-Anegón](#herrero) 1999)**</div>

El resultado gráfico de la aplicación de estas técnicas suele ser en forma de dendograma como el de la figura 4 (representación que usa la metáfora visual de árbol jerárquico), donde se pueden apreciar visualmente los diferentes grupos y subgrupos generados. Para su uso en la producción de 'Visual Interfaces for Information Retrieval' se podrían representar mediante metáforas jerárquicas alternativas como las jerarquías hiperbólicas ([Lamping, _et al._ 1995](#lamping)), o como los _treemaps_ - representación plana de una jerarquía en un espacio bi-dimensional - ([Shneiderman 1992](#schneiderman); [Kobourov & Yusufov 2005](#kobourov)). Hay que señalar que los _treemaps_ pueden ser considerados una metáfora visual híbrida entre representación jerárquica y mapa.

El mayor problema que presentan las técnicas de _clustering_ es que no posibilitan el etiquetado o rotulado automático de cada uno de los grupos y subgrupos creados, por lo que el usuario sólo podría identificar la clase o grupo a través de la exploración de sus elementos contenidos.

### Representaciones de redes

Las representaciones de redes son aquellas donde los diferentes elementos - documentos, términos... - son presentados en forma de nodos o vértices, mientras que la estructura semántica se encuentra definida por los enlaces o arcos que conectan dichos nodos.

Por ejemplo, en base a una matriz de similaridad N x N (donde N indica el número de documentos), se podría representar cada documento como un nodo, y cada grado de similaridad entre dos documentos como un enlace o arco. El problema de representar estructuras de datos multidimensionales de esta forma es que el número de arcos sería tal que impediría la comprensión del grafo resultante, ya que el número de enlaces salientes por cada nodo podría llegar a ser igual a N-1\.

Por tanto, es necesario el empleo de alguna técnica de 'poda' o reducción de enlaces con el fin de que el grafo resultante sea comprensible y por tanto útil para la visualización, sin perder ni distorsionar en la medida de lo posible la realidad estructural de la red.

Una de estas técnicas de 'poda' es el método de escalamiento de red _Pathfinder_ ([Schvaneveldt 1990](#schvaneveldt)), con el que se obtiene como resultado lo que se denominan redes _Pathfinder_ o PFNETs. Esta técnica se basa en la eliminación de todos aquellos arcos de la red que no cumplan el criterio conocido como la 'condición de la inigualdad del triángulo', es decir, que no formen parte del camino más corto entre cada par de nodos.

La topología de la red resultante de la aplicación del método de _Pathfinder_ estará condicionada por dos parámetros. Por un lado la métrica _r_ de Minkowski, que determina cómo calcular la distancia entre dos nodos no enlazados directamente, parámetro que puede tomar tres valores: cuando r=0 la distancia es igual a la suma de los pesos de los enlaces que conectan los dos nodos; cuando r=1 la distancia es igual a la distancia euclídea entre los dos nodos; cuando r=8 la distancia es igual al mayor de los pesos de aquellos enlaces que conectan dos nodos. Por otro lado el parámetro _q_ indica la longitud máxima (contabilizada en número de enlaces) del camino entre dos nodos en la que no podrá violarse la 'condición de la inigualdad del triángulo'.

Una vez realizada la poda de enlaces, para la representación visual de la red, es necesario aplicar algún algoritmo de posicionamiento de los nodos. Si bien técnicas de reducción de la dimensión como el MDS (de la que hablaremos en el siguiente apartado) podrían ser útiles, tienen el problema de que al no tener en consideración la estructura de enlaces resultado de aplicación del método de _Pathfinder_ , el posicionamiento final de los nodos provocaría cruces entre los enlaces que oscurecerían la visualización del grafo ([Fowler _et al._ 1992](#fowler)).

<div align="center">![](p258fig5.gif)</div>

<div align="center">  
**Figura 5: PFNET de un conjunto documental ([Chen](#chen) 1997)**</div>

Por ello, este posicionamiento de nodos se realiza normalmente mediante algoritmos basados en 'spring models', como el desarrollado por Kamada y Kawai ([1989](#kamada)). Estos algoritmos consideran que los nodos de la red se encuentran conectados por 'muelles virtuales', cuya fuerza es igual a la suma de los enlaces existentes entre los nodos. El algoritmo intenta reducir la tensión global del conjunto de muelles mediante un proceso iterativo de reposicionamiento de los nodos, hasta lograr la posición óptima de todos ellos.

### Representaciones de dispersión

Una forma alternativa de representar visualmente estructuras de datos multidimensionales es en forma de nubes de puntos o nubes de dispersión. Estos puntos - que visualmente no tienen por qué tener dicha forma, ya que podrían ser presentados como iconos o como rótulos de texto - estarían distribuidos en un espacio visual bidimensional o tridimensional, y distanciados unos de otros en función de las disimilaridades o distancias originales especificadas en la matriz de similaridad.

Para poder presentar estas distancias en dimensiones comprensibles por el ser humano, es necesaria la utilización de técnicas de reducción de la dimensión. Este es el caso de la técnica de estadística multivariante denominada Escalamiento Multidimensional o MDS (Multidimensional Scaling).

Este método consiste en un proceso iterativo en el que se van recolocando o re-posicionando los diferentes elementos (documentos, términos, etc.) hasta conseguir que disten entre sí lo más acercadamente a como lo hacen en la matriz original de distancias. Inevitablemente, existe una pérdida de información, mayor cuanta más diferencia exista entre el número de dimensiones del espacio multidimensional original y el número de dimensiones al que pretende ser reducido.

<div align="center">![](p258fig6.gif)</div>

<div align="center">  
**Figura 6: Representación MDS de los grandes grupos temáticos de la CDU ([Moya-Anegón, Herrero-Solana](#moya) 1999).**</div>

Esta pérdida de información o distorsión de las distancias originales entre elementos suele ser medida a través de la métrica de _stress_ propuesta por Kruskal ([1964](#kruskal)) (originalmente el autor la denominó STRESS, acrónimo de _STandardized Residual Error Sum of Squares_). En la aplicación de los algoritmos de MDS, como paso previo, se suele establecer un umbral de _stress_ aceptable, con el objetivo de reducir el tiempo de procesamiento.

### Mapas

Las representaciones visuales basadas en mapas se fundamentan en la idea de utilizar la metáfora de mapa geográfico para la visualización de espacios de información. Por lo general, el objetivo de la utilización de cualquier tipo de metáfora visual en el diseño de interfaces es hacer visible para el usuario la estructura y relaciones en un conjunto determinado datos. Por tanto, la idea de utilizar estas metáforas para la visualización de espacios de información complejos y abstractos parece tener bastante sentido, ya que brindan una visión diferente del conjunto que en la mayoría de los casos enriquecerá la imagen mental previa que el usuario tenga de él.

De entre todas las técnicas posibles para generar este tipo de mapas, resaltamos el modelo de mapas auto-organizativos o SOM (_Self-Organizing Map_) ([Kohonen 1989](#kohonen)) - aplicación de las Redes Neuronales Artificiales (RNA) para la organización y clasificación automática de información.

El funcionamiento de este modelo es sencillo, pues se basa en establecer una correspondencia entre la información de entrada y un espacio de salida de dos dimensiones. De esta manera, los datos de entrada con características comunes activarán zonas próximas del mapa. Este modelo de red se representa con sus neuronas de salida dispuestas de manera bidimensional. Cuando se ingresa un vector de datos a la red, ésta reacciona de forma tal que solo una neurona de la capa de salida resulta activada. A esta neurona se la denomina vencedora (_winner-take-all unit_) y determina un punto en el mapa bidimensional.

<div align="center">![](p258fig7.gif)</div>

<div align="center">  
**Figura 7: WebSOM, análisis de co-ocurrencia de términos sobre grupos de discusión Usenet. Helsinki University of Technology. ([http://websom.hut.fi/websom/](http://websom.hut.fi/websom/))**</div>

Lo que realmente esta haciendo la red es clasificar la información de entrada, ya que la neurona ganadora representa la clase a la que pertenece la entrada, además de que ante entradas similares se activará siempre la misma neurona. Por tanto, la red es válida para establecer relaciones, desconocidas previamente, entre un conjunto determinado de datos.

Como vemos, se trata de un proceso auto-organizativo, donde la clasificación u organización resultante se encuentra condicionada por la propia naturaleza de los datos introducidos.

Un ejemplo de 'Visual Interface for Information Retrieval'con forma de mapa SOM es el que se muestra en la figura 7\. En este, los rótulos o etiquetas describen la temática, y el coloreado representa la densidad documental de la zona del mapa.

### Comparación de los métodos

Los diferentes métodos descritos, clasificados en este trabajo en función del tipo de representación visual resultado de su aplicación, pueden ser considerados complementarios ya que ofrecen diferentes soluciones para un mismo problema ([Herrero-Solana 2000](#herrero)). Aunque con funcionamiento y procedimientos diferentes, todos comparten el objetivo de la reducción de estructuras de datos multidimensionales a formas 'visualizables' en 2 y/o 3 dimensiones.

En cualquier reducción, simplificación o resumen de conjuntos complejos de datos, se produce una pérdida de información respecto a la realidad estructural de los datos originales. Es precisamente en función de aquella información estructural más fielmente preservada, que se fundamenta uno de los criterios a través del cual pueden ser caracterizados y comparados los métodos descritos.

Como afirma Kaski ([1997](#kaski)), tras una exhaustiva comparación entre los métodos de MDS y SOM, mientras que el primero se orienta a la preservación de su estructura a través de las distancias entre elementos, los mapas auto-organizativos intentan preservar su topología o relaciones de vecindad.

Por otro lado, las técnicas de escalamiento _Pathfinder_ generan representaciones en forma de grafos, donde lo que se preserva y enfatiza son las relaciones locales entre elementos, representadas mediante arcos o enlaces entre nodos ([Chen 1998](#chen)).

La información preservada mediante las técnicas de _clustering_ es aquella representada por las relaciones de grupo entre elementos. Aunque se han demostrado muy útiles como técnicas de clasificación y visualización de información, las técnicas de _clustering_ no son tan utilizadas como las anteriores en la producción de interfaces visuales. Esto es debido, en parte, por la imposibilidad para etiquetar o rotular automáticamente cada uno de los grupos y subgrupos creados, por lo que el usuario solo podría identificar la clase o grupo a través de la exploración de sus elementos contenidos, y la metáfora jerárquica perdería utilidad. Por estas razones, las técnicas de _clustering,_ en el contexto de la producción de 'Visual Interfaces for Information Retrieval', son más útiles como complemento al resto (MDS, SOM y _Pathfinder_) que como solución _per se_.

<table width="550" border="1" cellspacing="0" cellpadding="3" style="background-color: #FDFFDD; font-family: Verdana, Geneva, Arial, Helvetica, sans-serif; font-size: smaller; font-style: normal; border: solid;" align="center"><caption align="bottom">  
**Tabla 1**</caption>

<tbody>

<tr>

<th width="150">Técnica</th>

<th width="400">Elementos que preserva de la estructura</th>

</tr>

<tr>

<td width="150">MDS</td>

<td width="400">Distancia entre elementos</td>

</tr>

<tr>

<td width="150">Clustering</td>

<td width="400">Relaciones de agrupación</td>

</tr>

<tr>

<td width="150">Pathfinder</td>

<td width="400">Relaciones locales más fuertes.</td>

</tr>

<tr>

<td width="150">SOM</td>

<td width="400">Relaciones de vecindad.</td>

</tr>

</tbody>

</table>

La preservación de un determinado elemento estructural (y por tanto la pérdida de otra información), condicionará la expresividad de la interfaz resultante, es decir, el grado de fidelidad con el que los datos originales se ven representados por la estructura visual de la interfaz. Al mismo tiempo, la elección de una u otra técnica condicionará la efectividad de la interfaz, la facilidad de interpretación y comprensión de ésta por el usuario.

Existen trabajos que ponderan estas técnicas, como es el caso de la tesis doctoral de Buzydlowski ([2003](#buzydlowski)) donde el autor compara SOM y _Pathfinder_ , pero el grado de expresividad de cada técnica está fuertemente influenciado por la naturaleza de los datos, por lo que no es posible afirmar que ninguna de ellas sea superior en todos los contextos.

En cambio, la efectividad y facilidad de interpretación de la metáfora visual resultante sí puede ser determinada independientemente de la naturaleza de los datos. La metáfora de grafo propia de _Pathfinder_ resulta de mayor familiaridad para el usuario, por lo que es previsible que interfaces creadas con esta técnica resulten más usables que las creadas con MDS o SOM. Las interfaces basadas en MDS y SOM pueden resultar igual de insólitas para el usuario, aunque el orden visual de los elementos en interfaces SOM puede ser una ventaja frente al aparente caos o desorden de elementos en dispersión en interfaces MDS.

La comparación entre estos métodos se puede realizar en base a otras variables igualmente importantes, como: escalabilidad, carga computacional, posibilidad de interpretación de dimensiones, distribución visual (estática o dinámica), y escala (global o local) en la que pueden ser aplicados de forma óptima ([Börner _et al._ 2003](#borner)). Algunas de estas variables son de vital importancia, como es el caso de la carga computacional del algoritmo, lo que suele conllevar descartar algoritmos pesados como MDS cuando la generación de la interfaz se deba producir en tiempo real ([Buzydlowski _et al._](#buzydlowski)).

## Aplicación de las técnicas de transformación visual

Aunque las técnicas de clasificación y distribución visual descritas hasta el momento tienen el objetivo de hacer visible para el usuario el espacio documental en su conjunto, reduciendo todas sus relaciones de similaridad y estructura a un simple 'pantallazo', estas representaciones gráficas no siempre son fáciles de explorar visualmente debido a su tamaño y complejidad, provocando lo que ha venido a denominarse como 'sobrecarga visual'.

En estos casos es necesario proveer a la interfaz de mecanismos dinámicos e interactivos que faciliten su visualización por el usuario y que reduzca esta sobrecarga.

Estas técnicas podemos denominarlas de transformación visual interactiva, y su investigación es anterior a los estudios sobre VI, ya que son necesarias desde el mismo momento en que surge el problema de tener que presentar en una reducida pantalla de ordenador más información de la que puede mostrar de forma simultánea.

Gutwin y Fedak ([2004](#gutwin)) clasifican estos mecanismos en cuatro grupos diferentes: _panning_, _zooming_, múltimes vistas y _focus+context_. Los tres primeros grupos podrían ser considerados como técnicas no orientadas a la distorsión, mientras que el grupo de _focus+context_ englobaría aquellas orientadas a la distorsión visual ([Leung & Apperley 1994](#leung)).

<table width="726" border="1" cellspacing="0" cellpadding="3" style="background-color: #FDFFDD; font-family: Verdana, Geneva, Arial, Helvetica, sans-serif; font-size: smaller; font-style: normal; border: solid;" align="center"><caption align="bottom">  
**Tabla 2**</caption>

<tbody>

<tr>

<th colspan="3">Técnicas de transformación visual interactiva</th>

</tr>

<tr>

<td width="308" rowspan="3">

<div align="right">No orientadas a la distorsión visual -></div>

</td>

<td width="129">

<div align="center">**Panning**</div>

</td>

<td width="257" rowspan="2">

<div align="left"><- Vista parcial</div>

</td>

</tr>

<tr>

<td width="129">

<div align="center">**Zooming**</div>

</td>

</tr>

<tr>

<td width="129">

<div align="center">**Múltiples vistas**</div>

</td>

<td width="257" rowspan="2">

<div align="left"><- Vista detalle + vista global</div>

</td>

</tr>

<tr>

<td width="308">

<div align="right">Orientadas a la distorsión visual -></div>

</td>

<td width="129">

<div align="center">**Focus+Context**</div>

</td>

</tr>

</tbody>

</table>

### Técnicas no orientadas a la distorsión visual

Las técnicas de _panning_ consisten en ofrecer al usuario un mecanismo para paginar o hacer 'scroll' en la interfaz, mientras que las de _zooming_ ofrecen la opción de agrandar o ver en detalle una parte de la interfaz. Estas técnicas, que pueden ser utilizadas conjuntamente, comparten el problema de que por sí solas pueden resultar desorientadoras para el usuario, ya que sólo permiten visualizar simultáneamente una parte de la interfaz sin tener una visión global de ésta ([Storey _et al._ 1999](#storey)).

Una posible solución para este problema es el empleo de técnicas de 'múltiples vistas' o _Detail+Overview_ , que se basan en ofrecer desde la interfaz diferentes vistas de la misma representación visual. Al mismo tiempo se ofrece una visión global de la representación para orientar al usuario, y por otro una vista para su exploración visual en detalle. Igualmente se proporcionan mecanismos interactivos para especificar el nivel de detalle (_zoom_), así como para seleccionar qué parte de la representación se quiere observar en detalle.

Como ejemplo de su aplicación en la producción de 'Visual Interfaces for Information Retrieval', podemos observar su uso para la visualización de representaciones complejas de categorías mediante redes _Pathfinder_ en la figura 8.

<div align="center">![](p258fig8.gif)</div>

<div align="center">  
**Figura 8: Aplicación de la técnica detail+overview en el proyecto [Atlas of Science](http://www.atlasofscience.net) sobre un mapa de categorías temáticas ISI para el dominio geográfico de España**</div>

### Técnicas orientadas a la Distorsión o Focus+Context

Las técnicas _Focus+Context_ pueden ser utilizadas como alternativa a las técnicas _Detail+Overview_ , e incluso, en algunos contextos, como complemento a éstas ([Hayama _et al._ 2003](#hayama)).

La idea consiste en ofrecer al usuario, a través de una única vista, tanto una visión en detalle de la representación visual, como una visión global. Las premisas de las que parte esta técnica son las siguientes ([Polanco & Zartl 2002](#polanco)):

*   El usuario necesita visualizar tanto la información global (contexto) como la información en detalle (el foco de su visualización) de forma simultánea.
*   La información que necesita visualizar en detalle es diferente a la que necesita para contextualizarla.
*   Esos dos tipos de información deben ser combinados en una única vista.

De acuerdo a estas premisas, el funcionamiento de las técnicas de _Focus+Context_ consiste en distorsionar la representación visual, haciendo más visible el foco y minimizando el contexto. Para realizar esta distorsión, las técnicas de _Focus+Context_ pueden hacer uso de dos procedimientos:

*   Filtrado o elisión de información visual: ocultamiento o elisión de aquellas partes de la estructura visual de la representación de menor interés, hasta que necesiten ser visualizadas.
*   Distorsión o deformación de información visual: alteración de las posiciones, formas y tamaños de los elementos visuales.

Aunque variando en las funciones de magnificación que emplean para realizar esta distorsión visual ([Leung & Apperley 1994](#leung)), podemos afirmar que las técnicas _Focus+Context_ conceptualmente tienen en común el efecto visual que persiguen, denominado genéricamente de ojo de pez (_Fisheye_), en el que se magnifica el foco de atención y se minimiza la zona visual contextual o periférica.

 A pesar de que existen propuestas previas conceptualmente similares como la vista bifocal ([Spence & Apperley 1982](#spence)) posteriormente extendida por Mackinlay _et al._ ([1991](#mackinlay)); fue Furnas ([1986](#furnas)) quien formalizó el concepto de ojo de pez como tal, a través de su función de Grado de Interés o DOI (_Degree Of Interest_), que asigna a cada elemento visual un valor que representa el interés del usuario en visualizarlo.

<div align="center">![](p258fig11.gif)</div>

<div align="center">  
**Fórmula 1: Degree Of Interest (DOI)**</div>

DOI(_x_, _y_) es el grado de interés que para el usuario tiene el elemento _x_, cuando el elemento foco que se está visualizando es _y_. API (_x_) es el valor global de la Importancia A Priori (A Priori Importance) que tiene el elemento _x_, y D(_x_, _y_) la distancia existente entre el elemento _x_ y el elemento focal _y_ .

En su trabajo, Furnas aplica dicha función a estructuras textuales jerárquicas, asignando el valor de API en función del nivel jerárquico en el que se encuentre el nodo, y calculando el valor de la distancia en función del camino que habría que recorrer a través del árbol jerárquico para llegar de un nodo a otro. Por tanto, no ofrece ningún modelo matemático para su aplicación en otros contextos, como por ejemplo en las representaciones gráficas.

Existen multitud de aplicaciones basadas en el concepto de ojo de pez, que no sólo difieren en el contexto de aplicación, sino también en la forma y método. De hecho, como afirma Noik ([1993](#noik)), mientras que la propuesta original de Furnas estaba enfocada principalmente a la utilización de procedimientos de filtrado o elisión, muchas de las posteriores aplicaciones están basadas en procedimientos exclusivamente de distorsión o deformación visual.

Algunas de las áreas de aplicación del modelo de ojo de pez han sido: menús de interfaces gráficas de usuario ([Bederson 2000](#bederson)); documentos textuales de estructura jerárquica ([Hayama _et al._ 2003](#hayama)) ([Hornbæk & Frøkjær 2003](#horn)); y jerarquías complejas ([Lamping _et al._ 1995](#lamping)).

En el contexto de las representaciones gráficas, Sarkar y Brown ([1992](#sarkar)) proponen un modelo matemático para la aplicación del efecto de ojo de pez en redes en forma de grafo, introduciendo dos posibles métodos de distorsión visual: por transformación cartesiana y polar. Para su aplicación en grafos, los autores introducen variaciones sobre la función DOI original, midiendo la distancia entre dos nodos D(_x_, _y_) a través del cálculo de la distancia euclídea entre estos dos vértices en la red.

<div align="center">![](p258fig9.gif)</div>

<div align="center">  
**Figura 9: (a) grafo sin distorsión, (b) distorsión cartesiana y (c) distorsión polar ([Sarkar, Brown](#sarkar) 1992)**</div>

Un aspecto importante en la aplicación de estas técnicas de transformación visual en representaciones complejas, es la necesidad de preservación del mapa mental que el usuario adquiere en la visualización previa a la distorsión. Para preservar este mapa mental, una vez que se aplique el efecto de distorsión, el usuario debería poder equiparar mentalmente la representación distorsionada con aquella que visualizaba antes de la distorsión.

Para ello se deberían conservar propiedades del grafo como la dirección de las líneas, la topología, la ortogonalidad y las distancias entre elementos. Lógicamente, preservar todas estas propiedades es imposible desde el momento en que lo que se está realizando es precisamente una distorsión visual. Una posible solución la ofrecen Storey _et al._ ([1997, 1999](#storey)), quienes proponen un algoritmo para la aplicación del efecto ojo de pez en grafos, adaptable según las propiedades del grafo que quieran ser conservadas tras la distorsión, con el objetivo de preservar el mapa mental del usuario.

Más concretamente, en el área de la visualización de información la técnica de ojo de pez ha sido utilizada con éxito en varias propuestas de 'Visual Interfaces for Information Retrieval' ([Fowler _et al._ 1992](#fowler); [Orimo & Koike 1999](#orimo); [Rennison 1994](#rennison); [Chen 1998](#chen); [Turetken & Sharda 2003](#turetken) y [Yang, _et al._ 2003](#yang)).

<div align="center">![](p258fig10.jpg)</div>

<div align="center">  
**Figura 10: mapa SOM (a) con distorsión polar de ojo de pez y (b) con filtrado basado en fractales ([Yang, Chen, Hong](#yang) 2003**)</div>

### Comparación de los métodos

Como ya indicábamos, las técnicas de _panning_ y _zooming_, aunque útiles en ciertos contextos, al no proporcionar una visión global de la representación no resultan del todo apropiadas para representaciones visuales complejas. De hecho, como se demuestra en varios trabajos ([Schaffer _et al._ 1996](#schaffer)) ([North & Shneiderman 2000](#north)) ([Gutwin & Fedak 2004](#gutwin)), las técnicas de _Overview+Detail_ así como _Focus+Context_, presentan una mayor efectividad demostrada en este tipo de interfaces visuales.

Por otro lado, la técnica _Overview+Detail_, aunque es ampliamente utilizada en multitud de contextos, presenta algunos problemas como es la desconexión visual entre la vista en detalle y la vista global ([Parker _et al._ 1998](#parker)) ([Storey _et al._ 1999](#storey)), que pueden ocasionar dificultades para apreciar de forma precisa la relación entre la zona visualizada en detalle y su contexto. Otro problema es que requiere por parte del usuario la integración mental de ambas vistas ([Schaffer 1996](#schaffer); [Yang, _et al._ 2003](#yang)), lo que podría repercutir en una 'sobrecarga cognitiva'. Por estos motivos en determinados contextos la aplicación de técnicas de _panning_ y _zooming_ por sí solas, ofrecen incluso mejores resultados que la de _Overview+Detail_ en cuanto a eficiencia en la consecución de tareas por el usuario ([Hornbæk _et al._ 2002](#horn)).

Aunque en base a esto podríamos concluir que las técnicas _Focus+Context_ serían las más adecuadas para su empleo en 'Visual Interfaces for Information Retrieval' complejos, coincidimos con Storey, _et al._ ([1999](#storey)) cuando afirman que existe una preocupante carencia de estudios de análisis y evaluación que determinen la validez de estas técnicas de distorsión visual de forma empírica.

Una notable excepción es el trabajo de Yang, _et al._ ([2003](#yang)), donde sobre un 'Visual Interface for Information Retrieval'con forma de mapa de categorías y generado mediante el modelo de mapas auto-organizativos (SOM), aplican diferentes técnicas de transformación visual para comparar su rendimiento.

Tras evaluar el 'Visual Interface for Information Retrieval'a través de un test de usuarios, los autores concluyen que tanto la técnica de ojo de pez (basada en procedimientos de distorsión de información visual), como la técnica de fractales ([Koike 1995](#koike)) (basada en procedimientos de filtrado de información visual), incrementan la eficacia en la visualización de grandes mapas de categorías frente a la no utilización de ninguna de ellas. La técnica de filtrado según sus resultados, en este tipo de mapas, parece ofrecer cierta ventaja frente a la de distorsión; mientras que entre los métodos de distorsión aplicables en la técnica de ojo de pez, el método de transformación cartesiana es preferida por los usuarios frente al método de transformación polar.

## Discusión

A lo largo de este trabajo se han descrito, analizado y comparado entre sí las posibles técnicas y métodos a emplear por cada una de las etapas de la producción de un VIRI, pero aún cabe cuestionarse qué posibles combinaciones entre técnicas de diferentes etapas ofrecen resultados más adecuados.

Obviando la etapa de análisis y transformación de los datos, donde concluimos que las diferentes técnicas de minería de datos eran complementarias entre sí e idealmente se debían usar conjuntamente en forma de análisis de meta-similaridad; es necesario determinar la _compatibilidad_ entre las técnicas de la etapa de clasificación y distribución visual y la etapa de transformación visual.

Las técnicas de transformación visual son necesarias cuando la representación gráfica producto de la etapa anterior resultaba compleja y de difícil visualización. Este hecho no sólo depende de la cantidad de datos a resumir y representar en la interfaz, sino también del algoritmo o técnica de clasificación y distribución visual empleados.

Mientras que hay algoritmos de distribución visual que aprovechan de forma óptima el espacio visual de la representación resultante, otros en cambio tienden a desaprovechar y aglomerar los elementos, repercutiendo negativamente en la facilidad de visualización. Este es el caso de la técnica de MDS, en cuyas representaciones es muy frecuente la aglomeración y solapamiento de elementos, lo que aumenta la necesidad de emplear técnicas interactivas de transformación visual que faciliten la exploración visual de la interfaz.

En redes PFNETs, en cambio, la aglomeración de elementos es menor, debido al propio funcionamiento de los algoritmos de posicionamiento _spring models_ , por lo que el empleo de técnicas de transformación visual normalmente sólo resulta necesario cuando el número de nodos y/o arcos a representar es muy elevado.

Por último el algoritmo SOM es el que mejor aprovecha el espacio visual, ya que en su representación gráfica no existen zonas 'en blanco'. Esto significa que la aplicación de técnicas de transformación visual suele ser en la mayoría de casos innecesaria.

Además del hecho de que la técnica empleada en la etapa de distribución visual influirá en la necesidad de emplear o no técnicas de transformación, también se debe tener en cuenta que no todas las técnicas de transformación visual son igualmente adecuadas y _compatibles_ con todas las de distribución visual.

<table width="713" border="1" cellspacing="0" cellpadding="3" style="background-color: #FDFFDD; font-family: Verdana, Geneva, Arial, Helvetica, sans-serif; font-size: smaller; font-style: normal; border: solid;" align="center"><caption align="bottom">  
**Tabla 3\. Leyenda:** √ Combinación adecuada, - Adecuada pero con reservas, × Combinación inadecuada</caption>

<tbody>

<tr>

<th> </th>

<th>MDS</th>

<th>SOM</th>

<th>PFNETS</th>

</tr>

<tr>

<td width="149">

<div align="right">**Focus+Context**</div>

</td>

<td width="174">

<div align="center">-</div>

</td>

<td width="176">

<div align="center">√</div>

</td>

<td width="174">

<div align="center">-</div>

</td>

</tr>

<tr>

<td width="149">

<div align="right">**Detail+Overview**</div>

</td>

<td width="174">

<div align="center">x</div>

</td>

<td width="176">

<div align="center">-</div>

</td>

<td width="174">

<div align="center">√</div>

</td>

</tr>

<tr>

<td width="149">

<div align="right">**Zoom and Panning**</div>

</td>

<td width="174">

<div align="center">√</div>

</td>

<td width="176">

<div align="center">√</div>

</td>

<td width="174">

<div align="center">√</div>

</td>

</tr>

</tbody>

</table>

Las técnicas de _zoom and panning_ , por su simplicidad y al no tratarse de técnicas de distorsión, pueden ser utilizadas sobre representaciones generadas con cualquiera de los métodos de distribución y clasificación visual sin problemas.

Por otro lado, las de 'vistas múltiples' o _Detail+Overview_ no son aconsejables sobre representaciones de dispersión generadas por MDS. Estas representaciones, al contrario que las redes en forma de grafos, no poseen una estructura global clara y reconocible, por lo que la vista global u _Overview_ no ofrecerá valor orientativo durante la visualización de la interfaz por el usuario. En cambio, las representaciones en forma de grafos generadas mediante técnicas _Pathfinder_ , sí poseen una estructura global reconocible modelada por los arcos entre nodos, resultando en este caso de valor el empleo de técnicas _Detail+Overview_ .

La combinación de técnicas _Detail+Overview_ y SOM no es por definición inadecuada, aunque su grado de adecuación dependerá directamente de la forma del mapa obtenida y cómo de reconocible resulta su estructura global.

Por otro lado, la naturaleza distorsionadora de las técnicas _Focus+Context_ , si bien es la que les confiere su mayor potencial como técnicas de transformación interactiva, también es causa de problemas en su combinación con MDS y PFNETs.

La aplicación del efecto 'ojo de pez' sobre representaciones MDS ofrece problemas desde el momento que se realiza mediante procedimientos de deformación visual sobre las posiciones de los elementos. Como se ha comentado, las técnicas MDS se caracterizan porque la información estructural preservada de los datos originales es la relacionada con las distancias entre elementos, información que finalmente se perdería cada vez que se aplicase este efecto de transformación sobre las posiciones de los elementos. Es previsible que métodos como el de transformación cartesiana minimizarán este problema frente a métodos como el de transformación polar.

En redes PFNETs la transformación de las posiciones de los nodos, aunque también influye en la expresividad de la representación, no implica la misma problemática, puesto que la información preservada mediante técnicas _pathfinder_ es la de las relaciones locales más fuertes entre nodos, información que no se pierde con la aplicación del 'ojo de pez'.

Finalmente, los mapas SOM parecen ser especialmente adecuados para este efecto visual, puesto que la información de las relaciones de vecindad de elementos no se vería modificada por la aplicación del efecto de 'ojo de pez', además de que existen trabajos ([Yang, _et al._ 2003](#yang)) en los que ya ha sido probada su efectividad.

## Conclusiones

Es lógico que dada la cantidad de posibles combinaciones de técnicas, algoritmos y tipos de análisis en la generación de interfaces visuales para la recuperación de información, no todas las combinaciones hayan sido exploradas o investigadas.

Debido a que el objetivo de este trabajo es precisamente servir a otros investigadores como herramienta para la elección de una u otra combinación de técnicas en el desarrollo de propuestas específicas de 'Visual Interfaces for Information Retrieval'; se ha puesto especial énfasis en las técnicas de transformación visual, ya que consideramos que han sido menos estudiadas y aplicadas en la producción de 'Visual Interfaces for Information Retrieval'.

Al igual que las técnicas de clasificación y distribución, las de transformación visual tienen por objetivo simplificar espacios complejos de información, en este caso de la información visual que conforma la interfaz final. Esta simplificación no sólo se encuentra motivada para posibilitar la comprensión de grandes volúmenes de información que de otra forma no podrían ser interpretados por el usuario, sino también para facilitar esta visualización e interacción entre usuario e interfaz.

En este sentido creemos necesaria la investigación sobre nuevas técnicas de transformación visual interactiva o sobre nuevos modelos de aplicación de las existentes. Como hemos visto, aquellas técnicas de distribución visual que dan como resultado representaciones más complejas de visualizar, son precisamente las menos compatibles con las descritas técnicas de transformación interactiva. E igualmente, las técnicas de transformación interactiva que más compatibilidad ofrecen con las de distribución, resultan ser las que menos ventajas ofrecen en su tarea de facilitar la exploración visual de la interfaz.

No debemos olvidar que la divulgación y aceptación de este tipo de interfaces visuales por el público general no se encuentra frenada por su utilidad o no como herramientas de recuperación de información, sino por la dificultad de aprendizaje y uso que presentan para el usuario final.

La reducción de la carga visual de la interfaz, y por tanto de la carga cognitiva del usuario en la interacción con dicha interfaz, supone actualmente el más importante reto a superar en la investigación científica sobre producción de interfaces visuales para la recuperación de información.

## Referencias

*   <a name="baeza" id="baeza"></a>Baeza-Yates, R. (2004). Excavando la web. _El profesional de la información_, **13**(1), 4-10.
*   <a name="bederson" id="bederson"></a>Bederson, B.B. (2000). Fisheye menus. In Mark Ackerman & K. Edwards, (Eds.), _Proceedings of ACM Conference on User Interface Software and Technology (UIST 2000)_, (pp. 217-226). New York, NY: ACM Press.
*   <a name="berendt" id="berendt"></a>Berendt, B., Hotho, A., & Stumme, G. (2002). Towards semantic Web mining. In Ian Horrocks & James A. Hendler (Eds.), Proceedings of the First International Semantic Web Conference on The Semantic Web, (pp.264-278), London: Springer-Verlag. (Lecture Notes In Computer Science, 2342)
*   <a name="borner" id="borner"></a>Börner, K., Chen, C., & Boyak, K.W. (2003).Visualizing Knowledge Domains. _Annual Review of Information Science and Technology_, **37**, 179-255\.
*   <a name="buzydlowski" id="buzydlowski"></a>Buzydlowski, J.W., White, H.D., & Lin, X. (2001). [Term co-occurrence analysis as an interface for digital libraries](http://vw.indiana.edu/visual01/buzydlowski-et-al.pdf). In Katy Börner & Chaomei Chen (Eds.), _Visual interfaces to digital libraries_ [JCDL 2002 Workshop] (pp. 133-144), London: Springer-Verlag. (Lecture Notes In Computer Science, 2539) Retrieved 19 March, 2006 from http://vw.indiana.edu/visual01/buzydlowski-et-al.pdf
*   Buzydlowski, J.W. (2003). [A comparison of self-organizing maps and pathfinder networks for the mapping of co-cited authors](http://dspace.library.drexel.edu/retrieve/503/Thesis.PDF). Unpublished Ph.D. thesis, Drexel University, Philadelphia, USA. Retrieved 15 August, 2005 from http://dspace.library.drexel.edu/retrieve/503/Thesis.PDF
*   <a name="chen" id="chen"></a>Chen, C. (1997). Structuring and visualising the WWW by generalised similarity analysis. In Mark Bernstein, Kasper Østerbye & Leslie Carr (Eds.) Conference on Hypertext and Hypermedia, Proceedings of the eighth ACM conference on Hypertext. Southampton, United Kingdom, April 06 - 11, 1997 (pp. 177 - 186). New York, NY: ACM Press.
*   Chen, C. (1998). Generalised similarity analysis and pathfinder network scaling. _Interacting with Computers_, **10**(2), 107-128\.
*   Chen, C., & Czerwinski, M.P. (2000). [Empirical evaluation of information visualizations: an introduction.](http://www.pages.drexel.edu/~cc345/papers/ijhcs2000a.pdf) _International Journal of Human-Computer Studies_, **53**(5), 631-635\. Retrieved 19 March, 2006 from http://www.pages.drexel.edu/~cc345/papers/ijhcs2000a.pdf
*   <a name="chung" id="chung"></a>Chung, W., Chen, H., & Nunamaker, J.F. (2003). [Business intelligence explorer: a knowledge map framework for discovering business intelligence on the Web.](http://csdl.computer.org/comp/proceedings/hicss/2003/1874/01/187410010b.pdf) In Proceedings of the 36th Hawaii International Conference on System Sciences (HICSS'03) - Track1 - Volume 1, January 6-9, 2003, (pp. 10.2). Washinton, DC: IEEE. Retrieved 19 March, 2006 from http://csdl.computer.org/comp/proceedings/hicss/2003/1874/01/187410010b.pdf
*   <a name="Dursteler" id="Dursteler"></a>Dürsteler, J.C. (2002). [Information visualisation, what is it all about?](http://www.infovis.net/printMag.php?num=100&lang=2). _Inf@Vis! The digital magazine of InfoVis.net_, (100). Retrieved 22 November, 2005 from http://www.infovis.net/printMag.php?num=100&lang=2
*   <a name="eick" id="eick"></a>Eick, S.G. (2001). Visualizing on-line activity. _Communication of the ACM_, **44**(8), 45-52\.
*   <a name="fowler" id="fowler"></a>Fowler, R.H., Wilson, B.A., & Fowler, W.A.L. (1992). [_Information Navigator: an information system using associative networks for display and retrieval_](http://www.cs.panam.edu/research/information_navigator.pdf). Edinburg, TX: University of Texas-Pan American, Department of Computer Science. (Technical Report NAG9-551, No. 92-1). Retrieved 19 March, 2005 from http://www.cs.panam.edu/research/information_navigator.pdf
*   <a name="furnas" id="furnas"></a>Furnas, G.W. (1986). [Generalized fisheye views.](http://www.si.umich.edu/~furnas/Papers/FisheyeCHI86.pdf) In Marilyn Mantei & Peter Orbeton (Eds.). _Proceedings of the SIGCHI conference on human factors in computing systems, Boston, Massachusetts, United States, April 13-17, 1986_, (pp. 16-23). New York, NY: ACM Press. Retrieved 19 March, 2006 from http://www.si.umich.edu/~furnas/Papers/FisheyeCHI86.pdf
*   <a name="gutwin" id="gutwin"></a>Gutwin, C.; & Fedak, C. (2004). [Interacting with big interfaces on small screens: a comparison of fisheye, zoom, and panning techniques](http://hci.usask.ca/publications/2004/bigui-gi04.pdf.). In Proceedings of the 2004 conference on graphics interface. London, Ontario, Canada, May 17-19, 2004\. (pp. 145-152). London, ON, Canada: University of Waterloo, Canadian Human-Computer Communications Society. Retrieved 19 March, 2006 from http://hci.usask.ca/publications/2004/bigui-gi04.pdf
*   <a name="hayama" id="hayama"></a>Hayama, T., Kanai, T., & Kunifuji, S. (2003). Personalized environment for skimming documents. _Lecture Notes in Computer Science_, **2774**(2), 771-778\.
*   <a name="herrero" id="herrero"></a>Herrero-Solana, V., & Moya-Anegón, F. (1999). Science in America Latina: a comparison of bibliometric and scientific-technical indicators. _Scientometrics_, 1999, **46**(2), 299-320\.
*   Herrero-Solana, V. (2000). _Modelos de representación visual de la información bibliográfica: aproximaciones multivariantes y conexionistas._ [Models of visual representation of bibliographic information: multivariate approximations and connections.] Unpublished Ph.D. thesis, University of Granada, Granada, Spain.
*   <a name="horn" id="horn"></a>Hornbæk, K., Bederson, B.B., & Plainsant, C. (2002). Navigation patterns and usability of zoomable user interfaces with and without an overview. _ACM Transactions on Computer-Human Interaction_, **9**(4), 362-389.
*   Hornbæk, K., & Frøkjær, E. (2003). Reading patterns and usability in visualizations of electronic documents. _ACM Transactions on Computer-Human Interaction_, **10**(2), 119-149\.
*   <a name="kamada" id="kamada"></a>Kamada, T., & Kawai, S. (1989). An algorithm for drawing general undirected graphs. _Information processing letters_, **31**(1), 7-15\.
*   <a name="kaski" id="kaski"></a>Kaski, S. (1997). [_Data exploration using self-organizing maps_](http://www.cis.hut.fi/%7Esami/thesis/). Espoo, Finland: Finnish Academy of Sciences. (Acta Polytechnica Scandinavica, Mathematics, Computing and Management in Engineering Series No. 82). Retrieved 13 August, 2005 from http://www.cis.hut.fi/~sami/thesis/
*   <a name="kobourov" id="kobourov"></a>Kobourov, S. G., & Yusufov, R. (2005). [Visualizing large graphs with compound-fisheye views and treemaps](http://www.cs.arizona.edu/people/kobourov/cfv-gd04.pdf). _Lecture Notes in Computer Science_, **3383**, 431-441\. Retrieved 13 June, 2005 from http://www.cs.arizona.edu/people/kobourov/cfv-gd04.pdf
*   <a name="kohonen" id="kohonen"></a>Kohonen, T. (1989). _Self-organization and associative memory_. (3rd ed.). Berlin : Springer-Verlag.
*   <a name="koike" id="koike"></a>Koike, H. (1995). Fractal views: a fractal-based method for controlling information display. _ACM Transactions on Information Systems_, **13**(3), 305-323\.
*   <a name="kopanakis" id="kopanakis"></a>Kopanakis, I., & Theodoulidis, B. (2003). Visual data mining modeling techniques for the visualization of mining outcomes. _Journal of Visual Languages and Computing_, **14**(6), 543-589\.
*   <a name="kruskal" id="kruskal"></a>Kruskal, J.B. (1964). Nonmetric multidimensional scaling: a numerical method. _Psychometrika_, **29**(2), 115-129\.
*   <a name="lamping" id="lamping"></a>Lamping, J., Rao, R., & Pirolli, P. (1995). A focus+context technique based on hyperbolic geometry for visualizing large hierarchies. In Irvin R. Katz, Robert Mack, Linn Marks, Mary Beth Rosson & Jakob Nielsen (Eds.). _Proceedings of the ACM SIGCHI conference on Human factors in computing systems, Denver, Colorado, United States, May 1995_ (pp. 401-408). New York, NY: ACM Press.
*   <a name="leung" id="leung"></a>Leung, Y.K., & Apperley, M.D. (1994). Review and taxonomy of distortion-oriented presentation techniques. _ACM Transactions on Computer-Human Interaction_, **1**(2), 126-160.
*   <a name="lin" id="lin"></a>Lin, X. (1997) . Map displays for information retrieval. _Journal of the American Society for Information Science_, **48**(1), 40-54.
*   <a name="luhn" id="luhn"></a>Luhn, H.P. (1958). The automatic creation of literature abstracts. _IBM Journal of Research and Development_, **2**(2), 159-165.
*   <a name="mackinlay" id="mackinlay"></a>Mackinlay, J. D., Robertson, G. G., & Card, S. K. (1991). The perspective wall: detail and context smoothly integrated. In Scott P. Robertson, Gary M. Olson & Judith S. Olson (Eds.). _Proceedings of the SIGCHI conference on Human factors in computing systems: reaching through technology. New Orleans, Louisiana, United States, April 27-May 2, 1991_ (pp. 173-176). New York, NY: ACM Press.
*   <a name="marchionini" id="marchionini"></a>Marchionini, G. (1995). _Information seeking in electronic environments_. New York, NY: Cambridge University Press.
*   <a name="marcos" id="marcos"></a>Marcos-Mora, M.C. (2004). _Interacción en interfaces de recuperación de información: conceptos, metáforas y visualización_. [Interaction in information retrieval interfaces: concepts, metaphors and visualization.] Gijón: Ediciones TREA.
*   <a name="moya" id="moya"></a>Moya-Anegón, F. (1994). _Los sistemas integrados de gestión bibliotecaria: estructuras de datos y recuperación de información_. [Integrated library management systems: data structures and information retrieval.] Madrid: ANABAD.
*   Moya-Anegón, F., & Herrero-Solana, V. (1999). [Investigaciones en curso sobre interfaces gráficos en dos y tres dimensiones para el acceso a la información electrónica](http://www.ucm.es/info/multidoc/multidoc/revista/num8/moya.html). _Cuadernos de Documentación Multimedia_, (8). Retrieved 15 August, 2005 from http://www.ucm.es/info/multidoc/multidoc/revista/num8/moya.html
*   <a name="noik" id="noik"></a>Noik, E.G. (1993). Layout-independent fisheye views of nested graphs. In _Proceedings of the 1993 IEEE Workshop on Visual Languages, August 24-27, 1993, Bergen, Norway_. (pp. 336-341). Washington, DC: IEEE Computer Society.
*   <a name="north" id="north"></a>North, C., & Shneiderman, B. (2000). Snap-together visualization: can users construct and operate coordinated visualizations? _International Journal of Human-Computer Studies_, **53**(5), 715-739\.
*   <a name="orimo" id="orimo"></a>Orimo, E., & Koike, H. (1999). ZASH: a browsing system for multi-dimensional data. In _Proceedings of the IEEE Symposium on Visual Languages, Washington, DC, USA, September 13 - 16, 1999_, (pp. 266-286). Washington: IEEE Computer Society.
*   <a name="parker" id="parker"></a>Parker, G., Franck, G., & Ware, C. (1998). Visualization of large nested graphs in 3D: navigation and interaction. _Journal of Visual Languages and Computing_, **9**(3), 299-317\.
*   <a name="polanco" id="polanco"></a>Polanco, X., & Zartl, A. (2002). [Information visualization](http://eicstes.inist.fr/public/D1.4_Visualization_WP9.pdf). EICSTES Project. Deliverable 1.4\. State of the art part c: WP9\. Retrieved 12 April, 2005 from http://eicstes.inist.fr/public/D1.4_Visualization_WP9.pdf
*   <a name="rennison" id="rennison"></a>Rennison, E. (1994). Galaxy of news: an approach to visualizing and understanding expansive news landscapes. In _UIST 94, ACM Symposium on User Interface Software and Technology_. (pp.3-12). New York, NY: ACM Press
*   <a name="rijsbergen" id="rijsbergen"></a>Rijsbergen, C.J. (1975). [_Information retrieval_](http://www.dcs.gla.ac.uk/Keith/Preface.html). London: Butterworths, 1975\. Retrieved 14 May, 2005 from http://www.dcs.gla.ac.uk/Keith/Preface.html
*   <a name="salton" id="salton"></a>Salton, G. (1989). _Automatic text processing: the transformation, analysis and retrieval of information by computer_. Reading, MA: Addison Wesley.
*   <a name="sarkar" id="sarkar"></a>Sarkar, M., & Brown, M.H. (1992). Graphical fisheye view of graphs. In Penny Bauersfeld, John Bennett & Gene Lynch (Eds.). _Proceedings of the SIGCHI conference on Human factors in computing systems. Monterey, California, United States, May 03 - 07, 1992_. (pp. 83-91). New York, NY: ACM Press.
*   <a name="schaffer" id="schaffer"></a>Schaffer, D. et al. (1996) . Navigating hierarchically clustered networks through fisheye and full-zoom methods. _ACM Transactions on Computer-Human Interaction_, **3**(2), 162-188.
*   <a name="schvaneveldt" id="schvaneveldt"></a>Schvaneveldt, R. (Ed.) (1990). _Pathfinder associative networks: studies in knowledge organization_. Norwood, NJ : Ablex.
*   <a name="schneiderman" id="schneiderman"></a>Shneiderman, B. (1992). Tree visualization with tree-maps: 2-d space-filling approach. _ACM Transactions on Graphics_, **11**(1), 92-99\.
*   <a name="spence" id="spence"></a>Spence, R., & Apperley, M. (1982). Data base navigation: an office environment for the professional. _Behaviour and Information Technology_, **1**(1), 43-54\.
*   <a name="storey" id="storey"></a>Storey, M-A.D., Wong, K., Fracchia, F.D. & Müller, H.A. (1997). On integrating visualization techniques for effective software exploration. In _Proceedings of the 1997 IEEE Symposium on Information Visualization, October 18-25, 1997_ (pp. 38-45). Washington: IEEE Computer Society.
*   Storey, MA. D., Fracchia, F.D., & Müller, H.A. (1999). Customizing a fisheye view algorithm to preserve the mental map. _Journal of Visual Languages and Computing_, **10**(3), 245-267\.
*   <a name="turetken" id="turetken"></a>Turetken, O., & Sharda, R. (2004). Development of a fisheye-based information search processing aid (FISPA) for managing information overload in the web environment. _Decision Support Systems_, **37**(3), 1-20\.
*   <a name="yang" id="yang"></a>Yang, C., Chen, H., & Hong, K. (2003). Visualization of large category map for Internet browsing. _Decision Support System_, _35_(1), 89-102.


## Abstract

> **Introduction**. In recent years the volume of electronic information has grown exponentially. This phenomenon improves data exchange and communication but introduces new troubles in relation to information access and searching.  
> **Aim**. This paper proposes an exhaustive review of the different models, methods and algorithms that can be used to develop Visual Interfaces for Information Retrieval. The methods are classified on the basis of the stage of the process in which they take part: data analysis and transformation, application of classification and visual distribution algorithms, and application of visual transformation techniques.  
> **Methodology**. Based on the analysis, we compare the different methods that can be used in each stage of the production process. We also determine which combinations of methods and algorithms are most suitable at different stages.  
> **Results**. In the first section, data analysis and transformation, we analyse content mining, structure mining and use mining. In the second section, visual classification algorithm, we shown the hierarchical, network, scattering and map representations. In the last section, visual transformation techniques, we present the distortion (Focus+Context) and non-distortion techniques.  
> **Conclusion**. The results aim to become useful tools for other researchers when choosing a methodological combination for the development of specific proposals for visual interfaces for information retrieval, as well as suggest implications to be considered on the research of new visual transformation techniques.
