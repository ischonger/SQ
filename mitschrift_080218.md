genauigkeit der lastsimulation
===
  * nicht perfekt, nur nahe genug ran kommen
  * prognosegestützt
  * calculation sheets: beo ortzenario sind x suchanfragen, bei anderem szenario y => summe bilden
  * session-mäßig aufgebaut

vorgehensweise bei lastTests
======
  * systm muss funktional fertig sein (checkliste für den kunden, was sie alles bereitstellen müssen)
  * meist auf live-system: payment-accounts sind schwierig anzulegen, mocking?
  * zeitaufwändig durch viele verbesserungsiterationene des produktcodes => so früh wie möglich beginnen
  * testplanung:
    * lasttests bei kundenkonkurrentetn sind verboten^^
    * ziele: gibt es **graceful relegation**? => es läuftunter last langsamer, aber vertretbar
    * black friday: nicht wegen  börsencrash, sondern weil der erste tag im jahr an dem amazon uä schwarze zahlen schreiben
    * bei salesforce kein stresstest möglich (ist ja dauerhaft live für alle kunden)
    * szenarien:
      * validierung: sut(system under test), unter welchen kriterien würde ein _mensch_ sagen, dass der test erfolgreich war?
    * lastmodelle: probeläufe notwendig!, wieviele pseudo-nutzer schafft das system in einer gewissen zeit?, vergleich von unterscheidlichen codeständen
    * plateaus: eine weile lassen, damit das system sich auf die neue last einstellen kann ('System ist noch kalt' - es wurden noch nicht alle daten geldaen, noch nicht alle threads sind da...) => anlaufen hat ein paar minuten zeit
  * testdurchführung: iterationen (kann übersprungen werden)
  * man kann nie von einem kleinen test hochrechnene: bweitere ottlenecks können auch erst unterer höherer last entstehen
  * testreports: wie stehen wir im vergleich zum konkurrenten? -> wertung der reports notwendig -> mapping
  * agenten aus images (betriebssystemabbilder) von amazon oder google cloud
  * patterns optional

  * 
