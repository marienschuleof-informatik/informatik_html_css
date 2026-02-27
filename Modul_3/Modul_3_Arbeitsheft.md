# Modul 3 – Arbeitsheft
## Thema: JavaScript – Einführung in die Skript-Programmierung

> **Ziel dieses Moduls:** In diesen beiden Unterrichtsstunden erweiterst du deinen Lebenslauf um interaktive Elemente. Du erstellst eine Datei `script.js` und verlinkst sie am Ende des `<body>` deiner `index.html`.
>
> **Lies zunächst das Informationsheft vollständig durch**, bevor du mit den Aufgaben beginnst. Teilt die Aufgaben so auf, dass beide Teammitglieder aktiv am Code arbeiten.

> **GitHub Education:** Lege `script.js` im selben Ordner wie `index.html` ab. Führe nach jeder abgeschlossenen Aufgabe einen **Commit** durch, z. B. `"M3.2 – Begrüßungs-Button implementiert"`.

---

## 🟥 Mindeststandard

### Aufgabe M3.1 – JavaScript einordnen und Einbindung verstehen

Schaut euch die **Übersichtstabelle** am Anfang des Informationsheftes an:

| Sprache | Zuständigkeit | Datei |
|---|---|---|
| HTML | Struktur | `index.html` |
| CSS | Aussehen | `style.css` |
| JavaScript | Verhalten | `script.js` |

Diskutiert im Partnerinterview: Was bedeutet „Verhalten" einer Webseite konkret? Nennt drei Beispiele für Interaktionen, die ihr euch für euren Lebenslauf vorstellen könntet.

Erklärt außerdem schriftlich in **mindestens 4 Sätzen** den Unterschied zwischen einem **Interpreter** und einem **Compiler** – und warum der Browser bei JavaScript der Interpreter ist. Geht auch auf den Unterschied zwischen **Syntax-** und **Semantikfehlern** ein. Orientiert euch an den Codebeispielen im Informationsheft:

```javascript
// ✅ Korrekt:         let name = "Max";
// ❌ Syntaxfehler:    let name = Max;
// ⚠️ Semantikfehler: let alter = "fünfzehn";
```

---

### Aufgabe M3.2 – `script.js` erstellen und ersten Button einbauen

Fügt in eurer `index.html` im Abschnitt „Über mich" folgende zwei Elemente ein – genauso wie im Informationsheft gezeigt:

```html
<p id="willkommen">Willkommen auf meiner Webseite!</p>
<button id="begruessung-button">Begrüße mich!</button>
```

Erstellt dann die Datei `script.js` und schreibt folgenden Code hinein:

```javascript
let button = document.getElementById("begruessung-button");

button.addEventListener("click", function() {
  document.getElementById("willkommen").textContent =
    "Hallo! Ich freue mich über deinen Besuch auf meiner Seite.";
});
```

Bindet die Datei **am Ende des `<body>`** in `index.html` ein:

```html
  <script src="script.js"></script>
</body>
```

Testet den Button im Browser. Erklärt schriftlich in **2 Sätzen**, warum das `<script>`-Tag ans Ende des `<body>` gehört und was passiert, wenn es stattdessen im `<head>` steht.

---

## 🟩 Regelstandard

### Aufgabe M3.3 – Dunkel-Modus und Ereignissteuerung

Fügt in eurer `index.html` einen zweiten Button hinzu:

```html
<button id="design-button">Design wechseln</button>
```

Erweitert `script.js` um den **Dunkel-Modus-Wechsel** aus dem Informationsheft:

```javascript
let designButton = document.getElementById("design-button");
let dunkelModus = false;

designButton.addEventListener("click", function() {
  if (dunkelModus === false) {
    document.body.style.backgroundColor = "#1A1A2E";
    document.body.style.color = "#FFFFFF";
    dunkelModus = true;
  } else {
    document.body.style.backgroundColor = "#F5F5F5";
    document.body.style.color = "#333333";
    dunkelModus = false;
  }
});
```

Fügt zu **jeder Zeile** einen kurzen Kommentar (mit `//`) hinzu, der erklärt, was diese Zeile tut.

Erklärt dann schriftlich in **2 Sätzen**, was das **Grundprinzip der Ereignissteuerung** bedeutet und worin der Unterschied zu einem Programm liegt, das einfach von oben nach unten durchläuft.

