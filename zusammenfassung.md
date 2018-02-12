zusammenfassung
======
immer mehr sw im alltag -> mehr sw -> mehr potentielle fehler möglich
fehlerfreie sw nicht möglich

fehlerarten:
  * failure (äußerer fehler) bspw anwendung bleibt hängen
  * fault (innrer fehler) fehlerhafte code-anweisung
  * error ("pebcac") anwender macht falsche eingabe, programmierer macht c&p-fehler
  * wechselwirkungen

stufen qa-organisation:
  1) kein dedizierter tester: nur entwickler testen sich selbst
  2) kein dedizierter tester: entwickler testen sich gegenseitig
  3) in einem team gibt es einene tester
  4) separates test-team
  5) unabhängige zentrale qa
  1+2 ungenügend, 3 agil, 4 gute idee..aber unüblich?, 5 traditionell

  bestes mittel um fehler zu vermeiden: **KOMMUNIKATION!!**

  test:
  1) der prozess eines systems/betriebs/komponente unter spezifizierten bedingungen
  unter beobachtung/aufzeichnung der ergbnisse und der evaluation einiger aspekte
  der komponente/system/betriebs.
  2) das ausführen eines programmes mit der absicht fehler zu finden.

  anforderungen:
    * explizit: gewünschte a.
      * funktional: spezifiziert die aufgaben
      * nicht-funktional: bspw rechenzeit, max größe der dateien, einhaltung gewisser stds
    * implizit: offensichtliches(kein zerschossenes design...) + berechtigtes

  testorakel: beschreibt soll-anforderungen. in dem orakel steht drin, was für ergebnisse bei bestimmten eingaben erwartet werden, unabh vom programmcode

  eigenschaften guter test:
    * findet viele fehler mit minimalem aufwand
    * gut dokumentiert
    * deckt alle arten von tests ab
    * einduetig und wiederholbar

  qs: "unter qs versteht man die gesamtheit aller merkmale/merkmalswerte eines swprodukts, die sich auf dessen nutzung beziehen, festgelegte soll+ist-anforderungen zu zu erfüllen."

  iso 25010:
    * funktionale eignung (viele können alles)
    * leistungseffizienz (ZiRKus)
    * kompatibilität (ki)
    * benutzbarkeit (für arme ernährer brauchen ärmere beine.)
    * zuverlässigkeit (riechen füße wieder vertraut?)
    * sicherheit (viele interessante nüsse zum aufmachen.)
    * wartbarkeit (meine WAnd muss pinkeln.)
    * übertragbarkeit (alles im abfall)
    * (dokumentation)

unterteilung von testarten:
  * manuell vs automatisiert (Unit-, komponenten-, schnittstellen, gui-tests)
  * gui tests (expertentest, feldstudie)
  * effizienztest (last+performanztest)
  * sehr wichtig: sicherheitstest(anwenderorientiert, penetrationstest)
  * reviews: manuell oder per automatisierter review-tools
  * statisch (objekt wird nicht ausgeführt, kontrolle der güte des codes) vs dynamisch (testobjekt wird ausgeführt, wichtigste testart!, wie gut erledigt code bestimmte aufgaben?)
  * konstruktiv (~tdd, während der entwicklung versuchen tests fehler zu vermeiden) vs analytisch (fertiger code wird auf fehler untersucht)
  * black-box (code wird nicht betrachtet, so werden testfälle unabhängig vom code gefunden) vs white-box (code wird mit betrachtet, bessere tester-entwickler-kommunikation, ermöglicht codespezifischeres testen)

weitere testarten:
  * Fehlernachtest (re-test): nach korrektur erneuter test
  * regressionstest: neue komponente wurde angefügt -> testen ob alles im verbund noch klappt
  * feature test: testen eines neu entwickelten features
  * smoketest: programm wird an allen stellen initial probegelaufen, entsteht an ieiner stelle etwas, was nicht passieren darf, wird fehler geworfen "smoke"

