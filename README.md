# Ethical Design Companion

Ein wiederverwendbarer AI-Skill für verantwortungsvolle UX- und Produktentscheidungen: von der ersten Idee über Interaktionsdesign und UX Writing bis zur Implementierung und Designkritik.

**Version:** `0.1.0` · **Status:** MVP · **Format:** Markdown-Skill mit YAML-Metadaten · **Repository:** privat

Der Companion hilft dabei, Geschäftsziele, Selbstbestimmung, Fairness und Nutzerwohl gemeinsam zu betrachten. Er benennt konkrete Risiken, trennt Beobachtungen von Vermutungen und schlägt umsetzbare Alternativen vor. Die Skill-Anweisungen sind auf Englisch; Aufgaben und Antworten können auf Deutsch formuliert werden.

## Funktionsumfang

- **Designbegleitung:** Relevante Prinzipien fließen in laufende Design- und Codeaufgaben ein. Hinweise konzentrieren sich auf wesentliche Risiken.
- **Gezielte Kritik:** Auffällige Mechanismen werden mit möglicher Auswirkung, Evidenz und einer konkreten Verbesserung beschrieben.
- **Strukturierte Reviews:** Auf ausdrücklichen Wunsch untersucht der Companion einen Flow systematisch und priorisiert Befunde nach Auswirkung und Beleglage.
- **Entwurfsvarianten:** Bei passenden Aufgaben entstehen zwei bis drei strukturell unterschiedliche Lösungen mit nachvollziehbaren Abwägungen.
- **Implementierungsnähe:** Code-Reviews berücksichtigen Zustände, Defaults, Fehler, Tastaturbedienung und Datenflüsse. Design-Reviews berücksichtigen Hierarchie, Komponenten und Microcopy.

Geeignete Eingaben sind Screenshots, Flow-Beschreibungen, Spezifikationen, UI-Texte und zugänglicher Quellcode. Figma, Repositories und Analytics werden nur berücksichtigt, wenn sie tatsächlich bereitgestellt oder über vorhandene Werkzeuge zugänglich sind. Der Skill selbst enthält keine Connectoren, ausführbaren Skripte oder API-Zugangsdaten.

## Ethical Design Framework

Das Framework verbindet **sieben Prinzipien und 31 Regel-IDs** mit einem Review-Protokoll für Evidenz, Schweregrad, Empfehlungen und Validierung.

| Prinzip | Regelgruppe | Leitfrage |
| --- | --- | --- |
| Selbstbestimmung | `AUT` | Können Menschen informiert wählen, ablehnen und Entscheidungen korrigieren? |
| Transparenz und Ehrlichkeit | `TRN` | Sind Handlung, Kosten und Konsequenzen verständlich? |
| Privacy by Design | `PRV` | Sind Datenerhebung, Defaults und Kontrolle angemessen? |
| Fairness und Respekt | `FAR` | Vermeidet das Design Ausgrenzung, Ausbeutung und Beschämung? |
| Schutz vor Manipulation | `MAN` | Verzichtet der Flow auf Täuschung, Druck und unnötige Hürden? |
| Zugänglichkeit und Inklusion | `ACC` | Können Menschen mit unterschiedlichen Voraussetzungen den Flow bedienen? |
| Digitales Wohlbefinden | `WEL` | Dienen Unterbrechungen und Engagement den Bedürfnissen der Nutzenden? |

Die [Pattern Library](references/pattern-library.md) enthält sechs Familien: Einwilligung und Berechtigungen, Checkout und Preise, Entscheidungsarchitektur, Onboarding und Formulare, Benachrichtigungen sowie Kündigung und Kontoverwaltung. Jede Familie enthält Warnsignale, Prüffragen, positive Alternativen und Abwägungen.

## Dateien

