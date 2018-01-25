scrum
===

transparenz: jeder kann alles sehen, alle mögen sich...
Ziel: sprints(2 wochen um eine auslieferbare sw herzustellen, nicht komplett fertig - auf branches)
  * d.h. feature branches: features befinden sich dann schon im produkt, sind aber noch nicht aktiviert
  * damit kunde immer den aktuellen stand sehen kann
scrum-rahmenwerk:
  * po: verantwortlich für das produkt
  * scrum master: zeremonienmeister (mderiert ereignisse, teamunterstützung)
  * entwicklungsteam
  * ereignisse:
  * sprint planning:
    * forecast: verhersage was in dem sprint alles fertig wird
        * tasks max 8 stunden aufwand
  * daily scrum...
  * sprint review, sprint retroperspective(was lief gut/schlecht/ was verbesern?)
  * timeboxed: max acht stds...

definition of done...
user stories: "als <wer> möchte ich <was> haben, um <...>"
...

sprint backlog
  * idealerweise gibt es ein sprint ziel. (dann arbeiten alle an einem thema)
  * drei spalten: todo, in progress, done
    * auf tested wird manchmal verzichtet, befindet sich dann zu 'in progress'
  * gegliedert nach themen (bestehena aus tasks, bugs, noch nicht deploytes)

daily scrum
  * störung im tagesablauf, daher morgens
  * meist im stehen, damit es shneller geht
  * 15 min länge, geht auch in großen teams
  * "was habe ich gestern erledigt, was uns weiterbringt; was habe ich heute vor?..."
  * rederecht: entwicklungsteam und scrum master, product owner darf zuhören
  * sprint burn-down chart: soll-ist (wieviel ist noch vor mir?)
    * y-achse: in stunden(unbeliebt) -> daher story points(ist das was man an einem tag schaffen kann), meist einfach anzahl der tasks
  * burn-up-diagramme als alternative (zeigt an, was schon geschafft wurde)
  * oft mit zacken nach oben: wenn man sieht, dass man doch mehr machen muss
  * als motivation

impediment backlog
  * vom scrum master geplefte liste der hndernisse
  * meistnes weggelassen
  * alles was die arbeit behindert, bspw ich hab keinen rechner um die sw aufzusetzen, zugänge fehlen, zu wenig ram, mangelnder input von anderen teams/kundenvertretern
  * -> scrum master betreut meist meherer teams

  sprint review:
    * zB alle teams gleichzeitig, oder jedes team für sich
    * max 2 std länge, idr demos oder kurze stichpunktliste

  sprint retroperspective:
    * freitags kein sprint-ende... danach fängt neuer sprint an
    * ...

  agile qa - erster testdatensatz
  ===
  * fokus beim testen zu schmal -> meherere test-maßnahmen von nöten
  * scrum kennt keine tester! (scrum will keine rollen haben)
  * es wird nie das GANZE scrum-system umgesetzt
  * alle scrum-teams haben inzwischen einen tester mit in das team integriert

  tester im entwicklungsteam
  ===
  * testaufwand so größer als entwicklungsaufwand
  * tester sind im idealfall spezialisten und geben konstruktive maßnahem den entwicklern mit auf dem weg (... träum weiter ...)
  * whole team approach! -> das ganze team ist für quali verantwiortlich

  * fehler: sprint freitags zuende..
  * bei umstellung auf scrum fallen fast alle alten rollen weg
  * tester sollten nicht schüchtern sein
  * alle im selben raum / etage für kurze wege
  * code review: "don't waste your time with code review"
  *  tester bekommt weitere aufgaben rg deployment auf testsysteme
  * übergreifendes qs-team macht manchmal sinn.
