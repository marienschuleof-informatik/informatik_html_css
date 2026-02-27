# Modul 4 – Informationsheft
## Thema: Barrierefreie Webseiten & Abschlussprojekt

> **Erinnerung:** Du hast in den Modulen 1–3 HTML-Struktur (`index.html`), CSS-Design (`style.css`) und JavaScript-Interaktivität (`script.js`) erstellt. In diesem letzten Modul vervollständigst du deinen Lebenslauf: Du strukturierst ihn mit semantischem HTML5 und machst ihn vollständig barrierefrei.
>
> **Modul 4:** Deine fertige, barrierefreie Webseite wird über GitHub Education abgegeben.

---

## Informationstext

### Barrierefreiheit im Web – WCAG

Die **Web Content Accessibility Guidelines (WCAG)** sind internationale Richtlinien für barrierefreie Webseiten, herausgegeben vom **W3C**. Sie sind in drei Stufen eingeteilt: **A** (Mindest), **AA** (Standard – in vielen Ländern gesetzlich vorgeschrieben) und **AAA** (höchste Stufe). Die vier Grundprinzipien lauten: Webseiten müssen **wahrnehmbar**, **bedienbar**, **verständlich** und **robust** sein.

---

### Semantisches HTML5 – Struktur mit Bedeutung

**Semantisches HTML** bedeutet: Elemente werden so eingesetzt, dass sie ihre inhaltliche Bedeutung widerspiegeln. Statt alles in `<div>`-Elemente zu stecken, nutzt du bedeutungstragende HTML5-Elemente. Der Unterschied am Lebenslauf-Projekt:

**❌ Nicht semantisch – mit `<div>`:**

```html
<div id="kopf">
  <div id="name">Max Mustermann</div>
  <div id="navigation">
    <div><a href="#ueber-mich">Über mich</a></div>
    <div><a href="#schulbildung">Schulbildung</a></div>
  </div>
</div>

<div id="inhalt">
  <div class="abschnitt">
    <div class="abschnitt-titel">Über mich</div>
    <div>Ich bin 15 Jahre alt...</div>
  </div>
</div>

<div id="fuss">
  <div>Kontakt: max@example.de</div>
</div>
```

**✅ Semantisch korrekt – mit HTML5-Elementen:**

```html
<header>
  <h1>Max Mustermann</h1>
  <nav aria-label="Seitennavigation">
    <a href="#ueber-mich">Über mich</a>
    <a href="#schulbildung">Schulbildung</a>
    <a href="#hobbys">Hobbys</a>
    <a href="#kontakt">Kontakt</a>
  </nav>
</header>

<main>
  <section id="ueber-mich">
    <h2>Über mich</h2>
    <p>Ich bin 15 Jahre alt und besuche die Klasse 9...</p>
  </section>

  <section id="schulbildung">
    <h2>Schulbildung</h2>
    <p>Seit 2020: Marienschule Offenbach</p>
  </section>

  <section id="hobbys">
    <h2>Hobbys</h2>
    <p>Fußball, Gitarre, Programmieren</p>
  </section>
</main>

<footer id="kontakt">
  <p>Kontakt: <a href="mailto:max@example.de">max@example.de</a></p>
  <p>Diese Webseite wurde im Informatikunterricht erstellt.</p>
</footer>
```

**Warum macht das einen Unterschied?** Ein Screen-Reader-Nutzer kann bei semantischem HTML direkt zum `<main>`-Bereich oder zur `<nav>` springen – ohne alles linear vorlesen lassen zu müssen. Bei reinen `<div>`-Strukturen ist das nicht möglich.

---

### Anker-Links – Navigation innerhalb der Seite

Mit Anker-Links kann man direkt zu einem Abschnitt auf der gleichen Seite springen. Das funktioniert so: Der Ziel-Abschnitt bekommt eine `id`, der Link verweist mit `#` darauf.

```html
<!-- Navigation oben auf der Seite: -->
<nav>
  <a href="#ueber-mich">Über mich</a>
  <a href="#schulbildung">Schulbildung</a>
  <a href="#kontakt">Kontakt</a>
</nav>

<!-- Weiter unten im Dokument: -->
<section id="ueber-mich">
  <h2>Über mich</h2>
  <p>...</p>
</section>
```