---

### Aufgabe M3.4 – `const` vs. `let` und Fehleranalyse

Schaut euch das `const`-/`let`-Beispiel im Informationsheft an:

```javascript
const name = "Max Mustermann";  // Konstante
let dunkelModus = false;        // Variable
```

Beantwortet schriftlich:
- Warum ist `name` eine `const` und `dunkelModus` ein `let`?
- Was würde passieren, wenn ihr versucht, `name` später zu überschreiben?

Öffnet die **Browser-Entwicklertools** (Taste `F12` → Reiter „Konsole"). Baut absichtlich einen **Syntaxfehler** in euren Code ein (z. B. eine fehlende geschweifte Klammer), speichert und schaut, welche Fehlermeldung erscheint. Notiert die Meldung und erklärt, ob es sich um einen Syntax- oder Semantikfehler handelt. Korrigiert den Fehler danach wieder.

| Eingebauter Fehler | Fehlermeldung in der Konsole | Fehlertyp (Syntax/Semantik) |
|---|---|---|
| | | |

---

## 🟦 Expertenstandard

### Aufgabe M3.5 – Datum und Uhrzeit mit dem `Date`-Objekt

Fügt in `index.html` im Abschnitt „Über mich" folgendes Element ein:

```html
<p id="zeitanzeige"></p>
```

Erweitert `script.js` um die Datum-/Uhrzeit-Anzeige aus dem Informationsheft:

```javascript
window.addEventListener("load", function() {
  const jetzt = new Date();
  const datum = jetzt.toLocaleDateString("de-DE");
  const uhrzeit = jetzt.toLocaleTimeString("de-DE");
  document.getElementById("zeitanzeige").textContent =
    "Heute ist der " + datum + " um " + uhrzeit + " Uhr.";
});
```

Erklärt schriftlich in **mindestens 3 Sätzen**: Was ist ein **Objekt** in JavaScript? Was sind **Methoden** und **Eigenschaften** eines Objekts? Welche Methoden des `Date`-Objekts verwendet ihr hier, und was geben sie zurück?

---

### Aufgabe M3.6 – Barrierefreiheit der JavaScript-Elemente prüfen

Schaut euch den Barrierefreiheits-Vergleich im Informationsheft an:

```html
<!-- ✅ RICHTIG -->
<button id="begruessung-button">Begrüße mich!</button>

<!-- ❌ FALSCH -->
<div id="begruessung-button">Begrüße mich!</div>
```

Testet eure fertige Seite, indem ihr ausschließlich die **Tab-Taste** benutzt: Könnt ihr alle Buttons ohne Maus erreichen und mit **Enter** aktivieren?

Diskutiert in der Gruppe und haltet das Ergebnis in **mindestens 5 Sätzen** fest:
- Was würde passieren, wenn ihr `<div>` statt `<button>` verwenden würdet?
- Welche Personengruppen sind auf Tastaturnavigation angewiesen?
- Wie hängen **Barrierefreiheit**, **Screen-Reader** und **Ereignissteuerung** zusammen?

---

## Reflexion

Bewertet am Ende der Stunde, wie sicher ihr euch mit JavaScript fühlt.

| Reflexionssatz | 😊 | 😐 | 😔 |
|---|:---:|:---:|:---:|
| Ich kann erklären, was JavaScript ist und welche Rolle es im Web spielt. | | | |
| Ich verstehe den Unterschied zwischen Syntax- und Semantikfehlern. | | | |
| Ich kann eine JavaScript-Datei erstellen und korrekt mit HTML verknüpfen. | | | |
| Ich verstehe, was ein Event-Listener ist, und kann ihn erklären. | | | |
| Ich kann mit `getElementById()` auf HTML-Elemente zugreifen. | | | |
| Ich habe Fehlermeldungen in der Browser-Konsole gelesen und genutzt. | | | |
| Ich habe Barrierefreiheitsaspekte in meiner Implementierung berücksichtigt. | | | |
| Ich habe nach jeder Aufgabe einen Commit in GitHub Education gemacht. | | | |

---

*Lernmodule HTML/CSS/JavaScript – Klasse 9 | Realschule Hessen | Marienschule Offenbach*
*Abzugeben: dieses Arbeitsheft (gedruckt oder als PDF) | `script.js` im GitHub Education Repository*
