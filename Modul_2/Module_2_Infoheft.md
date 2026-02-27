# Modul 2 – Informationsheft

## Thema: CSS – Gestaltung und Formatierung von Webseiten

> **Erinnerung:** In Modul 1 hast du die HTML-Grundstruktur deines Lebenslaufs erstellt (`index.html`). In diesem Modul gestaltest du ihn mit CSS – du fügst Farben, Schriftarten und Abstände hinzu. Am Ende kombinieren sich HTML (Struktur) und CSS (Aussehen) zu einer ansehnlichen Webseite.
> 
> **Modul 2:** Du erstellst `style.css` und verlinkst sie mit deiner `index.html`.

---

## Informationstext

**CSS** steht für **Cascading Style Sheets** – gestaffelte Stilvorlagen. Mit CSS bestimmst du Farben, Schriftarten, Abstände, Größen und Layouts von HTML-Elementen. Während HTML die Struktur beschreibt, ist CSS für das Design zuständig. Das Wort _cascading_ (gestaffelt) beschreibt eine wichtige Eigenschaft: CSS-Regeln werden nach einer Prioritätsreihenfolge angewendet – Regeln, die spezifischer formuliert sind oder weiter unten stehen, überschreiben allgemeinere. Dieses Prinzip nennt man die **Kaskade**.

---

### CSS einbinden – die externe CSS-Datei

Die beste Methode ist eine **externe CSS-Datei** (`style.css`), die im `<head>` deiner `index.html` verknüpft wird. So bleiben Inhalt (HTML) und Design (CSS) sauber getrennt:

```html
<!-- In index.html im <head>-Bereich einfügen: -->
<head>
  <meta charset="UTF-8">
  <title>Mein Lebenslauf – Max Mustermann</title>
  <link rel="stylesheet" href="style.css">
</head>
```

Ab diesem Moment gilt alles, was du in `style.css` schreibst, für deine gesamte `index.html`.

---

### Aufbau einer CSS-Regel

Eine CSS-Regel besteht aus einem **Selektor** und einem **Deklarationsblock**. Der Selektor legt fest, welche HTML-Elemente gestaltet werden. Im Deklarationsblock stehen **Eigenschaft** (Property) und **Wert** (Value), getrennt durch einen Doppelpunkt und abgeschlossen durch ein Semikolon.

```css
/* Allgemeines Schema: */
selektor {
  eigenschaft: wert;
  eigenschaft: wert;
}

/* Konkretes Beispiel für den Lebenslauf: */
h1 {
  color: #1F4E79;       /* Schriftfarbe: dunkles Blau */
  font-size: 2em;       /* Schriftgröße: doppelt so groß wie der Standard */
  font-family: Arial, sans-serif;
}
```

---

### Selektoren – was wird gestaltet?

**Tag-Selektor** – gilt für alle Elemente eines Typs:

```css
/* Alle Absätze bekommen dieselbe Schriftart und Zeilenhöhe */
p {
  font-family: Arial, sans-serif;
  line-height: 1.6;
  color: #333333;
}

/* Alle h2-Überschriften (Abschnitte im Lebenslauf) */
h2 {
  color: #2E75B6;
  border-bottom: 2px solid #2E75B6;  /* Trennlinie unter der Überschrift */
  padding-bottom: 4px;
}
```

**Klassen-Selektor** – gilt nur für Elemente mit dem passenden `class`-Attribut:

```html
<!-- In index.html: Dem Element eine Klasse geben -->
<p class="hervorhebung">Klassensprecher, Schuljahr 2023/2024</p>
```

```css
/* In style.css: Die Klasse gestalten */
.hervorhebung {
  background-color: #EBF3FB;
  padding: 8px;
  border-left: 4px solid #2E75B6;
}
```

**ID-Selektor** – gilt für genau ein einziges Element:

```html
<!-- In index.html -->
<h1 id="seitenname">Max Mustermann</h1>
```

```css
/* In style.css */
#seitenname {
  font-size: 2.5em;
  letter-spacing: 2px;   /* Buchstabenabstand */
}
```

> 💡 **Merke:** Klassen (`.`) können mehrfach vorkommen. IDs (`#`) müssen auf der ganzen Seite **eindeutig** sein.

---

### Den gesamten Lebenslauf gestalten – eine komplette `style.css`

Hier siehst du, wie eine vollständige CSS-Datei für deinen Lebenslauf aussehen kann:

```css
/* ===== GRUNDGESTALTUNG DER SEITE ===== */
body {
  background-color: #F5F5F5;  /* Hellgrauer Hintergrund */
  color: #333333;              /* Dunkelgrauer Text */
  font-family: Arial, sans-serif;
  font-size: 1em;
  margin: 0;
  padding: 20px;
}

/* ===== ÜBERSCHRIFTEN ===== */
h1 {
  color: #1F4E79;
  font-size: 2.2em;
}

h2 {
  color: #2E75B6;
  font-size: 1.4em;
  border-bottom: 2px solid #2E75B6;
  padding-bottom: 4px;
  margin-top: 30px;
}

/* ===== ABSÄTZE ===== */
p {
  line-height: 1.7;
}

/* ===== LINKS ===== */
a {
  color: #2E75B6;
  text-decoration: underline;
}

a:hover {
  color: #1F4E79;    /* Farbe wenn Maus drüber ist */
}

/* ===== BILD (Portraitfoto) ===== */
img {
  width: 150px;
  border-radius: 8px;   /* Abgerundete Ecken */
  margin-bottom: 16px;
}

/* ===== HERVORHEBUNGEN ===== */
.hervorhebung {
  background-color: #EBF3FB;
  padding: 8px 12px;
  border-left: 4px solid #2E75B6;
}
```

