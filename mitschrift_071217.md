Testausführung
======
re-test
===
  * auch mit den Leuten reden, die den fehler eingestellt haben
  * entwickler schauen nur auf die fehlerstelle -> schwierig bei komplexen zusammenhängen, -> zeitnah re-testen

hinweise zur testausfüTestausführung
===
 * die meisten fehler werden gefunden, weil jemandem etwas auffällt.
 * keine zeit / budget für aufwändige tests, tester muss ahnen, wo der fehler ist
 * bspw passwort: auch prüfen, dass man nicht mit falschem pw reinkommt
 * variationen: grenzwerte zB sollten nicht variiert werden, eher: versch wege testen

 Fehlerverfolgung
 ======
 * als tester müssen gefunden fehler kommuniziert werden -> tools
 * man muss sich drum kümmern, dass nach dem finden sich auch jemand um den fehler kümmert.
 * fehlerprozesse in praxis sehr unterschiedlich. meist sind die prozesse viel größer, als das was man zeigt, umgebungen müssen mit getrackt werden, ist es jetzt auf testumgebung?, wurde der test jetzt begonnen?, ist noch mal nachgetestet worden?... viele unterschiedliche mglkts...
 * fehlereinträge sind sehr wichtiges kommunikationsmittel... meistens das einzige! bei weltweiter vernetzung ist das schon remarkable, man tritt mit den programmieren gar nicht wirklich in kontakt

 einfacher fehlerprozesse
 ===
  * new: jemand erzeugt neuen fehlereintrag
  * assigned: leiter weist prüfer eintrag zu. zur behebnung/ anschauung. welche zustände gibt es? dann weisen sich entwickler das selber zu. wenn gefixed wurde:
  * fixed: ncohmal testen (re-testen)
  * wenn erfolgreich: **closed**
  * ca 50% -> der entwickler muss sich noch mal drum kümmern. das geht dann hin und her, aber nicht zu oft
  * rejected: entwickler meint, dass ist kein fehler. bspw fehlen informationen zum testen. kommunikation! dann auch auf closed
  * later / deferred: "wir kümmern uns später drum" ..., sog. fehlerkorridore bspw bei telekom. bedeutet: fiel heraus aus den statistiken. macht man iwann mal. macht sich oft ganz gut.
  * alle vollst behandelten fehler sind in closed! für diese statiskten zählt nicht ob de closed oder deferred sind.
  * große zustandsmatrizen... bei großen projekten führt das zu wildwuchs, deswegen genaue einstellungen. aufpassen und überlegen was man braucht. wie komplex soll's sein? bei vielen nicht eingespielten leuten merkt man auch was gut ist und was nicht. man möchte sehen, wie ein fhlereintrag behandelt wurde. -> den grund für's schließen. man sieht nicht warum er closed ist. man erkennt an, dass es ein fehler ist.. o.ä. -> einführung von zuständen. zB defect, duplicated. das ist sehr unübersichtlich.
  * -> filter: zB welche sind noch nicht fixed... -> aber dann werden filterausstellungen immer komplexer. wie wurde der fehler behoben? <- das wird in zustl parametern gerne angehängt.
  * ... summary: zB keine markierung bei eer gelassenen textfeldern. detected by: automatisch; manchmal gar nicht konkret belegbar. version: wichtig. severity: auch wichtig bei weller 3-10 stufen, xceptance: 3-4 stufen; bugzilla: 7 voreing stufen; aber wann tritt genau welche stufe zu?; wird vom ersteller gesetzt, oft ein streitthema. detected on date:... ...
  * (fortsetzung)... priority: berechnete priority - number: zum herausfinden was wichtiger ist. reproducible: untersch handhabe: oft nur zwei stufen; oder in %; wichtig für die entwickler, um fehler zu reproduzieren; oder always, sometimes. attachments: nützlich, weil dann der fehler offensichtlicher wird. product/component/...: angabe wo der fehler vermutet wird; pronlematisch: testingenieur weiß gar nicht wo der fehler hingehört.
  * recht aufwändig. geschätzte angaben werden quasi nie ausgefüllt. link entities: dann kann man zwischen den fehlern hin und herspringen. history: wer hat wann welchen wert geändert? gibt's auch bei jira, aber da recht unübersichtlich.

  erstellen eines neuen fehlereintrags
  ===
  * meist ewrden nur duplicate-fehler gefunden. fehler schwer zu beschreiben. -> minimieren. wenn es einen eintrag gibt, der noch nicht closed ist: immer hinweise hinzugeben. wenn ein bug gefunden wurde, der mit einem bereits geschlossenem ticket zusammenhängt, dann ein neues ticet aufmachen -> weil tester merken sich die id's. delta: unterschiede zum letzten mal anschauen. wird der fehler durch fehlerhafte testdaten verursacht?
  * ... ...

fehlerbeschreibung
===
 * überschrift der tickets muss eindeutig sein. konkret.

hinweise zum eintragen von fehlern
===
 * fehler nicht sammeln. sondern immer gleich eintragen. nie davon ausgehen, dass der fehler bereits gemeldet wurde. (das denkt jeder...). schwere produzierbare fehler inetragen, wahrsch zeitbomben. auch kleinere fehler eintragen. testdatensatz nicht manipulieren, sonst könnten fehler nicht mehr reproduzierbar sein.

 fehlerkultur
 ===
 * möglichst sachlcih darstellen, keine übertreibungen. keine ausrufezeichen, ekine schuldzuweisungen, kein leider... schon wieder
 * fehler werden nur an der qualität ihrer fehlereinträge bewertet.
 * der beste tester ist der, dessen fehleinträge auch behiben werden.


 Test in agilen Prozessen
 =========
  * agile vorhergehensweise und scrum
  * agile qs - erster ansatz
  * agile qs: tester im team - heute bewährt.

  historie
  ======
   * scrum: gedränge ~ viele wollen ein ziel erreichen.
   * pioniere: japanische produktionsoptimierungen
   * 93: erstes scrum-team.
   * '01': früher immer leichgewichtig wird durch agil ersetzt.
   * 03: erste scrum-master.

   agiles manifest
   ===
    * schlimm: wasserfallmodell: alles dauert, und dann ist es nicht das was der kunde will.
    * bereits nach vier wochen große erfolge.
    * ...
    * zwölf prinzipien:
     * kundenzufiedenheit: auslierferung funktioneller sw. kunde kann sich momentanen stand immer ansehen
     * hotfixes: spontan auf änderungen/ fehler reagierbar
     * funktionelle sw schneller ausliefern. max 2 wochen. besserer feedback -> continuous delivery.
     * funktionelle sw ist das entscheidende. sonst 90%-phänomen; dem entgegenwirken.
     * nachhaltige entwcklung mit gleichmäßigem tempo: artbeitszunahme gegen deadline -> es gibt mehr fehler! max acht stunden arbeit am tag macht sinn! -> konstantes leveldesign.
      * forecast: nicht mehr sagen, dass man es schafft, sondern: wir schätzen dass ir es schaffen
     * enge zusammenarbeit von fachexperten und entwicklern.
     * direkte gespräche! sind am effektivsten.
     * umfeld!
     * technical depth: teschnische finesse in arbeitsaufwand mit betrachten
     * einfachheit: man kann nicht alles vorausplanen... dann geht schief. immer so einfach wie möglich. änder das vorhandene, wenn möglich. -> refactoring.
     * beste ergebnisse entstehen durch selbstorganisierte teams
     * regelmäßige reflexion: wie kann man besser werden. können wir anderes tool benutzen... wirklich auf kleiner ebene... 