e-k-i-s-a:
  * entwicklertest: ungenügend
  * komponententest: einzelne komponente wird getestet
  * integrationstest: testen des zusammenspiels verschiedener code-komponenten
  * systemtest: gesamtes system wird getestet (vgl. end-zu-end - test?)
  * abnahmetest: final test, bevor produkt ausgelierfert wird

teststufe: unterteilung von test(fällen) in unterschiedliche klassen, zum beispiel nach (rbt->fehlerwahrscheinlichkeit, fehlerschwere, dringlichkeit, ...)

testobjekt: beschreibt was genau getestet werden soll.
  abh. von granularität kann es sich um funktionen bis zu ganzen (mehrerern?) komponenten handeln

wie wird getestet?
  bedingung: definition + priorisierung
  1) auswahl testobjekt
  2) sammeln von infos (zb aus testorakel, aber im grunde alles)
  3) berücksichtigung qs-maßnahmen, teststufe
  4) auswahl der testmethodik (lasttest, regressionstest, ...)
  5) festlegung der testtiefe
  6) überlegen von testideen
  7) ggf review
  8) erstes ausführen und **anpassen**

testfall:
  * besteht aus: namen, beschreibung, attachments, tags, ...
  * eigenschaften: in sich abgeschlossen, atomar, prüfbares ergebnis, testaktionen überlappen sich nicht

vorbedingungen:
  * alles was keine anweisung ist, wird benötigt um ausganssituation zu erreichen -> sog vorbedingungen
  * implizites/selbstverständliches weglassen

granularität von testfällen:
  * wenn A dann mach B vermeiden!
  * grundvoraussetzung schaffen und dann mehrere tests schaffen! => übersichtlicher
  * sonst auch abhängigkeiten der tests zueinander. jeder test soll nur eine spezielle sache testen

testaktionen:
  * jeder honk muss die anweisungen begreifen, um zu verstehen was intentiion, aktionen und eigenschaften des testfalls sind die der tester aufschreibt
  * so allgemein wie möglich, so spezifisch wie nötig
  * erw. testergebnis: testergebnis soll **ALLES** liefern. auch bspw implizites.
  * wir betrachten nur das testergebnis: -> testdurchlauf soll möglichst schlank sein! db's und alles was zeit raubt wird gemockt.

viele tester finden mehr tests! aber lorithmuskurve! bester wert: 2 tester!

fehlerarten:
  * normalfall: happy path. wir testen genau am code entlang
  * spezialfall:  tests, die erfolgreich sind, weil sie gesondert im code abgefangen werden
  * fehlerfall: das, was immer fehlschlägt

testfallerweiterung:
  1) breite testbasis: normalfälle
  2) sonder+fehlerfälle
  3) spezielle sonder+fehlerfälle
  4) spezielle sonder+fehlerfälle an maximalen grenzen testen (max. wortlänge)
  5) extremtest: programm unter erschwerten bedingungen laufen lassen. zB ram voll

granularität:
  bereiche: neue features, fehleranfällige features, ...
  arten: testschwere, fehlerwahrsch., priorisierung, ...

fehlerverfolgung:
  new) test von qs erstellt
  assigned) fehler von pm an dev zugewiesen
  rejected) dev weist ticket zurück (duplicated, notReproducible, ...)
  fixed) dev löst problem
  closed) tester setzt fehlerlösungsvorgang auf abgeschlossen

erstellen von testfällen)
  1) gibt' schon?
  2) wurde fehler durch falsche daten statt durch falschen code erzeugt? (zB cache nicht gelöscht?)
  3) sammeln aller informationen bzgl des fehlers
  4) Erstellen des Testfalls
  5) testmaschine züruck in ausgangssituation bringen

