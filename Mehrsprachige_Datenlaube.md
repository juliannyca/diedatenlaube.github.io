<h1 id="mehrsprachige-datenlaube">Mehrsprachige Datenlaube</h1>
<p>Multilingualität ist eines der wesentlichen Merkmale von Wikidata. <a href="https://w.wiki/xuZ">Knapp 600 Sprachen oder Varianten</a> sind aktuell im offenen Knowledge Graph des Wiki*Versums verfügbar um die jeweiligen Datensätze mit einem Label, einer Beschriftung oder einem Variantennamen zu versehen, bzw. in spezifischen mehrsprachigen Datenfelder (bspw. die Felder ‚<a href="https://www.wikidata.org/wiki/Property:P1476">Titel</a>‘ oder das <a href="https://www.wikidata.org/wiki/Property:P6375">Adress-Textfeld</a>) Textwerte mit der zugrunde liegenden Sprache zu versehen. </p>
<h2 id="mehrsprachige-beschreibungen-für-katalogdaten-und-illustrationen">Mehrsprachige Beschreibungen für Katalogdaten und Illustrationen</h2>
<p>Die Mehrsprachigkeit von Wikidata legt auch offen aus welchen Sprach- und Kulturkreis bestimmte Items stammen oder ihnen zuzurechnen sind. Die bibliographischen Items der Datenlaube wurden beispielsweise bislang standardmäßig dreisprachig mit Labels und Beschreibungstexten in Deutsch, Englisch und Niederländisch erfasst. (vgl. Abb. 1)</p>

<figure>
<img src="./Pictures/1000020100000350000001BBFECB95B322C7DC05.png" alt="Abbildung 1: Labels und Descriptions von Gartenlaube-Items in deutsch, englisch, holländisch" style="width:17cm;height:8.879cm" /><figcaption>Abbildung 1: Labels und Descriptions von Gartenlaube-Items in deutsch, englisch, holländisch</figcaption>
</figure>

<p>Das Label von bibliographischen Items wird standardmäßig zumeist mit dem Originaltitel des vorliegenden Werkes versehen, weshalb es eher nicht zu einer Übersetzung des Titels in Zielsprachen kommt. Der Beschreibungstext hingegen erlaubt es in der jeweiligen Sprache anzuzeigen, was das vorliegende Item beschreiben möchte – beispielsweise einen (Zeitschriften)-Artikel (in deutscher Sprache) in der Zeitschrift ‚Die Gartenlaube‘ mit Publikationsjahr und Fundstelle (Heftnummer und/oder Seitenzahl). </p>

<p>Gerade für das Beschreibungsfeld, das sich bei bibliographischen Datensätzen nach einem sehr stringenten Muster aufbaut, ist die Anreicherung mit weiteren Sprachen leicht möglich. Für die (nieder- und ober-)<a href="https://de.wikipedia.org/wiki/Sorbische_Sprache">sorbische Sprache</a> wurden Beschreibungstexte ergänzt. </p>
<figure>
<img src="./Pictures/10000201000001EA000002BC3C9110CA909D4684.png" alt="Abbildung 2: Tweet als Anstoß Gartenlaube-Items in sorbischer Sprache zu beschreiben https://twitter.com/juliannyca/status/1357422861695213569" style="width:12.965cm;height:18.521cm" /><figcaption>Abbildung 2: Tweet als Anstoß Gartenlaube-Items in sorbischer Sprache zu beschreiben https://twitter.com/juliannyca/status/1357422861695213569</figcaption>
</figure>

<p>Auf Basis der in Abbildung 2 gezeigten Vorlage kann mittels <a href="https://w.wiki/xuw">SPARQL-Query </a>eine Grundlage für neue Beschreibungstexte in nieder- und obersorbischer Sprache abgefragt und zum Import mittels <a href="https://quickstatements.toolforge.org/">QuickStatements</a> verwendet werden. </p>

<p>Die selbe Vorgehensweise gilt auch für die mehrsprachigen Beschreibungstexte der Gartenlaube-Illustrationen in Wiki Commons wie in Abbildung 3 gezeigt. </p>
<figure>
<img src="./Pictures/1000020100000387000001B6021FA75CAFF428CA.png" alt="Abbildung 3: Mehrsprachige Dateibeschreibungen in Wiki Commons" style="width:17cm;height:8.244cm" /><figcaption>Abbildung 3: Mehrsprachige Dateibeschreibungen in Wiki Commons</figcaption>
</figure>
<h2 id="mehrsprachige-sacherschließung">Mehrsprachige Sacherschließung</h2>
<p>Beschreibungstexte sind aber mehr eine Fingerübung und bieten gerade im vorliegenden Fall einen eher überschaubaren Mehrwert. Gänzlich anders verhält es sich, wenn man die mehrsprachige Verfügbarkeit von Item-Labels und Descriptions bei verlinkten Entitäten betrachtet. Gerade die für die inhaltliche Erschließung der Artikel verwendeten Schlagworte können, wenn sie denn übersetzt sind, ermöglichen auf Basis fremdsprachiger Einstiege nach inhaltlichen Bezügen in den (deutschsprachigen) Artikeln zu recherchieren. </p>

