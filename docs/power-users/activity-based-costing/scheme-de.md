# Das Berechnungsschema

## Inhaltsverzeichnis
* [1.0 - Berechnung der absoluten Wahrscheinlichkeiten](#calculate-global-prop)
  * [1.1 - Erläuterung der Begriffe](#calculate-global-prop-terms)
  * [1.2 - Herleitung der Eintrittswahrscheinlichkeit (prozess-globale/absolute Wahrscheinlichkeit)](#calculate-global-prop-derive)
* [2.0 - Berechnung der Kosten und Ressourcen-Auslastung je Task](#calculate-task-costs)

## <a name="calculate-global-prop">1.0 - Berechnung der Eintrittswahrscheinlichkeit</a>

### <a name="calculate-global-prop-terms">1.1 - Erläuterung der Begriffe</a>
<table>
  <tr><td><b>O<sup>P</sup></b> </td><td>Betrachtungszeitraum (<b><i>O</i></b>bservation period) eines Prozesses <sup>(<b><i>P</i></b>rocess)</sup> </td><td></td></tr>
  <tr><td><b>L<sup>P</sup></b> </td><td>Losgröße (<b><i>L</i></b>ot size) eines Prozesses <sup>(<b><i>P</i></b>rocess)</sup> </td><td></td></tr>
  <tr><td><b>N<sup>LP</sup></b> </td><td>Anzahl (<b><i>N</i></b>umber) der Lose <sup>(<b><i>L</i></b>ots)</sup> eines Prozesses <sup>(<b><i>P</i></b>rocess)</sup></td><td></td></tr>
  <tr><td><b>A<sup>P</sup></b> </td><td>Einsatzmenge (<b><i>A</i></b>mount) eines Prozesses <sup>(<b><i>P</i></b>rocess)</sup></td><td>A<sup>L</sup> = L<sup>P</sup> * N<sup>LP</sup></td></tr>
  <tr><td><b>Q<sup>T</sup></b> </td><td>Häufigkeit (<b><i>Q</i></b>uantity) einer Prozessaktivität <sup>(<b><i>T</i></b>ask)</sup> </td><td></td></tr>
  <tr><td><b>P<sup>T</sup></b> </td><td>Eintrittswahrscheinlichkeit (<b><i>P</i></b>robability) einer Prozessaktivität <sup>(<b><i>T</i></b>ask)</sup> </td><td>P<sup>T</sup> = Q<sup>T</sup> / A<sup>P</sup></td></tr>
</table>

### <a name="calculate-global-prop-derive">1.2 - Herleitung der Eintrittswahrscheinlichkeit (prozess-globale/absolute Wahrscheinlichkeit)</a>
Für die Berechnung der Kosten und Ressourcen-Auslastung ist die Häufigkeit  entscheidend, mit der eine Prozessaktivität innerhalb eines Prozesses ausgeführt wird. Diese Häufigkeit <b>Q<sup>T</sup></b> ergibt sich
* für die Bearbeitung aus der Einsatzmenge <b>A<sup>P</sup></b> und der Eintrittswahrscheinlichkeit (prozess-globale/absolute Wahrscheinlichkeit) <b>P<sup>T</sup></b> und
* für Einarbeitung/Transport und Wartezeit aus der Anzahl Lose <b>N<sup>LP</sup></b> und der Eintrittswahrscheinlichkeit (prozess-globale/absolute Wahrscheinlichkeit) <b>P<sup>T</sup></b>.

Die Eintrittswahrscheinlichkeit muss zum Zeitpunkt der Berechnung verfügbar sein. Zur Ermittlung der Eintrittswahrscheinlichkeit eignen sich folgende Ansätze:
* Process Mining
* REFA Messung
* Expertenschätzung

Speziell bei der Expertenschätzung und bei komplexen Prozessen (mit sich mehrfach teilenden, geschachtelten oder rekursiven Pfaden) ist das Vorgeben der Eintrittswahrscheinlichkeit (prozess-globalen/absoluten Wahrscheinlichkeit) für alle Prozessaktivitäten eine durchaus anspruchsvolle Aufgabe.
Deshalb werden in Symbio keine prozess-globalen/absoluten Wahrscheinlichkeiten erfasst, sondern die jeweiligen auf einen konkreten Kontext bezogenen lokalen Wahrscheinlichkeiten.

Alle Start-Ereignisse bilden einen gemeinsamen Kontext und für alle Start-Ereignisse muss die lokale Wahrscheinlichkeit vorgegeben werden. Jede Teilung des Prozesspfades an einem Gateway ist ebenfalls ein eigener Kontext und für alle Pfade (definiert durch die auf Gateways folgenden Conditions, Intermediate Ergeignisse, Prozessaktivitäten) muss die lokale Wahrscheinlichkeit vorgegeben werden.

Im Zuge der Berechnung der Kosten und Ressourcen-Auslastung werden dann die lokalen Wahrscheinlichkeiten automatisch (per Monte-Carlo-Simulation =
Gleichverteilung) in Eintrittswahrscheinlichkeiten (prozess-globale/absolute Wahrscheinlichkeiten) umgerechnet.

Dadurch ist es nicht erforderlich, Wahrscheinlichkeiten an Zusammenführungen von Prozesspfaden vorzugeben - was die Datenerfassung insbesondere bei
Rückschleifen (rekursive Pfade) erheblich vereinfacht.

#### 1.2.1 Eintrittswahrscheinlichkeit für Startobjekte
Startobjekte sind alle Struktur-definierenden Prozesselemente ohne Vorgänger. Die Erfassung der lokalen Wahrscheinlichkeit für die Startobjekte ist optional.

<table><tr><td width="66px"><image src="media/warning.png"/></td><td>
Die Prozesskennzahlenanalyse geht von einer Gleichverteilung der Eintrittswahrscheinlichkeit (automatische Zuweisung der Wahrscheinlichkeit) auf alle Startobjekte aus. Ist dies nicht gewünscht, ist eine Erfassung der lokalen Wahrscheinlichkeit für die Startobjekte erforderlich.
</td>
</tr></table>

#### 1.2.2 Eintrittswahrscheinlichkeit für Startobjekte im Beispiel
Im Beispielprozess hätten dann die Startobjekte „Transportauftrag (für Los) liegt vor“ (Ereignis mit der Nr. 1) und „Fertigungsauftrag (für Los) liegt vor“ (Ereignis mit der Nr. 4) jeweils eine Eintrittswahrscheinlichkeit von 0,5. Diese automatisch berechneten Werte können jedoch nach Belieben mit einer lokalen Eintrittswahrscheinlichkeit überschrieben werden.

<table><tr><td width="66px"><image src="media/hint.png"/></td><td>
Da im Beispielprozess das Ereignis „Transportauftrag (für Los) liegt vor“ nur einmal je Los und das Ereignis „Fertigungsauftrag (für Los) liegt vor“ für jedes Produkt ausgewertet werden soll, werden die automatisch berechneten Werte mit 0,0020 und 1,0000 überschrieben.
</td>
</tr></table>

#### 1.2.3 Eintrittswahrscheinlichkeit nach zusammenführenden Regeln
<table><tr><td width="66px"><image src="media/warning.png"/></td><td colspan="2">
Die Prozesskennzahlenanalyse im Symbio Modeling Client wertet zusammenführende Regeln nicht nach logischen Kriterien aus. Die Eintrittswahrscheinlichkeit für den - einer zusammenführenden Regel - nachfolgenden Pfad ergibt sich einfach aus der Summe aller Eintrittswahrscheinlichkeiten der vorangegangenen Pfade (automatisch berechnete Werte):
</td></tr>
<tr><td></td><td width="120px">UND:</td><td>Das ist falsch. Die Eintrittswahrscheinlichkeit muss manuell angepasst werden. Sie entspricht der kleinsten Eintrittswahrscheinlichkeit aller zusammengeführten Pfade.</td>
<tr><td></td><td>ENTWEDER-ODER:</td><td>Korrekt.</td>
<tr><td></td><td>ODER:</td><td>Das ist ggf. falsch. Die Eintrittswahrscheinlichkeit muss ggf. manuell angepasst werden. Sie liegt im Bereich zwischen der kleinsten Eintrittswahrscheinlichkeit aller zusammengeführten Pfade und der Summe der Eintrittswahrscheinlichkeiten aller zusammengeführten Pfade.</td>
</tr></table>

#### 1.2.4 Eintrittswahrscheinlichkeit nach zusammenführenden Regeln im Beispiel
Die drei grundlegenden Typen zusammenführender Regeln soll noch einmal detailliert veranschaulicht werden:
<table>
<tr><td width="33%">UND</td><td width="33%">ENTWEDER-ODER</td width="33%"><td>ODER</td></tr>
<tr><td><image src="media/path-combination-with-AND.png"/></td><td><image src="media/path-combination-with-XOR.png"/></td><td><image src="media/path-combination-with-OR.png"/></td></tr>
<tr><td>zusammenf. Regel:	1.0000 &lArr; n.i.O.<br/>Ereignis 1:	0.4000<br/>Ereignis 2:	0.3000<br/>Ereignis 3:	0.3000</td>
    <td>zusammenf. Regel:	1.0000<br/>Ereignis 1:	0.4000<br/>Ereignis 2:	0.3000<br/>Ereignis 3:	0.3000</td>
    <td>zusammenf. Regel:	1.0000 &lArr; n.i.O.<br/>Ereignis 1:	0.4000<br/>Ereignis 2:	0.3000<br/>Ereignis 3:	0.3000</td>
</tr>
<tr><td>Die Eintrittswahrscheinlichkeit der zusammenführenden Regeln muss auf 0.3 (kleinsten Eintrittswahrscheinlichkeit aller zusammengeführten Pfade) geändert werden.</td><td> </td><td>Die Eintrittswahrscheinlichkeit der zusammenführenden Regeln muss auf einen Wert zwischen 0.3 und 1.0 geändert werden.</td></tr>
</table>

Im Beispielprozess hätte dann der nachfolgende Pfad nach der Regel mit der Nr. 5 eine Eintrittswahrscheinlichkeit von 0,0020 + 1,0000 = 1,0020. Diese automatisch berechneten Werte können jedoch nach Belieben mit einer lokalen Eintrittswahrscheinlichkeit überschrieben werden.

<table><tr><td width="66px"><image src="media/hint.png"/></td><td>
Deshalb wird im Beispielprozess der automatisch berechnete Wert für die Eintrittswahrscheinlichkeit der Prozessaktivität „Feuerzeug montieren“ (Prozessschritt mit der Nr. 6) mit 1,0000 überschrieben.
</td>
</tr></table>

#### 1.2.4 Eintrittswahrscheinlichkeit nach zusammenführenden Regeln im Beispiel
Im Beispielprozess hätte weiterhin der nachfolgende Pfad nach der Regel mit der Nr. 13 eine Eintrittswahrscheinlichkeit von 0,0400 + 0,9600 = 1,0000. Hier ist kein Überschrieben erforderlich.

#### 1.2.5 Eintrittswahrscheinlichkeit nach teilenden Regeln
<table><tr><td width="66px"><image src="media/warning.png"/></td><td colspan="2">
Die Prozesskennzahlenanalyse im Symbio Modeling Client wertet teilende Regeln nach logischen Kriterien aus und berechnet die Eintrittswahrscheinlichkeiten für die - einer teilende Regel - nachfolgenden Pfade wie folgt (automatisch berechnete Werte):
</td></tr>
<tr><td></td><td width="120px">UND:</td><td>Alle Pfade haben die volle Eintrittswahrscheinlichkeit der teilenden Regel.</td>
<tr><td></td><td>ENTWEDER-ODER:</td><td>AAlle Pfade haben die Eintrittswahrscheinlichkeit der teilenden Regel dividiert durch (1 + Anzahl Pfade) / Anzahl Pfade.</td>
</tr></table>

#### 1.2.6 Eintrittswahrscheinlichkeit nach teilenden Regeln im Beispiel
Die drei grundlegenden Typen teilender Regeln soll noch einmal detailliert veranschaulicht werden:
<table>
<tr><td width="33%">UND</td><td width="33%">ENTWEDER-ODER</td width="33%"><td>ODER</td></tr>
<tr><td><image src="media/path-split-with-AND.png"/></td><td><image src="media/path-split-with-XOR.png"/></td><td><image src="media/path-split-with-OR.png"/></td></tr>
<tr><td>teilenden Regel:	1.0000<br/>Ereignis 1:	1.0000<br/>Ereignis 2:	1.0000<br/>Ereignis 3:	1.0000</td>
    <td>teilenden Regel:	1.0000<br/>Ereignis 1:	0.3333<br/>Ereignis 2:	0.3333<br/>Ereignis 3:	0.3333</td>
    <td>teilenden Regel:	1.0000<br/>Ereignis 1:	0.7500<br/>Ereignis 2:	0.7500<br/>Ereignis 3:	0.7500</td>
</tr>
<tr><td>Alle drei Pfade nach der teilenden Regel werden <b>immer</b> durchlaufen.</td><td>Jeweils nur <b>einer</b> der drei Pfade nach der teilenden Regel wird durchlaufen.</td><td>Jeder der drei Pfade nach der teilenden Regel kann<ul><li>allein durchlaufen werden,</li><li>zusammen mit einem der weiteren Pfad durchlaufen werden oder</li><li>zusammen mit den beiden weiteren Pfaden durchlaufen werden.</li></ul>
</td></tr>
</table>

## <a name="calculate-task-costs">2.0 - Berechnung der Kosten und Ressourcen-Auslastung je Task</a>

Kosten und Auslastung von Ressourcen entstehen nur an Tasks. Ereignisse, Gateways und Conditions tragen per definition nicht zu Kosten und
Auslastung von Ressourcen bei.

Die Kosten an den Tasks werden aus den Kostensätzen der Ressourcen berechnet, indem die Kostensätze je Stunde mit den Zeiten und Häufigkeiten der Tasks
multipliziert werden und die Kosten je Einheit mit den Häufigkeiten der Tasks multipliziert werden.

Ressourcen-Auslastungen an den Tasks werden aus den Zeiten und Häufigkeiten der Tasks berechnet und
die Ressourcen-Verbräuche werden aus den Häufigkeiten der Tasks berechnet.

### <a name="calculate-global-prop">2.1 - Berechnung der Standard-Kosten und Standard-Ressourcen-Auslastung</a>