kurzüberblick testmanagement
  * testplanung tm
    * kundengespräch vorausetzung für testing
    * => abnahmekritererien, testkonzept
    * top-down vs bottom-up
  * testvorbereitung
    * tm
      * priorisierung
      * risikoanalyse
      * vorbereitung test-tools
    * t
      * vorbereitung der tests
      * iterative feingranulierung der tests (anlegen der testarten -> konkrete test)
  * testdurchführung
    * tm
      * aufgabenverteilung
      * überwachung ob ein+ausgaben korrekt sind
    * t
      * eigtl testdurchführung
      * dokumentation
      * testmonitoring (ampel, teststatistik: von 100% 40% fehlerhaft, im 2. davon 10% fehlerhaft, ...)
  * testauswertung
    * **lessons learned**
    * bewertung
    * opt. testat oder bericht

was ist scrum?
* (hard to master, easy to learn)
lecihtgewichtiges rahmenwerk, vorgehensweise
* ziel: potentially shippable code, produkt-inkrement als ergebnis nach jedem sprint
* besteht aus drei bereichen:
  * 6 (3+3) rollen:
    * innere:
      * PO (product owner)
        * projektverantwortlicher
        * kümmert sich um (sprint) backlog(, welches die user stories beinhaltet: als ...  möchte ich ..., um ...)
        * nimmt code ab
        * entscheidet über auslieferung
      * Scrum master
        * "zeremonienmeister"
        * unterstützt das team
        * überwacht burn-down-chart
        * führt ma-gespräche
        * übernimmt keine verantwortung
      * dev-team:
        * setzt user stories in produkt-inkremente um
        * arbeitet eigenverantwortlich
        * besteht aus vielen spezialisten, die zusammen arbeiten
        * ca 10 ma
      * 3 außen:
        * verwaltung
          * schützt dev-team vor externen aufgaben
          * besetitgt hindernisse
          * => schafft rahmenbedingungen für optimale arbeit
        * kunde
          * enge zusammenarbeit mit po
        * nutzer
          * beurteilung
          * meist bei sprint planning und sürint review anwesend
  * 4 zeremonien
    * sprint planning
      * zu projektbeginn: schaffung der zentralen user stories
      * zu sprint beginn po zieht user stories aus product backlog in sprint backlog (was schaffen wir in diesem sprint?)
      * SP1: was können wir in diesem sprint schaffen?
      * SP2: wie können wir es schaffen?
    * daily scrum
      * stand-up meeting
      * jeder erzählt:
        * was habe ich gestern geschafft?
        * was mache ich heute?
        * gibt's probleme?
    * sprint review:
      * am ende des sprints (max. 4 stds)
      * po sagt was done ist, team stellt inkrement vor, po nimmt final ab
      * anpassung des sprint backlogs durch po
    * sprint retroperspective
      * direkt nach review
      * 3 fragen
        * was lief gut?
        * was lief schlecht?
        * wie können wir das verbessern?
  * 3 artefakte
    * product backlog
    * sprint backlog
    * burn-down-chart

agile qs: erster ansatz
  * meist nur 2 kontroll-instanzen:
    * automatische tests
    * abnahme durch po
  * durch qs:
    * fehler sollen früher gefunden werden
    * team hat höheren anspruch an die qualität seines codes
    * keine didizierten tester im dev-team! ===> KOMMUNIKATION
    * erste zwei kontrollinstanzen nicht ausreichend:
      * automatisierte tests durch entwickler => tester-expertise fehlt
      * po-abnahme => po auch zu positiv ggü code eingestellt, auch mangelnde programmier/tester-expertise

agile qs - tester im team
* 3 devs : 1 tester bis  1:1, wichtig für dod: früh mit testen beginnen können
* **whole team approach**: das ganze team sieht sich n der verantwortung code mit möglichst hoher codequalität auszuliefern
* neue herausforderungen an qs:
  * soziale schranke abbauen
  * weitere technische herausforderungen (CI, eigener testcode, code reviews)
