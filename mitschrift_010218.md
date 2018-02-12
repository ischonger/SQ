TDD, BDD, ATDD
====

test driven development
===
  * erst der test, dann der code => code passt sich den tests an
  * ? für jede methode ein testfall? und für funktionskombinationen?
  * tdd soll abhängigkeiten vermeiden
  * bessere übersicht was schon implementiert wurde und was nicht
  * psychologischer effekt eines grün ausgeführten tests...

behaviour driven development
===
  * in szenario-files formuliert, tools wandeln das dann in leeren code (funktionsrümpfe) um
  * weiterentwicklung aus ttd
  * tester, po, pm oder kunde der kein code lesen kann hat nix davon
  * gwt(given, when, than): mit **AND** können ereignisse spezifiziert werden. mit synonymen können formulierungen gespart werden
    * irgendwann werden die einzelnen fälle zu kompliziert
  * bdd hat ansonsten die selben nachteile wie tdd
  * die ersten testfälle sind dann wie in stein geeißelt. das schränkt weitere tester in programmeriung ein
  * kunde... versteht den code: sonst kein vorteil. der, der den code schreibt, schreibt auch das BDD
  * im grunde ist BDD nur die anleitung dafür code zu kommentieren

acceptance test driven development
===
  * kannste vergessen
  * entwickler, kunden, po, tester schreiben alle zusammen BDD
  * im prinzip das selbe. andere sprachen-tools, ansonsten genau so.
  * wird noch schneller noch unübersichtlicher
  * sehr untrschiedlcihes verständnis.
  * unterschiede zu BDD __kontrovers diskutiert__
  * formulierung kommt von anfoederungssicht -> pyramide dreht sich um...


lastTests
======

was ist ein lastTest
====
  * versucht typische programmierschwierigkeiten zu erreichen (deadlocks,...)
    * race conditions: zB. wenn zwei threads auf die gleiche ressource zugreifen
  * wird durchaus ins lastenheft geschrieben, als nichtfunktionale anforderung (wann ist die anwendung noch schnell genug? ... schwierig..., bedingungen sehr vielfältig)

simulation von web-lasttest
====
  * weniger: was sind typische nutzerverhalten mehr: die mischung aus mehreren nutzerverhalten
  * mithilfe von analysetools erstellt
