# open_data_portals
Abruf und Zusammenführung von Metadaten zu Ressourcen aus diversen Open Data Portalen

# Ansatz
In diesem Projekt sollen die öffentlich zugänglichen Angaben zu den Inhalten der Open Data Portale abgerufen und in einem gemeinsamen Dataset zur Verfügung gestellt werden.
## Einsatzzweck
Mit den gesammelten Daten können:
- Neuzugänge in Portalen gefunden und beurteilt werden
- die verfügbaren Ressourcen anhand ihrer Typen oder Namen gesucht werden.
- Portal-übergreifend bestimmte Ressourcen gefunden und heruntergeladen werden

## Zugängliche Portale
Aktuell werden in der Implementierung Portale der folgenden Typen abgefragt und ihre Inhalte zusammengeführt
- CKAN Portale, wie z.B. das Transparenzportal Karlsruhe
- DKAN Portale, die eine etwas abgewandelte API im Vergleich zu CKAN verwenden.
- Open Data Portale, die eine weitere API abweichend von CKAN oder DKAN verwenden und auch die Ergebnisse in einer etwas abweichenden Struktur liefern.

Die bisher verwendeten Portale sind über eine Suche im Internet gesammelt und die Liste kann bei Bedarf recht einfach ewrweitert werden.
Um Portale anzubinden, die sich einer weiteren API bedienen, müssen größere Teile der Implementierung angepasst oder neu entwickelt werden.

## Vereinheitlichung der Ergebnisse
Mit den entwickelten Verarbeitungsprozessen werden die aus den APIs gelieferten Rückmeldungen analog zu den aus CKAN erhaltenen Strukturen aufbereitet, so weit das möglich ist. Das kann aber dazu führen, dass bestimmte Attribute nur für Einträge aus einem bestimmten Typ der Portale gefüllt werden können.
Die Ergebnisse werden aktuell hauptsächlich als CSV-Dateien bereitgestellt. Beziehungen zwischen Objekten (Zeilen) aus unterschiedlichen Dateien werden über dafür generierte Schlüsselfelder hergesetllt. So können z.B. alle Ressourcen eines Portals identifiziert werden, aber auch die Ressourcen eines bestimmten Packages oder einer Gruppe.
## Verarbeitungsprozesse
Der Abruf und die Verarbeitung der Objekte wird über das Tool KNIME ausgeführt. Hier sind mehrere Prozesse entstanden, die die Daten besorgen, bereinigen und aufbereiten bzw. am Ende dann die verschiedenen Quellen miteinander kombinieren und in gemeinsamen Dateien ablegen.

## Auswertung
Um zu zeigen, wie man mit den Ergebnissen umgehen kann, wurde eine Beispielauswertung mit dem Tool Power BI Desktop erstellt, die ein Datenmodell aufbaut und darauf Auswertungen zeigt.
