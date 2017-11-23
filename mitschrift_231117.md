Testfallerstellung
===
 letztes Mal -> gefehlt...
 **Testfall**
  *bsp login: ein test ist nur eingabe des namens

 **granularität von testfällen**
  *zB Bestellhistorie testen -> angemdlet sein -> vorbedingung: nutzer ist angemeldet. das ist dann kein testschritt, sondern halt eine vorbddingung
  *erwartete ergenbisse: alles reinschrieben

**konzentration auf ddas testpbjekt:**
  *nromalfälle: beschriebt funktionailtätso dar, wie progrmam fnktionieren sollte
  *sonderfälle: sollen acuh zum erfolg führen, aber besonderheit im code dafür notwendig
  *fehlerfälle: behandeln fehler des utzers, zB automatische eingabekorrektur, einlesen von dateien, schnittsstellen allg
  *in realität wenige normalfälle, sehr viele spezialfälle ... anpassung für code...
  *bsp eingabefeld division...

heute
===
  *Bsp Dateiexport: falsche ndung, wlches syste? windows-linux backslash-slash, sonderzeichen in dateiname, dateinamenlänge, pfadangaben im namen, wie groß kann datei sein?, erfolgsmeldung nach vollendung oder abbruch oder progressIndicator so was?, speicherplatz geht auf zielsystem aus..., unterschiedliche codierungen,unterschiedliches verhalten von os' bei sehr velen dateien im ordner, caseSenisitive oder nicht?, speichern mit 'enter' triggern oder tabben?, codebefehle in dem dateinamen -> hackbar, falsche eingabe triggert welches verhalten?, ... siehe skript füe weitere fälle
  *immer auf sonder- unf fehlerfälle tessten
  *wichtige, weniger wichtige , gar nicht wichtige testobjekte äkategorisierung
  *fehlerfall-definiton ist eindeutg, sonderfallist vom denkmodell abhängig
  *menschliche eigenschaften: was kann schiefgehen?, wie arbeitetes?, qualität und erfahreung kann man nicht einfach dokumenieren, gute vorstellung was im rchner aassiert, so auch geschäftsanwendungen, **sinnvoll dauerhaft in einem projekt zu bleiben** @dotSource
  *knonkrete testabdeckung hängt von der individuellen genauigkeit ausdauer und kreativität ab.. -> Problem in der praxis... idee der testpatterns für onkrete anwendungen (zb dateiexport), bei standardmustern aber acuh wieder von individuellen aufwand abhängig => mehrere leute sollten drauf gucken
  *testabdeckung~persnen: umgekehrt logarithmische kurve --> meistens leicht erhöhte anzahl köpfe am effektivsten
  *komm ich an den testcode ran?
  *nicht in die tiefe gehen -> erst breite testabdeckung... erst ein paar normalfälle, nicht mir spezialfällen anpassen, das wär dann schon ein smoke test, einige obligatorische testts!, also vom allgemeinen zum speziellen gehen
  *priorisierung: gerne auch nach anderen kriterien! es gibt eine ganze menge! zB testobjekte, nicht nach einzelnen testfällen, oder vorgegbene anforderungen! prima..., oder qualitäätsmerkmale, effizients vor sicherheit, wie schwer könen otentielle fehler sein?, tester muss system im detail kennen ...(träum weiter) **wahrscheinlichkit von fehlern -> wo ist risiko besonder hoch RBT risk-based testin** => das macht der testManager
  *programmers pet: programmierer wollen bereiche ändern, sdie sie momentan gar nicht ändern sollen aber wollen, heißt auch uBoot, vertrauen ist gut - kontrolle ist besser..., 

Ökonomie des testens
======
======
  *wieviel test ist sinnvoll? wie hoch ist aufwand? vs sind fehlerkosten in der nutzung?, solange die kosten der qs geringer sind, als die der schäden, dann ist das gut
  *fehlerkosten im betrieb: oparitv: unmittelbar , messbar vs strategisch: fehler auf lange sicht, ...neuüberlegung der anforderungen...
  *je eher fehler gefunden wird, desto billiger, langsames exponentielles wachstum, 
  *QS-aufwand: wie hoch wäre sinnvoller aufwand für eine systemänderung?
    *alles geht nicth starkes exponentielles wachstum je mehr getesete gebaut werden soll..., -> unglaublich hoher aufwand...,
      *FDIV-bug bei intel: in bestimmten dividend/divisor kombination stimmen ergebnisse nicht... fehler in floatingpoint unit-> weltweiter austausch, es müssten alle möglichen werte getestet werden..., ergebnis muss gut vergleihbar sein, tests sind immer nur stichproben, es gibt kein perfektes testing,  
 *niemals sagen, dass man vollständig geteste hat!


sytematische testfallermittlung
===
===
 *referenzklassen erst mal auf papier schreiben.. mindesten sauf kopf
 *betrachte erst ein einziges atom, zB eingaben...
 *beispiel 1:versandkosten steigen in usa proprtional zum warenpreis aber in deutsfhcland fällt ->grenzwertanalyse
 *beispiel2: ...