| Datei | Inhalt |
| --- | --- |
| [SKILL.md](SKILL.md) | Einstieg, Aktivierung, Arbeitsweise und Grenzen |
| [design-rules.md](references/design-rules.md) | Ethical Design Framework: Prinzipien und operative Regeln |
| [review-framework.md](references/review-framework.md) | Evidenz, Schweregrade, Feedbackformat und Bewertungsrubrik |
| [pattern-library.md](references/pattern-library.md) | Sechs Pattern-Familien mit konkreten Alternativen |
| [test-cases.md](references/test-cases.md) | Zwölf Benchmark-Szenarien mit erwartetem Verhalten |
| [sources.md](references/sources.md) | Herkunft, Quellenangaben und externe Standards |
| [openai.yaml](agents/openai.yaml) | Anzeigename, Kurzbeschreibung und Markenfarbe |
| [VERSION](VERSION) | Paketversion |

## Installation

Voraussetzungen: Zugriff auf dieses private Repository, Git und eine passende AI-Umgebung. Die folgenden Shell-Befehle sind für macOS/Linux gedacht. Bei Verwendung von `gh` zuerst `gh auth status` prüfen und bei Bedarf `gh auth login` ausführen.

### Codex: persönlich installieren

In einem noch nicht vorhandenen Zielordner klonen:

```bash
mkdir -p "$HOME/.agents/skills"
gh repo clone andrnvc/ethical-design-companion "$HOME/.agents/skills/ethical-design-companion" -- --branch v0.1.0
```

Ohne GitHub CLI, mit eingerichtetem GitHub-SSH-Zugang:

```bash
git clone --branch v0.1.0 git@github.com:andrnvc/ethical-design-companion.git "$HOME/.agents/skills/ethical-design-companion"
```

