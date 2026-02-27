# Modul 3 – Informationsheft

## Thema: JavaScript – Einführung in die Skript-Programmierung

> **Erinnerung:** In Modul 1 hast du die HTML-Struktur (`index.html`) und in Modul 2 das CSS-Design (`style.css`) deines Lebenslaufs erstellt. In diesem Modul machst du ihn **interaktiv**: Schaltflächen reagieren auf Klicks, Texte ändern sich dynamisch.
> 
> **Modul 3:** Du erstellst `script.js` und verlinkst sie am Ende des `<body>` deiner `index.html`.

---

## Informationstext

**JavaScript** ist eine **Skript-Programmiersprache**, die direkt im Browser ausgeführt wird. Gemeinsam mit HTML und CSS bildet sie das Fundament jeder modernen Webseite:

|Sprache|Zuständigkeit|Datei|
|---|---|---|
|HTML|**Struktur** – welche Inhalte gibt es?|`index.html`|
|CSS|**Aussehen** – wie sehen sie aus?|`style.css`|
|JavaScript|**Verhalten** – was passiert bei Interaktion?|`script.js`|

JavaScript ist eine **Skriptsprache**: Der Browser führt den Code Zeile für Zeile aus, ohne einen vorherigen Kompilierungsschritt – der Browser ist der **Interpreter**. Das ist anders als bei Java oder C++, die erst in Maschinencode _kompiliert_ werden müssen.

---

### JavaScript einbinden

JavaScript wird in einer externen Datei `script.js` gespeichert und mit dem `<script>`-Tag **am Ende des `<body>`** eingebunden – nicht im `<head>`!

```html
<!-- In index.html – das <script>-Tag gehört ans Ende des <body> -->
<body>
  <h1>Max Mustermann</h1>
  <p>...</p>

  <!-- ✅ RICHTIG: am Ende des body -->
  <script src="script.js"></script>
</body>
```

> ⚠️ **Warum am Ende des `<body>`?** Der Browser liest HTML von oben nach unten. Steht das `<script>`-Tag im `<head>`, versucht JavaScript auf HTML-Elemente zuzugreifen, die noch gar nicht geladen sind – das führt zu Fehlern. Am Ende des `<body>` sind alle Elemente bereits im DOM vorhanden.

---

### Syntax und Semantik in JavaScript

Wie in allen Programmiersprachen gibt es in JavaScript den Unterschied zwischen **Syntax** und **Semantik**:

- Die **Syntax** beschreibt die formalen Schreibregeln. Ein Syntaxfehler verhindert die Ausführung des Programms.
- Die **Semantik** beschreibt die Bedeutung des Codes – was er tatsächlich bewirkt. Ein Semantikfehler lässt das Programm laufen, aber es macht etwas anderes als gewollt.

```javascript
// ✅ Syntaktisch korrekt UND semantisch sinnvoll:
let name = "Max";

// ❌ Syntaxfehler – fehlende Anführungszeichen, Programm startet nicht:
let name = Max;

// ⚠️ Syntaktisch korrekt, aber semantisch falsch (falscher Wert):
let alter = "fünfzehn";  // alter sollte eine Zahl sein, nicht ein Text
```

---

### Variablen – Daten speichern

Eine **Variable** ist ein benannter Speicherplatz für Daten. In JavaScript gibt es `let` für veränderbare und `const` für unveränderliche Werte:

```javascript
// Daten aus dem Lebenslauf speichern:
const name = "Max Mustermann";        // Konstante – ändert sich nie
const geburtsjahr = 2009;             // Konstante – Zahl, keine Anführungszeichen
let lieblingshobbys = "Fußball";      // Variable – könnte sich ändern

// Auf der Konsole ausgeben (zum Testen):
console.log(name);          // → "Max Mustermann"
console.log(geburtsjahr);   // → 2009
```

> 💡 **Faustregel:** Nimm `const`, wenn sich der Wert nie ändern wird. Nimm `let`, wenn er später überschrieben werden soll. Vermeide das veraltete `var`.

