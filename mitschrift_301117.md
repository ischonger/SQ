Testfallerstellung
======
Wiederholung
===
 * es gibt unternehmen, de keine pw-sicherung machen
 * stark von persönlichen eigenschaften abhäängig
 * frei definierbar wie tief getstet werden soll. of projektabhäabhäängig
 * priorisierung des testens gfrei möglich
 * aufwandschätzung qs-aufwand vs fehlerkosten der nutzung
 * fehlerkosten sehr unterschiedlich va oparative fehlerkosten, weniger strageische fehlerkosten, die eher auf lange sicht
  * fehler früh finden, sonst svchnell teuer
  * qs-aufwand: stichwort "testfallexplosion" -> keine vollständige fehlerabdeckung mömöglich, eigtl gehen nur testproben
  => man kann nicht beweisen, dass sw fehlerfrei ist
  * wie groß macht man seine stichprobe: !kommunikationsfhler hier häufig, siehe dreieck; nie sagen, dass man vollständig testet
  * reduktion des formellen aufwands: von theoretischen ideen zum konkreten test
  * äquivalenzklassenanalyse:
   * alle eingabewerte bis auf einer werden auf einen stadnard gesetzt
   * das für alle werte machen
   * repräsentanten: typische werte. zB für alle werte werden die gleichen codezweige dutvhlaufen
   * bspw datum (siehe 29.2.), je nach implementierung kann es unterschiedliche äquivalenzklassen geben
   * top-down: gültige vs nichtgügültige
   * elementklassenbeziehender test

grenzwertanalyse
===
 * grenzwertanalyse: typische fehler der anfängerprogrammierung; null immer gerne geprüft;
 * spillner: man soll die genaue grenze der machbarkeit testen. => hält ronny für n fehler.
 * technisch bedingt fehler prüfen
 * zB 32bit zahlen testen kommt immer gut...
 * kombination von eingabewerten: isoliert betrachten. müssen kmbinationen geteste werden, führt oft zur explosion, nur bei einem guten grund trotzdem testen, daher sequentiell und isoliert betrachten, bsp: addressprüfung: bestimmte kombi von str, zipcode, ort muss halt stimmen- da also überhängender test
 * entcheidungstabellen: grade für den fall, dass mehrere werte getestet werden müssen, gibts tolle tools für..., welche kombinationen sollen gar ncith möglich sein -> die kann man dann die zeilen ausgrauen, die übrig bleiben, kann man ergebnisse eintragen und dann loslegen
 * im sap-umfeld ein trainingsumfeld ein großen firma. einer rüft , einer testet, dann gehts zurück..., ... erst nur verbal geschriebene anforderungen, "wenn an der organisationseinheit des teilers das flag 'zustimmung' gesetzt ist, dann muss der betriebsrat zustimmen", "buchngseingaben: ist berufl weiterbildung oder nicht (wird halt unterschiedlich bearbeitet)", workflow: mit, ohne vorgesetzten, ohne (<- sehr interressante anordnug)... war intern wichtig. kurzum: alles war ur verbal formuliert gewesen und die freudenhansel haben das in eine superübersichtliche tabelle gepackt. aber entscheidungstbellen sind dafür wohl sehr gut geeignet...; am eben ne million zeilen groß... -> einige kombinationen wegschmeißen:
  * pairwise: alle werte aus allen spalten müssen zumindest paarweise mit den testwerten anderer tests enthalten sein. zB jede zweier kombination muss drin sein (man schaut sich nicht n-kombinationen an), dadurch wird auf ein tausendstel/10000 minimiert, zeigt praxis, dass fehler oft durch fehlerhafte zweierkombinationen entstehen. (ich denke es ist nur eine einfachere abbildung von komplexeren problemen).
  * testmatrix: es wird mal auf alle werte geguckt... spart viel aufwand

zustandsbasierte testfallermittlung:
===
   * manchmal zustände selber herausarbeiten
   * alle kanten des graphen müssen traversierar sein
   * Bsp: werkstatttermin
   * crud-matrix: für jeden testfall einen eintrag erzeugen, technische betrachtung, gedacht für geschäftsprozesse
    * delete: am schwierigsten, bspw bei sap: wird auf den letzten anzeigbaren tag gesetzt. datensatz mit anderen verknüpft... ma eben löschen ist ne scheißidee.
    * update schwierig... caches!

anforderungsbasierte Testfallerstellung
===
 * in kontrollierter sprache ausdrücken. wenn nutzer das macht, dann das und das... nicht: wenn... dann...!
 * in praxis: durchlesen für implementierung der testfälle, testobjekthierarchie, evtl noch ein paar ideen

intuitive testfallermittlung
===
 * error guessing. der tester kennt den fehler vorher schon, aus erfahrung ;)
 * in praxis: am erfolgreichsten...
 * ARE U KIDDING ME?
 * listen von alten fehlern aufschreiben aus anderen projekten

exploratives testen
===
 * fehler treten meist lokal gehäuft auf
 * da wo ein fehler ist, ist auch noch ein anderer -> dort gehäuft testen
 * session.based management: aufteilung in sessions, aus 2000. jede session bekommt eine mission. für test wird eine charta geschrieben.. minimalistisch, formell, möglichst ununterbrochen ungestört sich auf testcharta fokussiert, time-boxed: 1-2h, wenn länger wirds in nächste session verschoben => auch im agilen. ! aufgetretenene fragen und bedenken! -> schöne idee ('iwas sieht hier komisch aus'). am schluss: debriefing nach PROOF. vorteil: gute strukturierung. wird von facharbeitern als hilfe empfunden... nachteil formeller aufwand

 Umfrageergebnisse:
 ===
  * grobe testfälle
  * zufallstest: immerhin: 30%...
  * übersicht mit vorsicht zu genießen

  testausführung
  ===
   * wer testet den tester?
   * eigene testfallbibiothek, die meist gar nicht komplett ausgeführt wird, vllt beim ersten mal
   * zB smokeTest
   * der TESTDIRECTOR !!! ich glaub ich kack in den kübel...