---

### Das Box-Modell

Jedes HTML-Element wird vom Browser als rechteckige **Box** behandelt. Das Box-Modell beschreibt ihren Aufbau von innen nach außen:

```
┌─────────────────────────────────────────────┐
│                  margin (außen)              │
│  ┌───────────────────────────────────────┐  │
│  │              border (Rahmen)          │  │
│  │  ┌─────────────────────────────────┐  │  │
│  │  │          padding (innen)        │  │  │
│  │  │  ┌───────────────────────────┐  │  │  │
│  │  │  │        content (Inhalt)   │  │  │  │
│  │  │  └───────────────────────────┘  │  │  │
│  │  └─────────────────────────────────┘  │  │
│  └───────────────────────────────────────┘  │
└─────────────────────────────────────────────┘
```

Am Lebenslauf-Abschnitt erklärt:

```css
/* Abschnitt "Über mich" mit sichtbarem Box-Modell */
.abschnitt {
  content: /* der Text darin */;

  padding: 16px;          /* Innenabstand: Luft zwischen Text und Rahmen */
  border: 2px solid #2E75B6;  /* Rahmen: 2px breit, blau */
  margin: 24px 0;         /* Außenabstand: 24px oben und unten, 0 links/rechts */
}
```

---

### Barrierefreiheit und CSS – Kontrast

Die **WCAG** fordern für normalen Text ein Kontrastverhältnis von mindestens **4,5:1** zwischen Text und Hintergrund. Ein gutes Beispiel aus dem Lebenslauf:

```css
/* ✅ GUTES Kontrastverhältnis (~7:1) – barrierefrei */
body {
  background-color: #FFFFFF;  /* Weiß */
  color: #333333;              /* Dunkelgrau */
}

/* ❌ SCHLECHTES Kontrastverhältnis (~2:1) – nicht barrierefrei */
body {
  background-color: #EEEEEE;  /* Hellgrau */
  color: #AAAAAA;              /* Mittelgrau – kaum lesbar! */
}
```

Schriftgrößen sollten in **relativen Einheiten** (`em`, `rem`) angegeben werden – nicht in fixen `px`-Werten – damit Nutzerinnen und Nutzer die Schrift im Browser vergrößern können:

```css
/* ✅ Relativ – skaliert mit der Browser-Einstellung der Nutzerin/des Nutzers */
p {
  font-size: 1em;   /* 1em = Standardgröße des Browsers, meist 16px */
}

/* ⚠️ Absolut – ignoriert die Browsereinstellungen der Nutzerin/des Nutzers */
p {
  font-size: 14px;
}
```

---

## Quellen

- MDN Web Docs – CSS Grundlagen: [https://developer.mozilla.org/de/docs/Learn/CSS/First_steps](https://developer.mozilla.org/de/docs/Learn/CSS/First_steps)
- W3Schools – CSS Tutorial: [https://www.w3schools.com/css/](https://www.w3schools.com/css/)
- YouTube – „CSS in 20 Minuten" (Traversy Media): [https://www.youtube.com/watch?v=yfoY53QXEnI](https://www.youtube.com/watch?v=yfoY53QXEnI)
- WebAIM Kontrast-Checker: [https://webaim.org/resources/contrastchecker/](https://webaim.org/resources/contrastchecker/)
- WCAG 2.1 Richtlinien: [https://www.w3.org/TR/WCAG21/](https://www.w3.org/TR/WCAG21/)

---

## Merkblatt – Wichtige Begriffe

|Begriff|Beschreibung|
|---|---|
|CSS|Cascading Style Sheets – Sprache zur Gestaltung von HTML-Seiten|
|Kaskade|Prioritätsreihenfolge, nach der CSS-Regeln angewendet werden|
|Selektor|Gibt an, welche HTML-Elemente eine CSS-Regel betrifft|
|Eigenschaft (Property)|Stilmerkmal, das verändert werden soll, z. B. `color`, `font-size`|
|Wert (Value)|Konkrete Angabe zur Eigenschaft, z. B. `blue`, `1.5em`|
|`<link rel="stylesheet">`|Verknüpft eine externe CSS-Datei mit dem HTML-Dokument|
|Tag-Selektor|Wählt alle Elemente eines Typs aus, z. B. `p { }`|
|Klassen-Selektor (`.`)|Wählt alle Elemente mit einem bestimmten `class`-Attribut aus|
|ID-Selektor (`#`)|Wählt genau ein Element mit einer bestimmten `id` aus|
|Box-Modell|`content` → `padding` → `border` → `margin` – von innen nach außen|
|`padding`|Innenabstand zwischen Inhalt und Rahmen|
|`margin`|Außenabstand zwischen dem Element und seiner Umgebung|
|`border`|Rahmen um das Element|
|`em` / `rem`|Relative Schriftgrößeneinheiten – empfohlen für Barrierefreiheit|
|WCAG|Web Content Accessibility Guidelines – Richtlinien für Barrierefreiheit|
|Kontrastverhältnis|Helligkeitsunterschied zwischen Text und Hintergrund; Mindestanforderung: 4,5:1|

---

_Lernmodule HTML/CSS/JavaScript – Klasse 9 | Realschule Hessen | Marienschule Offenbach_ _Prozessbezogene Kompetenzen: P1, P2, P3, P5 | Inhaltsbezogene Kompetenzen: I2, I3, I5_