Codex lädt persönliche Skills aus `~/.agents/skills`. Über `/skills` oder `$ethical-design-companion` auswählen; falls der Skill fehlt, Codex neu starten. Der Tag fixiert diese Installation auf v0.1.0. Alternativ kann der vollständige Skill in `.agents/skills/ethical-design-companion/` eines Projektrepositories liegen. Eine Installation genügt. Siehe [OpenAI: Build skills](https://learn.chatgpt.com/docs/build-skills).

### ChatGPT: vorhandene Dateien übernehmen

Das Repository in einen lokalen Arbeitsordner klonen:

```bash
gh repo clone andrnvc/ethical-design-companion -- --branch v0.1.0
```

Die ChatGPT-Desktop-App unterstützt eigenständige Skills. Unter **Skills** sind vorhandene Skills sichtbar; mit `@` lassen sie sich auswählen. Für die Übernahme der vorhandenen Dateien kann der Skill Creator verwendet werden. Quelle: [OpenAI: Build skills](https://learn.chatgpt.com/docs/build-skills).

Einrichtungs-Prompt mit Zugriff auf den geklonten Ordner:

```text
@skill-creator Übernimm den vorhandenen Ethical Design Companion aus dem
Ordner ethical-design-companion als persönlichen Skill. Bewahre SKILL.md,
alle Referenzen und die Version 0.1.0. Erfinde keine zusätzlichen Regeln.
```

Falls deine ChatGPT-Oberfläche keine lokale Skill-Einrichtung anbietet, stelle `SKILL.md` und die fünf Markdown-Dateien aus `references/` als Chat-Dateien bereit und verwende diesen Prompt:

```text
Verwende die beigefügte SKILL.md und ihre Referenzen als Arbeitsanleitung
für diese Unterhaltung. Prüfe zuerst, ob alle fünf Referenzen vorliegen.
Antworte auf Deutsch und wende den Ethical Design Companion auf meine
nächste Designaufgabe an.
```

Diese Variante nutzt den bereitgestellten Kontext im Chat. Vertrauliche Projektdateien sind für die Einrichtung nicht erforderlich.

## Beispiele

Die Beispiele beschreiben fiktive Produkte. In ChatGPT zuerst den eingerichteten Skill mit `@` auswählen oder die oben beschriebene Dateivariante verwenden.

### ChatGPT: Checkout bewerten

```text
Prüfe diesen Checkout mit dem Ethical Design Companion:
Ein Jahresabo wird mit „9 € pro Monat“ beworben. Die jährliche Abbuchung
von 108 € erscheint erst nach dem Button „Jetzt kaufen“.

Trenne Beobachtung, Risiko und offene Fragen. Nenne relevante Regel-IDs,
priorisiere die Befunde und entwirf zwei unterschiedliche Verbesserungen
mit konkreter deutscher Microcopy.
```

Eine passende Rückmeldung würde die verspätete Information zur Abbuchung mit `AUT-03` und `TRN-02` verknüpfen, eine klare Preiszusammenfassung vor dem Kauf empfehlen und offene Fragen zu weiteren Kosten benennen. Konkrete Conversion-Effekte müssten erst getestet werden.

### ChatGPT: drei Consent-Varianten entwerfen

```text
Entwirf drei strukturell unterschiedliche Varianten für freiwillige
Produkt-E-Mails in einer fiktiven Lern-App. Der Kernzugang soll unabhängig
von der Einwilligung bleiben. Vergleiche eine separate Opt-in-Auswahl,
eine kontextbezogene Nachfrage und ein späteres Präferenzzentrum.
Berücksichtige Selbstbestimmung, Aufwand, Zugänglichkeit und UX Writing.
```

### Codex: Formular im Repository verbessern

```text
$ethical-design-companion Prüfe das Registrierungsformular in diesem
Repository auf vorausgewählte Marketing-Einwilligungen und Fehler,
die nur durch Farbe erkennbar sind. Untersuche die tatsächliche
Implementierung. Behebe bestätigte Probleme, ergänze passende Hinweise
und prüfe Tastaturbedienung sowie das bestehende Testverhalten.
Fasse Änderungen und verbleibende offene Fragen zusammen.
```

Für ein Review ohne Änderungen ersetze „Behebe bestätigte Probleme“ durch „Erstelle einen priorisierten Review; ändere keine Dateien“.

## Tests und Qualitätsprüfung

Die [zwölf Testfälle](references/test-cases.md) enthalten Risiken und Gegenbeispiele: bezahlte Extras, echte Reservierungsfristen, freiwillige Einwilligung, Kündigungswege, berechtigte Löschbestätigungen, Preistransparenz, Notfallmeldungen und fehlende Backend-Evidenz.

Für einen Verhaltensbenchmark jeden Fall in einer frischen Unterhaltung mit dem Skill ausführen und anhand der [Bewertungsrubrik](references/review-framework.md) beurteilen. Modell, Datum, Antwort und Bewertung festhalten; Fehlalarme ausdrücklich erfassen. Echte Knappheit und notwendige Bestätigungen dürfen nicht pauschal als Manipulation eingestuft werden.

v0.1.0 enthält Testszenarien und erwartetes Verhalten. Es liegt kein systematischer, modellübergreifender Zuverlässigkeitsnachweis vor. Eine Dateiprüfung bestätigt Struktur und Konsistenz, nicht die Qualität jeder späteren Modellantwort.

## Quellen und verantwortliche Weiterverwendung

Die Regeln und Beispiele sind eine eigenständig formulierte operative Synthese des bereitgestellten Skills. Die vollständige Herkunft steht in [sources.md](references/sources.md). Das Repository enthält keine Buchdateien, Scans, kopierten Buchpassagen oder internen Projektunterlagen. Literatur und Standards werden bibliografisch genannt beziehungsweise verlinkt.

Der Companion unterstützt Designentscheidungen. Er ersetzt keine rechtliche Prüfung, Nutzerforschung oder Prüfung mit assistiven Technologien. Aussagen über Rechtskonformität benötigen aktuelle Quellen und den konkreten Anwendungskontext; Screenshots allein belegen weder Backend-Verhalten noch vollständige Barrierefreiheit.

Für weitere Beiträge nur generische oder freigegebene Beispiele verwenden. Vor jedem Commit Änderungen auf vertrauliche Informationen, Zugangsdaten und fremde Inhalte prüfen. `.gitignore` schließt typische lokale Dateien und Publikationsformate aus; die inhaltliche Prüfung bleibt erforderlich.

Für dieses private Repository wurde keine Open-Source-Lizenz festgelegt. Rechte an zitierten Werken und Standards verbleiben bei ihren jeweiligen Rechteinhabern.