Wenn die Nutzerin oder der Nutzer auf „Über mich" klickt, scrollt die Seite automatisch zum Abschnitt mit `id="ueber-mich"`.

---

### ARIA-Attribute

**ARIA** (Accessible Rich Internet Applications) ergänzt HTML, wenn die Semantik allein nicht ausreicht.

```html
<!-- aria-label gibt der Navigation einen sprechenden Namen für Screen-Reader -->
<nav aria-label="Hauptnavigation des Lebenslaufs">
  <a href="#ueber-mich">Über mich</a>
  <a href="#schulbildung">Schulbildung</a>
</nav>

<!-- aria-hidden="true" versteckt rein dekorative Elemente vor Screen-Readern -->
<span aria-hidden="true">✉</span>
<a href="mailto:max@example.de">E-Mail schreiben</a>

<!-- role beschreibt die Funktion eines Elements, wenn kein semantisches Tag existiert -->
<div role="alert">Deine Nachricht wurde gesendet!</div>
```

> 💡 **Regel:** Nutze ARIA nur, wenn kein semantisches HTML-Element die gleiche Funktion erfüllt. Wo möglich, ist semantisches HTML immer vorzuziehen.

---

### Die vollständige `index.html` – Abschlussprojekt

So sieht deine fertige `index.html` nach allen vier Modulen aus:

```html
<!DOCTYPE html>
<html lang="de">
<head>
  <meta charset="UTF-8">
  <title>Lebenslauf – Max Mustermann</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>

  <!-- ===== KOPFBEREICH ===== -->
  <header>
    <img src="bilder/portrait.jpg"
         alt="Portraitfoto von Max Mustermann">
    <h1>Max Mustermann</h1>
    <p>Schüler | Marienschule Offenbach | Klasse 9</p>

    <nav aria-label="Seitennavigation">
      <a href="#ueber-mich">Über mich</a>
      <a href="#schulbildung">Schulbildung</a>
      <a href="#hobbys">Hobbys</a>
      <a href="#kontakt">Kontakt</a>
    </nav>
  </header>

  <!-- ===== HAUPTINHALT ===== -->
  <main>

    <section id="ueber-mich">
      <h2>Über mich</h2>
      <p id="willkommen">
        Ich bin 15 Jahre alt und interessiere mich für Informatik,
        Fußball und Musik.
      </p>
      <p id="zeitanzeige"></p>
      <button id="begruessung-button">Begrüße mich!</button>
    </section>

    <section id="schulbildung">
      <h2>Schulbildung</h2>
      <p>Seit 2020: Marienschule Offenbach (Realschule)</p>
      <p>2016–2020: Grundschule Musterstadt</p>
    </section>

    <section id="hobbys">
      <h2>Hobbys</h2>
      <p>Fußball, Gitarre spielen, Programmieren</p>
      <p>
        Mehr über meine Lieblingssportart:
        <a href="https://www.dfb.de">DFB – Deutscher Fußball-Bund</a>
      </p>
    </section>

  </main>

  <!-- ===== FUSSBEREICH ===== -->
  <footer id="kontakt">
    <h2>Kontakt</h2>
    <p>E-Mail: <a href="mailto:max@example.de">max@example.de</a></p>
    <p>
      Diese Webseite wurde im Informatikunterricht der Klasse 9
      der Marienschule Offenbach erstellt.
    </p>
    <p>
      Alle verwendeten Bilder sind eigene Aufnahmen oder unter
      Creative-Commons-Lizenz veröffentlicht.
    </p>
  </footer>

  <!-- JavaScript am Ende des body einbinden -->
  <script src="script.js"></script>

</body>
</html>
```

---

### Barrierefreiheits-Checkliste – vor der Abgabe prüfen

