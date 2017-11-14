Seit Jahren beschäftige ich mich mit dem Thema **Clustering** mit mehr und mehr Begeisterung. Angefangen hat alles mit einem simplen Problem:
> "Warum machen meine Rechner im Büro eigentlich nichts Sinnvolles, wenn niemand daran arbeitet?"

Zuerst war die Frage simpel, doch dann kamen andere wie:
>"Warum kann ich nicht die Rechenleistung meiner Büronachbarn benutzen?"

Später kamen dann noch mehr Fragen, meist sehr schwierige, und mit schlaflosen Nächten verbundene Fragen. Mittlerweile bewegen sich professionelle *Clusterkonzepte* nicht nur in IT Infrastrukturen von Forschungsbereichen oder Universitäten, sondern erhalten auch immer mehr Einzug in die wirtschaftlichen Bereiche wie Hosting oder in  DataCentern. Selbst Branchenfremdlinge wie [Amazon.com](Amazon.com) versuchen sich sehr erfolgreich an diesem neuen Markt, wie wir später noch sehen werden.

Die Clusterwelt ist hierbei nicht hochspezialisiert, wie viele denken mögen, sondern hat einen sehr breit gefächertes Repertoire an Projekten, Funktionen und Leistungen. Die Community ist meist noch in der Forschungswelt angesiedelt, doch man bemerkt eine langsame Verlagerung hin zum Allgemeingut.

# Mose, Wölfe und Freaks
Projekte wie [openMosix](http://openmosix.sourceforge.net) oder [BeoWulf](http://www.beowulf.org) sind wohl die angestammtesten Projekte der Clustering-Szene und spätestens seit der Veröffentlichung von [ClusterKnoppix](http://clusterknoppix.sw.be) auch für einfache Anwender zu gebrauchen. Spezialisierte Clustering-Lösungen wie [openSSI](http://openssi.org) sind jedoch noch auf dem Weg und werden aktiv von einer großen Community unterstützt.

Die allseits belächelten *Cluster-Freaks* haben sich zu einer nicht zu verachteten Marktmacht gewandelt. Die Fortschritte, die im Bereich des klassischen Clustering momentan gemacht werden, sind hervorragend, und ebenso tauchen verstärkt Begriffe wie
*public computing* und *grid computing* aus den Tiefen des Internet an die Oberfläche der normalen Alltagswahrnehmung.

Hierbei werden nicht einzelne Rechner in einem
kleinen Clusterverbund zusammengeschlossen, sondern vielmehr mehrere tausend Rechner über eine öffentlich zugängliche Infrastruktur für Aufgaben zur Verfügung gestellt. Ob es sich dabei um einzelne Rechner, ganze Cluster oder Supercomputer handelt, ist hierbei ohne Belang. Daher wird diese Technik auch gerne als *Meta-Clustering* bezeichnet. Jeder kann die Rechenleistung dieses distributiven Rechennetzwerkes nutzen.

Wenn Sie sich weiter in diese Richtung informieren wollen, kann ich Ihnen zwei in meinen Augen sehr interessante Projekte ans Herz legen:

+ Das momentan von der [Cambridge University](https://www.cam.ac.uk/) entwickelte Projekt [XenoServer](http://www.xenoservers.net) und die Seiten von
+ [The Globus Alliance](http://www.globus.org) mit Ihrem *Globus Toolkit* für Grid-Computing.

# Kaugummi
Ich möchte mich mit dieser Ausarbeitung dem Thema *Virtual Elastic Services* widmen, um Mittel und Wege aufzuzeigen, allgemein bekannte und geprüfte Techniken aus dem OpenSource Bereich einzusetzen, um eine hochmoderne Infrastruktur für Hosting- bzw. Clustering-Lösungen abzubilden. Augenmerk bei der hier vorgestellten Lösung ist die Interdisziplinarität, da mehrere Ansätze aus Cluster-, Grid-, Virtualisierungs- und Hostinglösungen verwendet werden, um ein gemeinsames Ganzes zu schaffen.

Es gibt im Bereich des *Elastic Hosting* bereits einige proprietäre und kommerzielle Produkte, die jedoch jenseits des
Erschwinglichen liegt. Diesen Lösungen werden wir uns in späteren Kapiteln noch ausführlicher widmen. Den Weg, den ich versuche aufzuzeigen, kann man allein mit Arbeitszeit (ein paar *alte* Rechner vorausgesetzt) begehen. Die benötigte Software ist kostenlos und kann aus frei zugänglichen Quellen bezogen werden. Stellen Sie sich also auf einige schlaflose Nächte ein.

+ [Seminarausarbeitung](/content/images/2016/11/seminar_virtual_elastic_services.pdf)
+ [Seminarpräsentation](/content/images/2016/11/seminar_virtual_elastic_services_praesentation.pdf)