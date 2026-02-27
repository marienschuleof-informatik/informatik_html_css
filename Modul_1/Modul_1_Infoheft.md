# Modul 1 – Informationsheft

## Thema: Grundlagen HTML – Struktur einer Webseite

> **Unser Projekt:** In allen vier Modulen erstellst du Schritt für Schritt eine vollständige persönliche Webseite mit deinem Lebenslauf. Am Ende von Modul 4 hast du eine fertige, barrierefreie Webseite in deinem GitHub Education Repository.
> 
> **Modul 1:** Du legst das Fundament – die HTML-Grundstruktur deines Lebenslaufs.

---

## Informationstext

**HTML** steht für **HyperText Markup Language** und ist die Grundsprache des World Wide Web. HTML ist keine Programmiersprache, sondern eine **Auszeichnungssprache**: Sie beschreibt die Struktur und den Inhalt einer Webseite mithilfe von sogenannten **Tags**. Ein Tag ist ein in spitzen Klammern geschriebenes Schlüsselwort, zum Beispiel `<p>` oder `</p>`. Die meisten HTML-Elemente bestehen aus einem öffnenden Tag und einem schließenden Tag – das schließende Tag trägt einen Schrägstrich vor dem Schlüsselwort. Zwischen den Tags steht der Inhalt des Elements. Diese Kombination nennt man **HTML-Element**.

---

### Grundstruktur eines HTML-Dokuments

Jedes HTML-Dokument folgt einem festen Aufbau. Das folgende Beispiel zeigt die komplette Grundstruktur der ersten Datei deines Lebenslauf-Projekts: `index.html`.

```html
<!DOCTYPE html>
<html lang="de">
  <head>
    <meta charset="UTF-8">
    <title>Mein Lebenslauf – Max Mustermann</title>
  </head>
  <body>
    <h1>Max Mustermann</h1>
    <p>Willkommen auf meiner persönlichen Webseite.</p>
  </body>
</html>
```

**Was bedeuten diese Zeilen?**

|Zeile|Bedeutung|
|---|---|
|`<!DOCTYPE html>`|Teilt dem Browser mit: Dies ist ein HTML5-Dokument.|
|`<html lang="de">`|Wurzelelement der Seite; `lang="de"` sagt Screen-Readern, dass die Seite Deutsch ist.|
|`<head>`|Kopfbereich mit Metainformationen – **nicht sichtbar** auf der Webseite.|
|`<meta charset="UTF-8">`|Stellt sicher, dass Umlaute (ä, ö, ü) korrekt angezeigt werden.|
|`<title>`|Der Text, der im Browser-Tab erscheint.|
|`<body>`|Anzeigebereich – **alles Sichtbare** steht hier drin.|
|`<h1>`|Die wichtigste Überschrift der Seite – hier dein Name.|
|`<p>`|Ein Absatz (paragraph).|

---

### Hypertexte und ihre Baumstruktur

HTML-Dokumente sind **Hypertexte** – Dokumente mit einer inneren **Baumstruktur**. Das `<html>`-Element ist die Wurzel, `<head>` und `<body>` sind seine Kinder, und alle weiteren Elemente verzweigen sich darunter. So sieht die Baumstruktur der obigen Datei aus:

```
html
├── head
│   ├── meta
│   └── title
└── body
    ├── h1
    └── p
```

Diese Hierarchie ähnelt einem **Dateisystem** auf dem Computer (Ordner → Unterordner → Dateien) oder dem **DNS-System**, das Domainnamen baumartig organisiert (z. B. `.de` → `marienschule-offenbach` → Unterseiten). Der Browser baut aus dieser Baumstruktur intern das **Document Object Model (DOM)** auf und rendert daraus die sichtbare Webseite.

---

### Überschriften und Absätze

HTML stellt `<h1>` bis `<h6>` für Überschriften zur Verfügung. `<h1>` ist die wichtigste Überschrift, `<h2>` wird für Abschnitte wie „Über mich" oder „Schulbildung" verwendet. Für einen Lebenslauf sieht das so aus:

```html
<body>
  <h1>Max Mustermann</h1>
  <p>Schüler der Klasse 9, Marienschule Offenbach</p>

  <h2>Über mich</h2>
  <p>
    Ich bin 15 Jahre alt und interessiere mich für Informatik,
    Fußball und Musik. In meiner Freizeit lerne ich Gitarre spielen.
  </p>

  <h2>Schulbildung</h2>
  <p>Seit 2020 besuche ich die Marienschule Offenbach.</p>

  <h2>Hobbys</h2>
  <p>Fußball, Gitarre, Programmieren</p>
</body>
```

> 💡 **Tipp:** Benutze Überschriften immer in der richtigen Reihenfolge: nach `<h1>` kommt `<h2>`, dann `<h3>` – überspringe keine Ebene! Das ist wichtig für Screen-Reader und Suchmaschinen.

---

### Attribute – Zusatzinformationen für Tags

**Attribute** ergänzen ein HTML-Element um zusätzliche Informationen. Sie stehen immer im öffnenden Tag und haben die Form `name="wert"`.

**Hyperlinks mit `<a href="...">`** – das Attribut `href` gibt das Ziel des Links an:

```html
<h2>Kontakt</h2>
<p>
  Mehr über meine Schule erfährst du hier:
  <a href="https://www.marienschule-offenbach.de">Marienschule Offenbach</a>
</p>

<!-- Innerhalb der eigenen Seite verlinken (Anker-Link): -->
<a href="#schulbildung">Direkt zur Schulbildung springen</a>
```

**Bilder mit `<img>`** – ein **leeres Element** ohne schließendes Tag. Das Attribut `src` gibt den Pfad zum Bild an, `alt` liefert einen Beschreibungstext für Screen-Reader:

```html
<!-- Bild aus dem Unterordner "bilder/" einbinden -->
<img src="bilder/portrait.jpg"
     alt="Portraitfoto von Max Mustermann, lächelnd vor weißem Hintergrund">
```

