Mitschrift 25.01.2018
======
eval.fmi.uni-jena.de

Testautomatisierung
===
  * erlaubt mehr exploratives arbeiten (man hat mehr zeit für andere dinge)
  * weniger fehleranfällig
  * datengetriebene tests ermöglichen schnelles arbeiten

nachteile
==
  * insg hoher aufwand
  * testcode ist nicht perfekt und aufwändig in der produktion
  * test-sw muss auch getestet werden
  * code muss permanent nachgepflegt werden: 400 testfälle auf ui-ebene, bei häufiger änderung muss ständig die testfälle angepasst (d.h. rausgenommen werden), am ende nur noch 50 tests ausführbar; neue tests müssen geschrieben werden
  * code erfordert auch code-review, gelegentlich refactoren, ständige anpassung an den zu testenden code
  * solcher code ist echt anspruchsvoll!; code soll fehler merken, aber robust genug, dass der nicht ständig crashed

hinweise
==
  * von kleinen testfällen zu komplexeren
  * von 1-2 leuten so komplexe sw, dass keiner der entwickler die anschauen, geschweige denn auszuführen => sw wurde weggeworfen...; sw wartbar halten!
  * testfälle unabhängig halten -> schwierig, weil das gegen die effizienz geht
  * vermeiden tests zu schreiben, die ähnlich sind (ähnliche vorgeschichten...)
  * testfälle müssen voneindander unabhängig sein, sonst weiß man nicht die jeweilige fehlerquelle; jeder testfall hat eigene vorgeschichte
  * zB: JUnittests: feste reiehenfolge der tests; noch schöner aber, wenn auch parallel ausführbar
  * testfall kann daten an der db ändern (oder andere globale einstellungen) => jeder testfall soll gleiche ausgangsbedingungen haben => **tear-down**
  * nicht zu früh mit der automatisierung/ testen allgemein anfangen
  * testcode womöglich in die gleiche codebasis halten, wo auch der produktcode ist <= wird kontrovers diskutiert

Ebenen der Testautomatisierungen
====
  * Unittests: insg zu 50% automatisiert
  * unterschiedliche interpretation der unterschiedlcihen testarten
  * code vom programmierer wird stark automatisiert getestet, abnahmetest hingegen kaum noch (das veranschaulicht auch die pyramide)
  * gui-code auch automatisieren? eher nicht.
  * code ebene:
    * testcode meistens auch der sprache des produktcodes
    * früher: testnamen mit nameskonventionen, heute nur mit annotationen, hi java!
    * assert: annahme, nimm an das xy = 5 ist..., typisch für stringvergleiche, anzahlvergleiche
    * nutzen von exceptions, um fehlerfälle zu catchen
    * stand-alone (im fat client) vs schritt im CI, wo der report dann iwo abgelegt wird
    * alles in einem testprozess
    * keine db-...tests! (auch kontrovers diskutiert: muss ja auch mal getestet werden, man nutzt library, die so tut als ob "mocking") => nicht zu viel mocken! sonst wird am ende nur noch einen testzeile geprüft
    * "policies": geben fest, was der entwickler zu beachten hat. kürztmöglicher "weg" beim entwickler
    * 10000 bis 100000 testfälle pro projekt! (es läbbert sich.)
    * JUnit, testNG, ...
  * api ebene:
    * weniger tests als auf code ebene
    * lokal vs remote
    * auch mit JUnit-test implementiert, daher oft auch fälschlicherweise als Unit-Tests bezeichnet
    * remote: code wird nicht direkt aufgerufenen, sondern iwo ein anderer server oder so. testfälle kommunizieren dann so..., synchron oder asynchron
      * synchron: http, RESTful
      * asynchron: entwickler selber muss testchnittstelle anbieten, wo auf die antwort gewartet wird
    * testfälle / testumgebungen hier wesentlich kmplexer
  * gui ebene:
    * früher mit zu installierender test-sw
    * nicht die ui wird getestet, sondern die anwendung der der ui!
    * immer mit testwerkzeug:
      * tool hängt sich vor die zu testende anwendung
      * tool fernsteuert zu testende anwendung, früher: einfach aufzeichnung von maus und tastaturbefehlen -> blöde idee: schon bei unterschiedlicher auflösung greift man daneben
        -> _hanorex_ **?**
    * meistens auf windows, ... zugeschnitten
    * heute: testanwendungen im browser, zb _katalon recorder_ ... _#grummel_, also erweiterungen v.a. ei lastTests
    * eigtl soll ja anwendung getestet werden, nicht der browser...
  * automatisierte tests auf unterer ebene leichter zu implementieren als auf den darüberliegendene ebenen.

  grenzen der Testautomatisierung
  ===
    * validierung macht tests sehr langsam
    * kaum testgewinne
    * James Bach: "Ein automatisierter Test testet nicht, er prüft nur."


-> prüfungen immer montags oder dienstags, mittwochs, an xceptance adresse, ab 12.2.
