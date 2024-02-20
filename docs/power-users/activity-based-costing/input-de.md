# Bereitstellung von Eingabedaten

Zur Verdeutlichung der Vorgehensweise bei der Prozesskennzahlenanalyse im Sinne einer **Activity-Based-Costing** Berechnung wird an verschiedenen Stellen in diesem Dokument ein Beispil-Prozess (Merchandising-Feuerzeug "Senator") bemüht.
Für diesen Beispil-Prozess wurde ein Fertigungsprozess mit von 1 verschiedener Losgröße und mehreren [Mengenindikatoren](https://de.wikipedia.org/wiki/Indikator_(Wirtschaft)#Mengenindikatoren) gewählt. Solche Prozesse sind die anspruchsvollste Form der Prozesskennzahlenanalyse.

![hint](media/hint.png) Fertigungsprozesse laufen häufig in Fertigungslosen und mit wechselnden Mengenindikatoren ab, während Büroprozesse in der Regel Einzelvorgänge sind, bei denen die Losgröße immer eins und die Anzahl Lose der einzige Mengenindikator des betrachteten Prozesses ist.

![hint](media/hint.png) Wechselnde Mengenindikatoren müssen in der Symbio Prozesskennzahlenanalyse immer auf die Einsatzmenge (entspricht der Anzahl Prozessstarts) bezogen sein. Anderenfalls wäre die Einführung von Kostentreibern erforderlich gewesen und das hätte die Prozesskennzahlenanalyse erheblich komplexer gemacht.

## Inhaltsverzeichnis
* [1.0 - Eingabedaten auf Prozess-Ebene](#inputdata-on-diagram)
  * [1.1 - Erläuterung der Eingabedaten auf Prozess-Ebene](#inputdata-on-diagram-terms)
  * [1.2 - Interpretation der Eingabedaten auf Prozess-Ebene](#inputdata-on-diagram-interpretation)
  * [1.3 - Prozess-Informationen im Beispiel](#inputdata-on-diagram-sample)
* [2.0 - Eingabedaten auf Ebene der Struktur-definierenden Elemente eines Prozesses](#inputdata-on-structures)
  * [2.1 - Eingabedaten für Ereignisse, Gateways und Conditions](#inputdata-on-structures-events)
  * [2.2 - Eingabedaten für Tasks](#inputdata-on-structures-tasks)
  * [2.3 - Eingabedaten für Prozess-Schnittstellen und Szenarios](#inputdata-on-structures-interfaces)
* [3.0 - Eingabedaten auf Ebene der Glossar-Elemente eines Prozesses](#inputdata-on-glossaries)
  * [3.1 - Eingabedaten für Rollen](#inputdata-on-glossaries-roles)
  * [3.2 - Eingabedaten für Applikationen](#inputdata-on-glossaries-apps)

## <a name="inputdata-on-diagram">1.0 - Eingabedaten auf Prozess-Ebene</a>

![ABC-inputdata-on-diagram_DE](media/ABC-inputdata-on-diagram_DE.png)

### <a name="inputdata-on-diagram-terms">1.1 -Erläuterung der Eingabedaten auf Prozess-Ebene</a>

* **Zeitraum** - Der Betrachtungszeitraum zur Analyse von Prozesskosten. Die Angaben zur Losgröße und die Anzahl der Lose beziehen sich auf den Betrachtungszeitraum.
  * Der Betrachtungszeitraum ist rein informativ und hat keinen Einfluss auf das Berechnungsergebnis.
* **Anzahl Lose** - Die Anzahl Lose multipliziert mit der Losgröße ergibt die Einsatzmenge (Anzahl Prozessinstanzen).
  * Ein Los wird ohne Unterbrechung abgearbeitet.
  * Einarbeitungsaufwand, Transportaufwand und Wartezeiten entstehen nur einmalig für jedes Los.
* **Losgröße** - Ein Los wird ununterbrochen abgearbeitet.
  * Die Anzahl Lose multipliziert mit der Losgröße ergibt die Einsatzmenge (Anzahl Prozessinstanzen).
* **Direkte Gemeinkosten** - Direkte Gemeinkosten (unechte Gemeinkosten) sind die Kosten, die durch die allgemeine Verfügbarkeit des Prozesses entstehen. Sie sind unabhängig von der tatsächlichen Prozessausführung, aber eindeutig dem Prozess zuzuordnen (z. B. Modellbau/Prototyp oder Zulassung, unter Umständen auch Energie oder Miete für nur von diesem Prozess genutzte Ressourcen). Sie sind Fixkosten und werden jeder Berechnung einmalig zugeschlagen.
 * Die direkten Gemeinkosten gehen in die Fixkosten ein.
* **Indirekte Gemeinkosten** - Indirekte Gemeinkosten (echte Gemeinkosten) sind die Kosten, die für die ununterbrochene Aufrechterhaltung des Geschäftsbetriebs notwendig sind, dem Prozess aber nicht direkt zugeordnet werden können (z. B. Versicherung oder Steuern). Sie sind Fixkosten und werden jeder Berechnung einmalig zugeschlagen.
  * Die indirekten Gemeinkosten gehen in die Fixkosten ein.
* **Zugewiesene Einzelkosten je Prozessinstanz** - Zugewiesene Einzelkosten sind die Kosten, die einem Prozess auf Basis einer Kostenträgerstückrechnung (z. B. Divisionskalkulation) zugewiesen werden. Sie sind nicht wie die Einzelkosten eines Prozesses aus prozessspezifischen Ressourcenverbräuchen und -nutzungen berechnet, entstehen aber ebenso erst bei der Ausführung des Prozesses. Sie sind variable Kosten und werden jeder Prozessinstanz zugeschlagen.
  * Die zugewiesenen Einzelkosten gehen in die Fixkosten ein.

### <a name="inputdata-on-diagram-interpretation">1.2 - Interpretation der Eingabedaten auf Prozess-Ebene</a>

Es soll beispielhaft angenommen werden, dass eine [Kostenträgerstückrechnung](https://de.wikipedia.org/wiki/Kostentr%C3%A4ger#Kostentr%C3%A4gerst%C3%BCckrechnung) zur Berechnung der Selbstkosten eines Produktes (Merchandising-Feuerzeug "Senator") durchzuführen ist. Dazu bietet sich folgendes Vorgehen an:

| Kalkulations-Schema	| In der Symbio Prozesskennzahlenanalyse umgesetzt als |
|---------------------|------------------------------------------------------|
|   [Materialeinzelkosten](https://de.wikipedia.org/wiki/Materialeinzelkosten) (MEK)<br/>(Fertigungsmaterial)	| System, Kostensatz je Stück („System“ = Material) |
| +	[Materialgemeinkosten](https://de.wikipedia.org/wiki/Materialgemeinkosten)<br/>(Einkauf, Verpackung, Fracht, Warenannahme, Lager, …)	| Direkte Gemeinkosten  |
| =	***Materialkosten*** | |	
| +	[Fertigungseinzelkosten](https://de.wikipedia.org/wiki/Fertigungskosten) [1] (FEK)<br/>(Fertigungslöhne, Maschinen-/Anlage-Kosten)	| Rolle, Kostensatz je Stunde<br/>System, Kostensatz je Stunde |
| +	Maschinenabhängige Gemeinkosten [1]<br/>(kalkulatorische Zinsen/Abschreibungen)	| Direkte Gemeinkosten |
| +	[Fertigungsgemeinkosten](https://de.wikipedia.org/wiki/Fertigungskosten) (FGK)<br/>(Hilfsstoffe, Energie, Löhne der Meister/Ingenieure, …)	| Indirekte Gemeinkosten |
| +	[Sondereinzelkosten Fertigung](https://de.wikipedia.org/wiki/Fertigungskosten#Sondereinzelkosten_der_Fertigung) (SEKf)<br/>(Modelle, Schablonen, Vorrichtungen, …)	| Zugewiesene Einzelkosten |
| =	***Herstellkosten*** | |	
| +	[Verwaltungsgemeinkosten](https://de.wikipedia.org/wiki/Verwaltungsgemeinkosten) (VwGK)<br/>(Kosten der Leitung/Verwaltung des Unternehmens)	| Indirekte Gemeinkosten |
| +	[Vertriebsgemeinkosten](https://de.wikipedia.org/wiki/Vertriebsgemeinkosten) (VtGK)<br/>(Fertigwaren Lager, Verkaufsbüros, Werbung)	| Indirekte Gemeinkosten |
| +	[Sondereinzelkosten Vertrieb](https://de.wikipedia.org/wiki/Sondereinzelkosten) (SEKv)<br/>(Verpackung, Fracht, Zoll, Händlerprovision, …)	| Zugewiesene Einzelkosten |
| =	***Selbstkosten*** | |	

[1] Maschinen/Anlagen, für die **Kostensätze** verfügbar sind, können als Systeme an die Prozess-Funktionen modelliert werden und gehen so in die Fertigungseinzelkosten ein. Die anderen Maschinen/Anlagen müssen über **Direkte Gemeinkosten** abgebildet werden und gehen so in die Maschinenabhängigen Gemeinkosten ein.

### <a name="inputdata-on-diagram-sample">1.3 - Prozess-Informationen im Beispiel</a>

Der Beispielprozess (Merchandising-Feuerzeug "Senator") ist für eine **Losgröße** von 500 Teilen und eine **Anzahl Lose** von 4 im **Betrachtungszeitraum** 20 Arbeitstage / 28 Kalendertagen (ein Monat) definiert. Es ergibt sich also eine Anzahl Prozessstarts bzw. eine **Einsatzmenge** von 500 * 4 = 2000.

![warn](media/warn.png) Für Funktionen, die an jedem Produkt durchgeführt werden müssen, beträgt die Eintrittswahrscheinlichkeit somit 2000 Teile (Einsatzmenge) / 2000 Teile (Einsatzmenge) = 100% oder 1,0.

Im Beispielprozess treten darüber hinaus Mengenindikatoren für die Bereitstellung des Materials und der Versandverpackungen auf.

Die Materialbereitstellung erfolgt je ein Mal pro Los. Der Mengenindikator, bezogen auf die Einsatzmenge, ist also 2000 Teile (Einsatzmenge) / 500 Teile je Los (gleichzeitig bereitgestellte Menge) = 4.

![warn](media/warn.png) Für Funktionen, die an jedem Los durchgeführt werden müssen, beträgt die Eintrittswahrscheinlichkeit somit 4 Lose / 2000 Teile (Einsatzmenge) = 0,2% oder 0,002.

Die Handhabung der Versandverpackung erfolgt ein Mal pro 25 Teile. Der Mengenindikator, bezogen auf die Einsatzmenge, ist also 2000 Teile (Einsatzmenge) / 25 Teile (in einer Versandverpackung befindliche Menge) = 80.

![warn](media/warn.png) Für Funktionen, die an jeder Versandverpackung durchgeführt werden müssen, beträgt die Eintrittswahrscheinlichkeit somit 80 / 2000 (Einsatzmenge) Teile = 4% oder 0,04.

Dem Beispielprozess sind weiterhin **Direkte Gemeinkosten** (unechte Gemeinkosten) in Höhe von 1200,00€, **Indirekte Gemeinkosten** (echte Gemeinkosten) in Höhe von 875,00€ und **Zugewiesene Einzelkosten** in Höhe von 245,00€ zugeordnet.

![warn](media/warn.png) Für alle bisher eingeführten Prozesskennzahlen (Betrachtungszeitraum, Anzahl Lose, Losgröße, Direkte Gemeinkosten, Indirekte Gemeinkosten und Zugewiesene Einzelkosten) sind Hilfetexte ![info-icon](media/info-icon.png)  verfügbar.

## <a name="inputdata-on-structures">2.0 - Eingabedaten auf Ebene der Struktur-definierenden Elemente eines Prozesses</a>

### <a name="inputdata-on-structures-events">2.1 - Eingabedaten für Ereignisse, Gateways und Conditions</a>

![ABC-inputdata-on-events_DE](media/ABC-inputdata-on-events_DE.png)

* **Relative Wahrscheinlichkeit** - Die relative Wahrscheinlichkeit (lokal) zur Analyse von Prozesskosten. Bitte geben Sie die Eintrittswahrscheinlichkeit als Fließkommazahl an. 1,0 entspricht 100%. Die Eintrittswahrscheinlichkeit muss nur für Startobjekte und Objekte direkt nach teilenden Regeln angegeben werden.

### <a name="inputdata-on-structures-tasks">2.2 - Eingabedaten für Tasks</a>

![ABC-inputdata-on-tasks_DE](media/ABC-inputdata-on-tasks_DE.png)

* **Relative Wahrscheinlichkeit** - Die relative Wahrscheinlichkeit (lokal) zur Analyse von Prozesskosten. Bitte geben Sie die Eintrittswahrscheinlichkeit als Fließkommazahl an. 1,0 entspricht 100%. Die Eintrittswahrscheinlichkeit muss nur für Startobjekte und Objekte direkt nach teilenden Regeln angegeben werden.
* **Ø Bearbeitungszeit** - Die Bearbeitungszeit zur Analyse von Prozessleistung. Die Bearbeitungszeit ist die Zeit, während der Ressourcen für die Bearbeitung eines Vorgangs/Werkstücks im Los gebunden werden.
* **Ø Liegezeit** - Die Liegezeit zur Analyse von Prozessleistung. Die Liegezeit ist die Zeit, während der ein Los auf eine Zuteilung von Ressourcen wartet.
* **Ø Einarbeitungszeit** - Die Einarbeitungszeit zur Analyse von Prozessleistung. Die Einarbeitungszeit (oder auch Rüstzeit) ist die Zeit, während der die Voraussetzungen zur Bearbeitung eines Loses geschaffen werden.
* **Ø Übertragungszeit** - Die Übertragungszeit zur Analyse von Prozessleistung. Die Übertragungszeit ist die Zeit, während der ein Los an die nächste Arbeitsstation weitergegeben wird.
* **Ø Durchlaufzeit** - Die Durchlaufzeit zur Analyse von Prozessleistung. Die Durchlaufzeit ist eine Kombination aus Bearbeitungszeit, Liegezeit, Einarbeitungszeit und Übertragungszeit, bezogen auf einen einzelnen Vorgang/Werkstück.

### <a name="inputdata-on-structures-interfaces">2.3 - Eingabedaten für Prozess-Schnittstellen und Szenarios</a>

![ABC-inputdata-on-diagram_DE](media/ABC-inputdata-on-diagram_DE.png)

Erläuterungen siehe [1.1 - Erläuterung der Eingabedaten auf Prozess-Ebene](#inputdata-on-diagram-terms).

## <a name="inputdata-on-glossaries">3.0 - Eingabedaten auf Ebene der Glossar-Elemente eines Prozesses</a>

### <a name="inputdata-on-glossaries-roles">3.1 - Eingabedaten für Rollen</a>

![ABC-inputdata-on-roles_DE](media/ABC-inputdata-on-roles_DE.png)

* **Kostensatz (je Stunde)** - Der Kostensatz je Stunde Tätigkeitszeit.

### <a name="inputdata-on-glossaries-apps">3.2 - Eingabedaten für Applikationen</a>

![ABC-inputdata-on-apps_DE](media/ABC-inputdata-on-apps_DE.png)

* **Kostensatz (je Stunde)** - Der Kostensatz je Stunde Tätigkeitszeit.
* **Kostensatz (je Einheit)** - Der Kostensatz je Einheit.