---

### Den DOM manipulieren – HTML-Elemente verändern

Das **Document Object Model (DOM)** ist die interne Baumstruktur des HTML-Dokuments im Browser. JavaScript kann darauf zugreifen und es verändern.

**Schritt 1:** Element im HTML mit einer `id` versehen:

```html
<!-- In index.html -->
<p id="willkommen">Willkommen auf meiner Webseite!</p>
<button id="begruessung-button">Klick mich!</button>
```

**Schritt 2:** In `script.js` das Element auswählen und verändern:

```javascript
// Element anhand der ID auswählen:
let absatz = document.getElementById("willkommen");

// Textinhalt des Elements ändern:
absatz.textContent = "Hallo! Schön, dass du meinen Lebenslauf besuchst.";

// Oder den Stil direkt ändern:
absatz.style.color = "#2E75B6";
```

---

### Funktionen – wiederverwendbarer Code

Eine **Funktion** ist ein benannter, wiederverwendbarer Codeblock:

```javascript
// Funktion definieren:
function begruessen() {
  // Das Element mit der ID "willkommen" auswählen:
  let absatz = document.getElementById("willkommen");
  // Seinen Textinhalt ändern:
  absatz.textContent = "Hallo! Ich bin Max – schön, dass du vorbeischaust.";
}

// Funktion aufrufen (ausführen):
begruessen();
```

---

### Ereignisse und Event-Listener – auf Klicks reagieren

Das **Grundprinzip der Ereignissteuerung** bedeutet: Das Programm läuft nicht einfach von oben nach unten durch, sondern es **wartet** auf Ereignisse (Events) wie Mausklicks oder Tastendrücke und reagiert dann darauf.

```javascript
// Den Button aus dem DOM holen:
let button = document.getElementById("begruessung-button");

// Einen Event-Listener hinzufügen:
// "Wenn der Button angeklickt wird, führe die Funktion begruessen() aus"
button.addEventListener("click", begruessen);

function begruessen() {
  let absatz = document.getElementById("willkommen");
  absatz.textContent = "Hallo! Ich bin Max – schön, dass du vorbeischaust.";
}
```

**Oder mit einer anonymen Funktion direkt im Event-Listener:**

```javascript
let button = document.getElementById("begruessung-button");

button.addEventListener("click", function() {
  document.getElementById("willkommen").textContent =
    "Hallo! Ich bin Max – schön, dass du vorbeischaust.";
  document.body.style.backgroundColor = "#EBF3FB";
});
```

---

### Vollständiges Beispiel – `script.js` für den Lebenslauf

So könnte deine fertige `script.js` aussehen, nachdem du Modul 3 abgeschlossen hast:

```javascript
// ===== LEBENSLAUF – script.js =====

// ---- Begrüßungs-Button ----
let begruessung = document.getElementById("begruessung-button");

begruessung.addEventListener("click", function() {
  document.getElementById("willkommen").textContent =
    "Hallo! Ich freue mich über deinen Besuch auf meiner Seite.";
});

// ---- Design-Wechsel-Button ----
let designButton = document.getElementById("design-button");
let dunkelModus = false;  // Variable: ist der dunkle Modus aktiv?

designButton.addEventListener("click", function() {
  if (dunkelModus === false) {
    // Dunklen Modus aktivieren:
    document.body.style.backgroundColor = "#1A1A2E";
    document.body.style.color = "#FFFFFF";
    dunkelModus = true;
  } else {
    // Hellen Modus wiederherstellen:
    document.body.style.backgroundColor = "#F5F5F5";
    document.body.style.color = "#333333";
    dunkelModus = false;
  }
});

// ---- Datum und Uhrzeit beim Laden der Seite anzeigen ----
window.addEventListener("load", function() {
  const jetzt = new Date();
  const datum = jetzt.toLocaleDateString("de-DE");
  const uhrzeit = jetzt.toLocaleTimeString("de-DE");
  document.getElementById("zeitanzeige").textContent =
    "Heute ist der " + datum + " um " + uhrzeit + " Uhr.";
});
```