> ⚠️ **Urheberrecht:** Verwende nur Bilder, die du selbst fotografiert hast, oder Bilder mit einer Creative-Commons-Lizenz (z. B. von [Wikimedia Commons](https://commons.wikimedia.org/)). Bilder fremder Personen dürfen außerdem nur mit ihrer Zustimmung veröffentlicht werden (**Persönlichkeitsrecht**).

---

### HTML-Kommentare

Kommentare werden im Browser nicht angezeigt und helfen dir, deinen Code zu strukturieren und zu erklären:

```html
<!-- ==================== KOPFBEREICH ==================== -->
<h1>Max Mustermann</h1>
<p>Klasse 9 | Marienschule Offenbach</p>

<!-- ==================== ABSCHNITT: ÜBER MICH ==================== -->
<h2>Über mich</h2>
<p>Hier steht etwas über mich.</p>
```

---

### Wie funktioniert ein Browser?

Ein **Browser** ist ein Informatiksystem, das HTML-Dokumente liest und grafisch darstellt. Wenn du eine URL eingibst, läuft folgendes ab:

```
Du gibst ein:  https://www.marienschule-offenbach.de/lebenslauf.html
                        │
                        ▼
              Browser sendet Anfrage an Webserver
                        │
                        ▼
              Webserver schickt HTML-Datei zurück
                        │
                        ▼
              Browser parst HTML → baut DOM-Baum auf
                        │
                        ▼
              Browser rendert → sichtbare Webseite
```

---

### Die URL – Adresse im Internet

**URL** steht für Uniform Resource Locator. Eine URL besteht aus mehreren Bestandteilen:

```
https://www.marienschule-offenbach.de/klasse9/lebenslauf.html
│       │                              │       │
│       │                              │       └─ Dateiname
│       │                              └─ Pfad zum Ordner auf dem Server
│       └─ Domain (Name des Webservers)
└─ Protokoll  (HTTPS = verschlüsselt, erkennbar am 🔒 im Browser)
```

**HTTP** überträgt Daten unverschlüsselt – jeder, der den Datenverkehr abfängt, kann mitlesen. **HTTPS** verschlüsselt die Übertragung und schützt damit deine Daten und die Daten deiner Besucherinnen und Besucher.

---

## Quellen

- MDN Web Docs – HTML-Grundlagen: [https://developer.mozilla.org/de/docs/Learn/HTML/Introduction_to_HTML](https://developer.mozilla.org/de/docs/Learn/HTML/Introduction_to_HTML)
- W3Schools – HTML Tutorial: [https://www.w3schools.com/html/](https://www.w3schools.com/html/)
- HTML & CSS - Teil 2 - Einstieg: [https://youtu.be/pq-X-pQVwg8](https://youtu.be/pq-X-pQVwg8)
-  HTML & CSS - Teil 3 - Tabellen und Bilder: [https://youtu.be/SU3D5B37_ps](https://youtu.be/SU3D5B37_ps)
- HTML & CSS - Teil 4 - Verlinkungen: [https://youtu.be/BJWma6oTumY](https://youtu.be/BJWma6oTumY)
- Creative Commons – Lizenzen verstehen: [https://creativecommons.org/licenses/?lang=de](https://creativecommons.org/licenses/?lang=de)

---

## Merkblatt – Wichtige Begriffe

|Begriff|Beschreibung|
|---|---|
|HTML|HyperText Markup Language – Auszeichnungssprache zur Strukturierung von Webseiten|
|Tag|Schlüsselwort in spitzen Klammern, z. B. `<p>` oder `</p>`|
|Element|Kombination aus öffnendem Tag, Inhalt und schließendem Tag|
|Attribut|Zusatzinformation in einem Tag, z. B. `src="bild.jpg"` oder `lang="de"`|
|`<!DOCTYPE html>`|Deklaration, die HTML5 als Dokumenttyp ankündigt|
|`<head>`|Kopfbereich: enthält Metadaten – nicht sichtbar auf der Seite|
|`<body>`|Anzeigebereich: enthält alle sichtbaren Inhalte|
|`<h1>` bis `<h6>`|Überschriften-Tags von größter (h1) bis kleinster (h6) Ebene|
|`<p>`|Absatz (paragraph)|
|`<a href="...">`|Hyperlink zu einer anderen Seite oder einem Anker auf der gleichen Seite|
|`<img src="..." alt="...">`|Einbindung eines Bildes; `alt` = Alternativtext für Barrierefreiheit|
|Hypertext|Verknüpfte Dokumente mit hierarchischer Baumstruktur|
|DOM|Document Object Model – interne Baumstruktur des HTML-Dokuments im Browser|
|Browser|Informatiksystem zum Darstellen von Webseiten (Chrome, Firefox, Edge …)|
|URL|Uniform Resource Locator – Protokoll + Domain + Pfad + Dateiname|
|HTTPS|Verschlüsseltes Übertragungsprotokoll; erkennbar am Schloss-Symbol im Browser|
|Screen-Reader|Hilfstechnologie, die Webseiteninhalte vorliest (Barrierefreiheit)|
|Urheberrecht|Schutz kreativer Werke – fremde Inhalte dürfen nicht ohne Erlaubnis genutzt werden|
|Persönlichkeitsrecht|Fotos anderer Personen dürfen nicht ohne Zustimmung veröffentlicht werden|
|DNS|Domain Name System – übersetzt Domainnamen in IP-Adressen (Baumstruktur)|

---

_Lernmodule HTML/CSS/JavaScript – Klasse 9 | Realschule Hessen | Marienschule Offenbach_ _Prozessbezogene Kompetenzen: P1, P2, P3, P5 | Inhaltsbezogene Kompetenzen: I2, I3, I4, I5_
