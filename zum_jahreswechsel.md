# "Zum neuen Jahre"

Die [geprägten Zeiten](https://de.wikipedia.org/wiki/Gepr%C3%A4gte_Zeiten) fanden in der Gartenlaube natürlich ihren Niederschlag. Den [Weihnachtsfesten](https://diedatenlaube.github.io/weihnachtliche_Gartenlaube) folgen geradezu nahtlos die Jahreswechsel. Selbstredend bieten sich derlei Ereignisse wundervoll für Beiträge in der Gartenlaube an. Als Auftakt für das neue Jahr wurde gerne gereimt; Berichte und Erzählungen zu Traditionen des Jahreswechsels finden sich verstreut darunter:

<!-- w.wiki/EW$ -->

<iframe style="width: 300px; height: 60vh; border: none; margin-bottom:14px;" src="https://query.wikidata.org/embed.html#SELECT%20DISTINCT%20%3FDie_Gartenlaube%20%3FDie_GartenlaubeLabel_%20%3Ferscheinungsjahr%20%3FgenreLabel%20(GROUP_CONCAT(%3FschlagwortLabel%3B%20SEPARATOR%20%3D%20%22%2C%20%22)%20AS%20%3FzentralesThema)%20WHERE%20%7B%0A%20%20%3FDie_Gartenlaube%20wdt%3AP1433%20wd%3AQ655617%3B%0A%20%20%20%20rdfs%3Alabel%20%3FDie_GartenlaubeLabel_%3B%0A%20%20%20%20wdt%3AP577%20%3Fpubdate.%0A%20%20BIND(YEAR(%3Fpubdate)%20AS%20%3Ferscheinungsjahr)%0A%20%20OPTIONAL%20%7B%0A%20%20%20%20%3FDie_Gartenlaube%20wdt%3AP921%20%3Fschlagwort.%0A%20%20%20%20%3Fschlagwort%20rdfs%3Alabel%20%3FschlagwortLabel.%0A%20%20%20%20FILTER((LANG(%3FschlagwortLabel))%20%3D%20%22de%22)%0A%20%20%7D%0A%20%20OPTIONAL%20%7B%20%3FDie_Gartenlaube%20wdt%3AP136%20%3Fgenre.%20%7D%0A%20%20FILTER(REGEX(%3FDie_GartenlaubeLabel_%2C%20%22Jahreswechsel%7CNeujahr%7Cneue.*Jahr%7CJahresend.*%7CSylvester%22%40de))%0A%20%20FILTER((LANG(%3FDie_GartenlaubeLabel_))%20%3D%20%22de%22)%0A%20%20SERVICE%20wikibase%3Alabel%20%7B%20bd%3AserviceParam%20wikibase%3Alanguage%20%22%5BAUTO_LANGUAGE%5D%2Cen%22.%20%7D%0A%7D%0AGROUP%20BY%20%3FDie_Gartenlaube%20%3FDie_GartenlaubeLabel_%20%3Ferscheinungsjahr%20%3FgenreLabel%0AORDER%20BY%20(%3Ferscheinungsjahr)" referrerpolicy="origin" sandbox="allow-scripts allow-same-origin allow-popups"></iframe>

## Vorsätze

Das Projekt 'Die Datenlaube' ist kaum ein Jahr alt und blickt voller Ideen und Wünschen auf das nächste Jahr:

* Mit [Structured Data on Commons](https://commons.wikimedia.org/wiki/Commons:Structured_data) wollen wir dem "Illustrierten" in der Gartenlaube ein Stück auch im Digitalen näher kommen
* Wir wollen über 'Die Datenlaube' [sprechen](abstract_datenlaube_dbt20.html) und für Mitarbeit und für die Verschränkung mit anderen Projekten im Connex [[Wikisource+Wikidata+Commons]] motivieren
* Weiter Gartenlaube-Artikel erschließen, die Datenqualität verbessern, Nutzung und [OER](https://de.wikisource.org/wiki/Wikisource:OER) anregen, Schlagworter verteilen (Stand 28.12.2019: nur [6947](http://w.wiki/43s) Artikeln fehlt mind. ein 'main subject')

Wir wünschen allen ein gutes Neues Jahr 2020!

Team [<em>#DieDatenlaube</em>](https://diedatenlaube.github.io/die_datenlaube_der_gartenlaube)

<p>&nbsp;</p>
<p>Veröffentlicht am 27.12.2019</p>
<img alt="Creative Commons Lizenzvertrag" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/80x15.png" />&nbsp;&nbsp;&nbsp;<a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Namensnennung 4.0 International Lizenz</a> <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">