**Das passende HTML dazu in `index.html`:**

```html
<!-- Buttons für die JavaScript-Funktionen -->
<button id="begruessung-button">Begrüße mich!</button>
<button id="design-button">Design wechseln</button>

<!-- Ausgabe-Bereiche -->
<p id="willkommen">Willkommen auf meiner Webseite!</p>
<p id="zeitanzeige"></p>
```

---

### Barrierefreiheit und JavaScript

```html
<!-- ✅ RICHTIG – semantischer Button, tastaturzugänglich, von Screen-Readern erkannt -->
<button id="begruessung-button">Begrüße mich!</button>

<!-- ❌ FALSCH – ein <div> ist kein Button! Nicht tastaturzugänglich,
     Screen-Reader erkennt die Funktion nicht -->
<div id="begruessung-button">Begrüße mich!</div>
```

Das `<button>`-Element ist automatisch mit der Tab-Taste fokussierbar und mit Enter aktivierbar – ein `<div>` nicht. Teste deine Seite immer mit der Tab-Taste: Kannst du alle Buttons ohne Maus erreichen?

---

## Quellen

- MDN Web Docs – JavaScript Grundlagen: [https://developer.mozilla.org/de/docs/Learn/JavaScript/First_steps](https://developer.mozilla.org/de/docs/Learn/JavaScript/First_steps)
- W3Schools – JavaScript Tutorial: [https://www.w3schools.com/js/](https://www.w3schools.com/js/)
- JavaScript - Teil 1 - Eine Einführung: [https://youtu.be/EfVNy15itHA](https://youtu.be/EfVNy15itHA)
- JavaScript - Teil 2 - Abfragen und Schleifen: [https://youtu.be/KTu9XomNHbA](https://youtu.be/KTu9XomNHbA)
- JavaScript - Teil 3 - Funktionen: [https://youtu.be/Xgckg_Ek4CU](https://youtu.be/Xgckg_Ek4CU)

---

## Merkblatt – Wichtige Begriffe

|Begriff|Beschreibung|
|---|---|
|JavaScript|Skript-Programmiersprache für interaktives Verhalten; läuft im Browser|
|Interpreter|Führt Code Zeile für Zeile aus – hier: der Browser|
|`<script src="...">`|Bindet eine externe JavaScript-Datei ein (ans Ende des `<body>`)|
|`const`|Deklariert eine unveränderliche Konstante, z. B. `const name = "Max";`|
|`let`|Deklariert eine veränderbare Variable, z. B. `let modus = false;`|
|Funktion|Wiederverwendbarer Codeblock, definiert mit `function name() { }`|
|Event (Ereignis)|Benutzeraktion, z. B. Klick (`click`), Seitenaufruf (`load`)|
|Event-Listener|`addEventListener("click", funktion)` – reagiert auf ein Ereignis|
|Ereignissteuerung|Programm wartet auf Ereignisse statt linear abzulaufen|
|DOM|Document Object Model – interne Baumstruktur des HTML im Browser|
|`getElementById()`|Wählt ein HTML-Element anhand seiner `id` aus|
|`textContent`|Liest oder ändert den Textinhalt eines Elements|
|`style.backgroundColor`|Ändert die Hintergrundfarbe eines Elements per JavaScript|
|Syntax|Formale Schreibregeln – Fehler verhindern die Ausführung|
|Semantik|Bedeutung des Codes – Fehler führen zu falschem Verhalten|
|`<button>`|Semantisches Element für Schaltflächen – tastaturzugänglich|

---

_Lernmodule HTML/CSS/JavaScript – Klasse 9 | Realschule Hessen | Marienschule Offenbach_ _Prozessbezogene Kompetenzen: P1, P2, P3, P5 | Inhaltsbezogene Kompetenzen: I1, I2, I4, I5_
