# Das Berechnungsschema

## Inhaltsverzeichnis
* [1.0 - Berechnung der absoluten Wahrscheinlichkeiten](#calculate-global-prop)
* [2.0 - Berechnung der Kosten und Ressourcen-Auslastung je Task](#calculate-task-costs)

## <a name="calculate-global-prop">1.0 - Berechnung der absoluten Wahrscheinlichkeiten</a>

**Herleitung**

Für die Berechnung der Kosten und Ressourcen-Auslastung ist die Wahrscheinlichkeit entscheidend, mit der ein Task innerhalb eines Prozesses ausgeführt wird
(globale Wahrscheinlichkeit). Diese Wahrscheinlichkeit muss vorgegeben werden. Dazu eignen sich folgende Ansätze:
* Process Mining
* REFA Messung
* Expertenschätzung

Speziell bei der Expertenschätzung und bei komplexen Prozessen (mit sich mehrfach teilenden, geschachtelten oder rekursiven Pfaden) ist das Vorgeben der
(globalen) Wahrscheinlichkeit für alle Tasks eine durchaus anspruchsvolle Aufgabe.
Deshalb werden in Symbio keine globalen Wahrscheinlichkeit erfasst, sondern die jeweiligen zum Kontext bezogenen Wahrscheinlichkeiten (lokale
Wahrscheinlichkeiten).

Alle Start-Ereignisse bilden einen gemeinsamen Kontext und für alle Start-Ereignisse muss die lokale Wahrscheinlichkeit vorgegeben werden.
Jede Teilung des Prozesspfades an einem Gateway ist ebenfalls ein eigener Kontext und für alle Pfade (Conditions, Intermediate Ergeignisse, Tasks)
muss die lokale Wahrscheinlichkeit vorgegeben werden.

Im Zuge der Berechnung der Kosten und Ressourcen-Auslastung werden dann die lokalen Wahrscheinlichkeiten automatisch (per Monte-Carlo-Simulation =
Gleichverteilung) in globale Wahrscheinlichkeiten umgerechnet.

Dadurch ist es nicht erforderlich, Wahrscheinlichkeiten an Zusammenführungen von Prozesspfaden vorzugeben - was die Datenerfassung insbesondere bei
Rückschleifen (rekursive Pfade) erheblich vereinfacht.


![warning](media/warning.png)

<img src="media/warning.png" />

<span class="warning" style="background-color:#ffff00;">
| ![warning](media/warning.png) | AA |
</span>
  
<table>
<tr class="hint" style="background-color:#ffbb44;">
<td>![hint](media/hint.png)</td>
<td>BB</td></tr>
</table>

## <a name="calculate-task-costs">2.0 - Berechnung der Kosten und Ressourcen-Auslastung je Task</a>

Kosten und Auslastung von Ressourcen entstehen nur an Tasks. Ereignisse, Gateways und Conditions tragen per definition nicht zu Kosten und
Auslastung von Ressourcen bei.

Die Kosten an den Tasks werden aus den Kostensätzen der Ressourcen berechnet, indem die Kostensätze je Stunde mit den Zeiten und Häufigkeiten der Tasks
multipliziert werden und die Kosten je Einheit mit den Häufigkeiten der Tasks multipliziert werden.

Ressourcen-Auslastungen an den Tasks werden aus den Zeiten und Häufigkeiten der Tasks berechnet und
die Ressourcen-Verbräuche werden aus den Häufigkeiten der Tasks berechnet.

### <a name="calculate-global-prop">2.1 - Berechnung der Standard-Kosten und Standard-Ressourcen-Auslastung</a>