<p>Um hier einen Beitrag zu leisten, kann nach Schlagworten in Gartenlaube-Artikel abgefragt werden, die in einer bestimmten Zielsprache noch kein Label besitzen, der folgende <a href="https://w.wiki/xv2">Code-Block </a>zeigt dies für die obersorbische Sprache, ausgenommen von den Schlagworten sind Personen-Items, da es hier bei den Labels abgesehen von kulturellen oder sprachlichen Erfordernissen nicht zu einer Übersetzung kommt. </p>

<p>SELECT DISTINCT ?schlagwort ?schlagwortLabel ?schlagwortLangLab WHERE {</p>
<p>  ?item wdt:P1433 wd:Q655617;</p>
<p>    wdt:P921 ?schlagwort.</p>
<p>  FILTER(NOT EXISTS {</p>
<p>    ?schlagwort rdfs:label ?schlagwortLangLab.</p>
<p>    FILTER((LANG(?schlagwortLangLab)) = "hsb") #Hier Sprachcode einbauen</p>
<p>  })</p>
<p>  MINUS { ?schlagwort wdt:P31 wd:Q5. }</p>
<p>  SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],en". }</p>
<p>}</p>

<p>Datenpflege nach diesem Muster erlaubt es in Wikidata nach Artikeln der Gartenlaube zu <a href="https://w.wiki/xv7">recherchieren</a>, deren Thema „Kamjenc“ (obersorbisch für Kamenz) ist.</p>

<p>SELECT ?item ?itemLabel ?schlagwortLangLab WITH { </p>
<p>  SELECT DISTINCT ?item ?schlagwortLangLab WHERE {</p>
<p>  ?item wdt:P1433 wd:Q655617;</p>
<p>    wdt:P921 ?schlagwort.</p>
<p>  ?schlagwort rdfs:label ?schlagwortLangLab.</p>
<p>  FILTER((LANG(?schlagwortLangLab)) = "hsb")</p>
<p> } } AS %results </p>
<p>WHERE {</p>
<p>  INCLUDE %results.</p>
<p>  FILTER(CONTAINS(?schlagwortLangLab,"Kamjenc"))</p>
<p>  SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],hsb,en". }</p>
<p>}</p>

<p>In Wikidata läuft Mehrsprachigkeit zentral zusammen und ermöglicht Portalen unterschiedlicher Sprach- und Kulturkreise, ob diese Millionen oder nur wenige hundert SprecherInnen aufweist, mit überschaubarem Aufwand Datenbestände anzureichern, abzufragen und somit erfahrbar zu machen.</p>
<h2 id="ein-blick-auf-die-mehrsprachigkeit">Ein Blick auf die Mehrsprachigkeit</h2>
<p>Zum Zeitpunkt (2020-02-05) lagen für die zur Beschreibung der Gartenlaube-Artikel verwendeten Schlagworte Labels in 424 verschiedenen Sprachen vor. Wie viele Schlagworte je Sprache dabei vorhanden sind zeigt das folgende Diagramm:</p>

<p>Für 9.517 Schlagworten liegen deutsche Labels vor, gefolgt von 9.392 Items mit englischen Labels, beispielsweise liegt hingegen mit tunesisch-arabischem Label am anderen Ende der Skala nur ein Item vor. </p>
<h2 id="verbessert-die-mehrsprachigkeit">Verbessert die Mehrsprachigkeit</h2>
<p>Um abzufragen welche Schlagwortlabels der Gartenlaube noch nicht in eine bestimmte Sprache übersetzt sind, wählt man zuerst einen Sprachcode aus dieser <a href="https://w.wiki/xuZ">Abfrage</a> aus und setzt den Code in der Abfrage nach fehlenden <a href="https://w.wiki/xv2">Schlagwort-Labels</a> ein. Und schon kann Labels „<a href="https://w.wiki/xvD">ins Boarische iwasetzn</a>“. </p>