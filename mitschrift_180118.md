Mitschrift 18.01.2018
======

Aglie Tests: Tester im Team
===
 * entwickler:tester = 3:1 sehr hoch
 * tests könnten sonst nicht in der dod sein, daher testkollegen im team, damit man planen kann
 * whole team apporach das team ist für alles zuständig, entwickler sind nciht fertig, wenn sie den code an den tester abgegeben haben
 * tester haben im idealfall einfluss auf den programmcode, so aus alten modellen (zb wasserfallmodell)
 * am anfang vom sprint wissen tester meist gar nicht, was sie machen sollen
 * tagtägliche kooperation mit entwicklern, große soziale herausforderung: am anfang große unklarheiten, vorgehensweisen müssen erst gefunden werden
 * technisch fit sein, damit man als tester akzeptiert wird: tester steht dem entwiklern auch beratend für die implementierung zur verfügung

 QS in Scrum
 ===
  * tester nimmt an allem gleichberechtigt teil
  * diskutieren: was ist leicht zu implementieren, aber schwer zu testen
  * im sprint review: oft präsentieren tester selbst, weil die mehr überlick haben

  * test-in-cycle vs out-of-cycle:
    * out-of: im ersten sprint implementieren, im 2. erst testen, dann im dritten in die produktion
    * in-cycle: alles in einem sprint
    * erst auslieferbar, wenn dod erreicht ist
    * in einem sprint werden nie alle fehler gefixed
    * im dod: welche fehler dürfen noch drinne sein und welche nicht?
    * **keinen aufwand in den nächstne sprint verschieben**, sonst hat man keinen klaren endpnkt, sonst rutscht immer noch iwas rein => "hardening sprint" oder "end sprint" zusätzliche qs. aber eigtl am sprintende immer fertig/auslieferbar präsentieren
    * => scrum fordert eigtl test-in-cycle, entscheidung hängt also mit der dod zusammen
    * entwickler sind testern im fortschritt nicht voraus (in test-in-cycle)

zeitplanung
===
 * logische testfälle erstellen, abstrakter
 * mini-wasserfall im sprint vermeiden
 * absprechen was noch gehen soll und daran entscheiden, ob ein fehler noch aufgetreten ist oder nicht
 * nicht alles paralell machen, sondern motivieren, dass immer alles stückweise fertig wird => besser für zusammenarbeit
 * möglichst minimalistische soll-nforderungen der tickets ermöglichen
 * beisst sich das nicht mit dem ticket-system? ticket gibt doch eindeutig an, wer gerade die zuständigkeit hat ???

 definition of test (dot)
 ===
  * welche konstruktive qs maßnahemen gibt es?
  * welche tools... alle genauen anforderungen halt definiert
  * gegliedert nach code stosy integrationund release ebene
  * definerit nicht tiefer als code ebene
  * continuos integation
  * ebenen:
    * code ebene
    * story ebene: automatisierte tests nicht zu früh implementieren, weil der code sich eh noch ständig ändert
    * integrationsebene: schaut, was alles so zusammenspielt, mit endnutzern
    * release ebene
    * für jede ebene eine dot, dod

continuos integration
===
 * produkt entsteht dadurch, dass funktionierender code immer sprintweise hinzugepushed wird
 * über zentrales code repository, entwickler können sich immer den aktuellen code holen
 * es können automatisierte tests durchgeführt werden
 * kurze commit-intervalle
 * => verbesserte sw-qualität
 * tools instrumentieren den code, dadurch wird code angereichert beim test, danach sieht man wo es noch keine automatisiereten tests gibt
 * code wuality management: schauen auf quellcode, liefert mögliche fehler... zb zu viele zeilen pro klasse
  * spezialisiert zT auf sicherheit
 * max 10 min laufzeit, praktisch aber schwierig, oft parallelisierung notwendig
 * so immer garantiert, dass der aktuelle code geprüft wird
 * zB jenkins, teamCity, ...

 continuos delivery
 ===
  * sw in kleinen portionen ausrollen, enge zzusammenarbeit mit entwicklern und denjenigen die das produkt zB installieren, heißt also auch das man ständig für den kundne da ist und betreut, manuele schranken ermöglichen
  * dev ops: die, die den kunden ünterstützen, oft geht es ja auch schief, wenn fertig entwickelt wurde; so geht es aber besser
  * produkt verbessert sich auch noch nach release
  * wann ist ein produkt fertig? ^^ wenn's live ist?^^
  * nach release auch noch al manuelle tests
  * "don't roll back, roll forward"
