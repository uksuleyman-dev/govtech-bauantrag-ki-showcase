# Beispiel — Hybrider Prüfablauf

> Vereinfachtes, anonymisiertes Beispiel. Keine fachliche oder rechtliche Aussage.

## Eingang

Ein Antrag enthält strukturierte Felder sowie ein beigefügtes Dokument.

## Ablauf

1. Intake normalisiert die verfügbaren Daten.
2. Eine deterministische Regel prüft, ob definierte Pflichtinformationen vorhanden sind.
3. Ein KI-Service analysiert einen unstrukturierten Text auf für die Prüfung relevante Hinweise.
4. Beide Pfade erzeugen strukturierte Befunde mit Herkunft.
5. Die Review-Schicht zeigt Befunde und Evidenz getrennt von den Originaldaten.
6. Ein Mensch entscheidet über die weitere Bearbeitung.
7. Die Statusänderung wird für die Nachvollziehbarkeit protokolliert.

## Kerngedanke

```text
Originaldaten ≠ Regelbefund ≠ KI-Vorschlag ≠ menschliche Entscheidung
```

Diese Trennung ist eine bewusste Architekturentscheidung.
