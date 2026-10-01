# Architektur — GovTech Bauantrag KI

## Ziel

Eine Assistenzschicht entwerfen, die strukturierte und unstrukturierte Antragsinformationen prüfen kann und dabei deterministische Logik, KI-Unterstützung und menschliche Verantwortung sauber voneinander trennt.

## Komponenten

### Intake / Normalisierung
Übernimmt strukturierte Antragsdaten und Dokumentmetadaten und übersetzt sie in ein internes Prüfmodell.

### Rule Engine
Bearbeitet Prüfungen, die eindeutig als Regeln formuliert werden können. Ergebnisse sind deterministisch und reproduzierbar.

### AI Service
Bearbeitet semantische Aufgaben und unstrukturierte Inhalte. Ausgaben werden als Vorschläge bzw. Befunde mit eigener Herkunft behandelt.

### Finding Model
Vereinheitlicht Ergebnisse aus Regeln und KI. Ein Befund sollte Quelle, Typ, Status und nachvollziehbare Evidenz tragen können.

### Review
Menschen prüfen relevante Befunde, bestätigen sie, verwerfen sie oder fordern weitere Informationen an.

### Audit
Protokolliert relevante Zustandsänderungen und trennt ursprüngliche Eingaben von später abgeleiteten Ergebnissen.

## Vertrauensgrenzen

```text
externes Fachsystem
       │
       ▼
[ Intake Boundary ]
       │
       ▼
 internes Datenmodell
    │           │
    ▼           ▼
 Rule Engine   AI Service ── externe Modellgrenze
    │           │
    └─────┬─────┘
          ▼
      Findings
          │
          ▼
 [ Human Review ]
          │
          ▼
     Entscheidung
```

## Governance-Prinzipien

1. KI-Ausgabe ist kein automatischer Entscheid.
2. Provenienz von Daten und Befunden bleibt erkennbar.
3. Deterministische Regeln und probabilistische Modelle werden nicht vermischt.
4. Modellwechsel dürfen historische Evidenz nicht überschreiben.
5. Fachlich relevante Aktionen besitzen einen menschlichen Kontrollpunkt.
6. Fehler und Unsicherheit müssen als Systemzustand darstellbar sein.

## Trade-offs

Human-in-the-Loop reduziert vollständige Automatisierung, erhöht aber Kontrolle und Nachvollziehbarkeit. Eine getrennte Rule Engine erzeugt zusätzliche Architekturkomplexität, verhindert jedoch, dass klar definierte Regeln unnötig probabilistisch behandelt werden. Ein einheitliches Finding-Modell vereinfacht Review und Audit, verlangt dafür saubere Provenienz.
