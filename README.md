# GovTech Bauantrag KI — Showcase

> Architektur-Showcase einer KI-gestützten Assistenz- und Qualitätssicherungsschicht für digitale Bauantragsprozesse.

## Projektidee

Bauanträge verbinden strukturierte Fachdaten, Dokumente, formale Anforderungen und menschliche Entscheidungen. Das Projekt untersucht, wie **regelbasierte Prüfungen und KI-Unterstützung** kombiniert werden können, ohne fachliche Verantwortung oder Nachvollziehbarkeit an ein Sprachmodell abzugeben.

Der Schwerpunkt liegt deshalb nicht auf einem autonomen „KI-Entscheider“, sondern auf einer **assistierenden Data/AI-Architektur mit Human-in-the-Loop**.

Dieses öffentliche Repository ist ein technischer Showcase und keine produktive Verwaltungssoftware oder Rechtsberatung.

## Architekturüberblick

```text
 Antrag / Dokumente / XBAU-nahe Daten
                  │
                  ▼
        Datenaufnahme & Validierung
                  │
          ┌───────┴────────┐
          ▼                ▼
   Regelbasierte       KI-gestützte
      Prüfungen          Assistenz
          │                │
          └───────┬────────┘
                  ▼
        strukturierte Befunde
        + Begründung / Evidenz
                  │
                  ▼
           Human-in-the-Loop
                  │
                  ▼
       Freigabe / Rückfrage /
       weitere Bearbeitung
                  │
                  ▼
          Audit / Protokoll
```

## Architekturprinzipien

- **Deterministische Regeln dort, wo Regeln deterministisch sind**
- **KI dort, wo unstrukturierte Inhalte oder semantische Unterstützung Mehrwert liefern**
- **Human-in-the-Loop** bei fachlich relevanten Entscheidungen
- Trennung zwischen Eingabedaten, Prüflogik, KI-Ausgabe und finaler Entscheidung
- Nachvollziehbare Befunde statt undurchsichtiger Endergebnisse
- Auditierbarkeit und Protokollierung als Teil des Systemdesigns
- XBAU-nahe bzw. strukturierte Schnittstellen als Integrationsgrenze

## Warum hybride Prüfung?

Nicht jede Prüfung braucht KI. Pflichtfelder, Wertebereiche oder eindeutig formulierbare Konsistenzregeln können deterministisch geprüft werden. KI wird dort interessant, wo Dokumente interpretiert, Informationen zusammengeführt oder Hinweise aus unstrukturiertem Inhalt erzeugt werden sollen.

```text
                 Prüfanforderung
                       │
              ┌────────┴────────┐
              ▼                 ▼
       deterministisch?      semantisch?
              │                 │
              ▼                 ▼
          Regelwerk          KI-Service
              │                 │
              └────────┬────────┘
                       ▼
                Befund + Evidenz
                       ▼
                menschliche Prüfung
```

## Data/AI-Governance

Eine KI-Ausgabe wird nicht automatisch zur fachlichen Wahrheit. Das System sollte unterscheiden zwischen:

**Quelldaten → abgeleiteten Befunden → KI-Vorschlägen → menschlicher Entscheidung.**

Diese Trennung verbessert Nachvollziehbarkeit und erlaubt, Modelle oder Regeln später auszutauschen, ohne historische Entscheidungen mit aktuellen Modellantworten zu vermischen.

## Systemgrenzen

Die Architektur trennt mindestens folgende Verantwortlichkeiten:

- Datenaufnahme und Normalisierung
- deterministische Validierung
- KI-/LLM-Service
- Evidenz und Ergebnisstruktur
- Benutzerinteraktion / Review
- Audit und Protokollierung
- Schnittstelle zu vor- und nachgelagerten Fachsystemen

## Was dieses Projekt demonstriert

GovTech Bauantrag KI zeigt den Umgang mit einer zentralen Data/AI-Frage: **Wie integriert man probabilistische KI-Komponenten in einen Prozess, der nachvollziehbar, kontrollierbar und fachlich verantwortbar bleiben muss?**

Damit liegt der Schwerpunkt auf **AI Governance, Systemgrenzen, Datenflüssen, Human-in-the-Loop und der Verbindung deterministischer und probabilistischer Komponenten**.

## Inhalt dieses Showcases

- `README.md` — Projekt- und Architekturüberblick
- `ARCHITECTURE.md` — Systemgrenzen, Prüfpfade und Governance
- `examples/check-flow.md` — anonymisiertes Beispiel eines hybriden Prüfablaufs

## Abgrenzung

Der Showcase behauptet keine produktive Behördenintegration und keine automatisierte rechtliche Entscheidung. Er dokumentiert eine Architekturidee und deren technische Umsetzungsmuster.

---

**Portfolio-Schwerpunkt:** Data/AI Architecture · AI Governance · Human-in-the-Loop · Auditability
