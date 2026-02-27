# Modul 1 – Arbeitsheft
## Thema: Grundlagen HTML – Struktur einer Webseite

> **Ziel dieses Moduls:** Am Ende dieser beiden Unterrichtsstunden hast du die Grundstruktur deiner persönlichen Lebenslauf-Webseite erstellt und in deinem GitHub Education Repository abgelegt.
>
> **Lies zunächst das Informationsheft vollständig durch**, bevor du mit den Aufgaben beginnst. Arbeite mit einer Partnerin oder einem Partner zusammen – besprecht die Aufgaben gemeinsam, bevor ihr mit der Umsetzung beginnt.

> **GitHub Education:** Lege alle Dateien in deinem persönlichen Repository ab. Deine Hauptdatei heißt `index.html`. Erstelle außerdem einen Ordner `bilder/` für spätere Bilder. Führe nach jeder abgeschlossenen Aufgabe einen **Commit** durch mit einer kurzen Beschreibung, z. B. `"M1.2 – Grundstruktur erstellt"`.

---

## 🟥 Mindeststandard

### Aufgabe M1.1 – HTML erklären und die Baumstruktur verstehen

Schaut euch gemeinsam die **Grundstruktur** und das **Baumstruktur-Diagramm** im Informationsheft an. Erklärt euch gegenseitig:

- Was ist eine Auszeichnungssprache – und was ist sie **nicht**?
- Was steht im `<head>`, was steht im `<body>`?
- Warum ähnelt die HTML-Baumstruktur einem Dateisystem?

Notiert eure Erklärung anschließend schriftlich in **mindestens 4 Sätzen**. Orientiert euch an den Stichworten:

> Auszeichnungssprache · Tag · Baumstruktur · Browser

---

### Aufgabe M1.2 – Erste `index.html` erstellen

Erstellt gemeinsam eine Datei `index.html` in eurem GitHub Education Repository. Übertragt die Grundstruktur aus dem Informationsheft und passt sie an euren eigenen Lebenslauf an:

```html
<!DOCTYPE html>
<html lang="de">
  <head>
    <meta charset="UTF-8">
    <title>Mein Lebenslauf – [Dein Name]</title>
  </head>
  <body>
    <h1>[Dein Name]</h1>
    <p>Willkommen auf meiner persönlichen Webseite.</p>
  </body>
</html>
```

Ersetzt `[Dein Name]` durch euren echten Namen. Öffnet die Datei anschließend im Browser (über GitHub Pages oder lokal mit Doppelklick) und überprüft: Erscheint der Name im Browser-Tab und als Überschrift auf der Seite?

**Notiert hier, was ihr angepasst habt:**

| Element | Euer Inhalt |
|---|---|
| `<title>` | |
| `<h1>` | |
| `<p>` (erster Absatz) | |

---

## 🟩 Regelstandard

### Aufgabe M1.3 – Den Lebenslauf ausbauen

Erweitert eure `index.html` nach dem Vorbild aus dem Informationsheft zu einem vollständigen Lebenslauf-Entwurf. Fügt mindestens folgende Abschnitte hinzu:

```html
<h2>Über mich</h2>
<p>...</p>

<h2>Schulbildung</h2>
<p>...</p>

<h2>Hobbys</h2>
<p>...</p>
```

Fügt außerdem einen **Hyperlink** zu einer Webseite eurer Wahl hinzu, zum Beispiel zur Schulwebseite:

```html
<a href="https://www.marienschule-offenbach.de">Marienschule Offenbach</a>
```

Diskutiert miteinander: Wozu dient das `href`-Attribut? Was passiert, wenn ihr `href` weglasst? Probiert es aus und notiert das Ergebnis.

---

### Aufgabe M1.4 – URL analysieren

Analysiert die folgende URL aus dem Informationsheft und tragt eure Ergebnisse in die Tabelle ein:

```
https://www.marienschule-offenbach.de/klasse9/lebenslauf.html
```

| Bestandteil | Wert aus der URL | Bedeutung |
|---|---|---|
| Protokoll | | |
| Domain | | |
| Pfad zum Ordner | | |
| Dateiname | | |

Bewertet schriftlich in **mindestens 2 Sätzen**, warum HTTPS gegenüber HTTP bevorzugt werden sollte. Bringt dabei den Begriff **Datensicherheit** ein.

---

## 🟦 Expertenstandard

### Aufgabe M1.5 – Bild einbinden und Urheberrecht beachten

Bindet ein Bild in euren Lebenslauf ein. Verwendet entweder ein eigenes Foto oder ein Bild mit Creative-Commons-Lizenz von [Wikimedia Commons](https://commons.wikimedia.org). Legt das Bild in den Ordner `bilder/` und bindet es so ein:

```html
<img src="bilder/portrait.jpg"
     alt="[Beschreibung des Bildes]">
```

Ersetzt `[Beschreibung des Bildes]` durch einen aussagekräftigen Alternativtext – beschreibt, **was** auf dem Bild zu sehen ist (nicht nur „Foto").

Beantwortet schriftlich in **mindestens 3 Sätzen**:
- Warum ist das `alt`-Attribut für die Barrierefreiheit wichtig?
- Welche Personengruppen profitieren davon?
- Wie habt ihr das **Urheberrecht** und das **Persönlichkeitsrecht** bei der Bildauswahl beachtet?

---

### Aufgabe M1.6 – Baumstruktur zeichnen und DOM erklären

Zeichnet die **Baumstruktur** eurer eigenen `index.html` auf Papier – nach dem Vorbild des Diagramms im Informationsheft:

```
html
├── head
│   ├── meta
│   └── title
└── body
    ├── h1
    ├── p
    ├── h2
    └── ...
```

Tragt **alle** eure Elemente ein, nicht nur die aus dem Beispiel. Erklärt danach schriftlich in **mindestens 4 Sätzen**: Was ist der DOM? Wie entsteht er aus dem HTML? Welche Analogie hat er zum Dateisystem oder zum DNS?

---

## Reflexion

Bewertet am Ende der Stunde, wie gut ihr die Inhalte dieses Moduls verstanden habt. Setzt für jede Aussage ein Kreuz in die passende Spalte.

| Reflexionssatz | 😊 | 😐 | 😔 |
|---|:---:|:---:|:---:|
| Ich kann erklären, was HTML ist und wofür es verwendet wird. | | | |
| Ich verstehe den Aufbau eines HTML-Dokuments (`DOCTYPE`, `head`, `body`). | | | |
| Ich kann eine einfache HTML-Datei selbstständig erstellen. | | | |
| Ich weiß, was ein Attribut ist, und kann `href` und `alt` erklären. | | | |
| Ich kann die Bestandteile einer URL benennen und erläutern. | | | |
| Ich habe das Urheberrecht beim Einbinden von Bildern beachtet. | | | |
| Ich habe die Baumstruktur meiner HTML-Datei verstanden und gezeichnet. | | | |
| Ich habe nach jeder Aufgabe einen Commit in GitHub Education gemacht. | | | |

---

*Lernmodule HTML/CSS/JavaScript – Klasse 9 | Realschule Hessen | Marienschule Offenbach*
*Abzugeben: dieses Arbeitsheft (gedruckt oder als PDF) | `index.html` im GitHub Education Repository*