```
[ ] <html lang="de"> – Sprachangabe vorhanden?
[ ] <meta charset="UTF-8"> – Zeichenkodierung gesetzt?
[ ] <title> – sinnvoller Seitentitel vorhanden?
[ ] Semantische Struktur: <header>, <nav>, <main>, <section>, <footer>?
[ ] Überschriften in richtiger Reihenfolge: h1 → h2 → h3?
[ ] Alle <img>-Tags mit aussagekräftigem alt-Attribut?
[ ] Kontrastverhältnis ≥ 4,5:1 (mit WebAIM-Tool geprüft)?
[ ] Schriftgrößen in em oder rem (nicht px)?
[ ] Alle interaktiven Elemente als <button> (nicht <div>)?
[ ] Seite mit Tab-Taste vollständig bedienbar?
[ ] Urheberrecht beachtet – alle Bilder/Texte selbst erstellt oder lizenziert?
[ ] Persönlichkeitsrecht beachtet – keine Fotos anderer Personen ohne Zustimmung?
```

---

### Informatik, Mensch und Gesellschaft

Das Internet ist Teil der digitalen Infrastruktur unserer Gesellschaft. Barrierefreiheit ist in Deutschland und der EU gesetzlich geregelt:

- **BGG §12a** (Behindertengleichstellungsgesetz): Öffentliche Stellen des Bundes müssen barrierefrei sein.
- **EU-Richtlinie 2016/2102**: Gilt für alle öffentlichen Stellen in der EU.
- **European Accessibility Act** (seit 2025): Gilt auch für viele private Unternehmen.

Als Informatikerinnen und Informatiker tragt ihr die Verantwortung, Technologien so zu gestalten, dass sie allen Menschen zugänglich sind.

---

## Quellen

- WCAG 2.1 Richtlinien (W3C): <https://www.w3.org/TR/WCAG21/>
- MDN Web Docs – Barrierefreiheit: <https://developer.mozilla.org/de/docs/Learn/Accessibility>
- YouTube – „Web Accessibility erklärt" (Google Chrome Developers): <https://www.youtube.com/watch?v=HtTyRajRuyY>
- Bundesfachstelle Barrierefreiheit: <https://www.bundesfachstelle-barrierefreiheit.de>
- Creative Commons – Lizenzen: <https://creativecommons.org/licenses/?lang=de>

---

## Merkblatt – Wichtige Begriffe

| Begriff | Beschreibung |
|---|---|
| WCAG | Web Content Accessibility Guidelines – internationale Richtlinien für Barrierefreiheit |
| Konformitätsstufe A/AA/AAA | A = Mindest, AA = Standard (gesetzlich gefordert), AAA = höchste Anforderung |
| Semantisches HTML | Elemente gemäß ihrer inhaltlichen Bedeutung verwenden |
| `<header>` | Kopfbereich – enthält Name, Foto, Navigation |
| `<nav>` | Navigationsbereich mit Links (z. B. Anker-Links zum Lebenslauf) |
| `<main>` | Hauptinhalt der Seite – nur einmal pro Seite verwenden! |
| `<section>` | Thematischer Abschnitt mit eigener `<h2>`-Überschrift |
| `<footer>` | Fußbereich – enthält Kontakt, Impressum, Quellenangaben |
| Anker-Link | `<a href="#id">` – springt zu einem Abschnitt auf der gleichen Seite |
| ARIA | Accessible Rich Internet Applications – nur einsetzen wenn semantisches HTML nicht reicht |
| `aria-label` | Gibt einem Element einen lesbaren Namen für Screen-Reader |
| `aria-hidden="true"` | Blendet rein dekorative Elemente vor Screen-Readern aus |
| `lang`-Attribut | `<html lang="de">` – Sprachangabe, wichtig für Screen-Reader |
| BGG §12a | Deutsches Gesetz zur barrierefreien Gestaltung öffentlicher Webseiten |
| EU-Richtlinie 2016/2102 | EU-Gesetz – öffentliche Stellen müssen barrierefrei sein |
| Urheberrecht | Fremde Bilder/Texte nur mit Erlaubnis oder unter passender Lizenz nutzen |
| Persönlichkeitsrecht | Fotos anderer Personen nur mit deren ausdrücklicher Zustimmung veröffentlichen |

---

*Lernmodule HTML/CSS/JavaScript – Klasse 9 | Realschule Hessen | Marienschule Offenbach*
*Prozessbezogene Kompetenzen: P1, P2, P3, P5 | Inhaltsbezogene Kompetenzen: I2, I3, I4, I5*
