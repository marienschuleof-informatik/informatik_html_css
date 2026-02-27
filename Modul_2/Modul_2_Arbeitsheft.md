# Modul 2 – Arbeitsheft
## Thema: CSS – Gestaltung und Formatierung

> **Ziel dieses Moduls:** In diesen beiden Unterrichtsstunden gestaltest du deinen Lebenslauf aus Modul 1 mit CSS. Du erstellst eine Datei `style.css` in deinem GitHub Education Repository und verlinkst sie mit deiner `index.html`.
>
> **Lies zunächst das Informationsheft vollständig durch**, bevor du mit den Aufgaben beginnst. Arbeite wieder mit deiner Partnerin oder deinem Partner zusammen.

> **GitHub Education:** Lege `style.css` im selben Ordner wie `index.html` ab. Führe nach jeder abgeschlossenen Aufgabe einen **Commit** durch, z. B. `"M2.2 – style.css erstellt und verlinkt"`.

---

## 🟥 Mindeststandard

### Aufgabe M2.1 – CSS-Regelaufbau erklären

Schaut euch gemeinsam das CSS-Regelbeispiel im Informationsheft an:

```css
h1 {
  color: #1F4E79;
  font-size: 2em;
  font-family: Arial, sans-serif;
}
```

Führt ein **Partnerinterview** durch: Eine Person erklärt der anderen, was **Selektor**, **Eigenschaft** und **Wert** in dieser Regel bedeuten. Dann tauscht ihr die Rollen.

Notiert eure Erklärungen anschließend schriftlich, indem ihr die Tabelle ausfüllt:

| Begriff | Wert aus dem Beispiel | Bedeutung in eigenen Worten |
|---|---|---|
| Selektor | | |
| Eigenschaft (1) | | |
| Wert (1) | | |
| Eigenschaft (2) | | |
| Wert (2) | | |

---

### Aufgabe M2.2 – `style.css` erstellen und verlinken

Erstellt eine neue Datei `style.css`. Fügt zuerst in eurer `index.html` im `<head>`-Bereich den folgenden Link-Tag ein – genau wie im Informationsheft gezeigt:

```html
<link rel="stylesheet" href="style.css">
```

Schreibt dann in `style.css` folgende Grundgestaltung und passt die Farben nach eurem Geschmack an:

```css
body {
  background-color: #F5F5F5;
  color: #333333;
  font-family: Arial, sans-serif;
  padding: 20px;
}

h1 {
  color: #1F4E79;
  font-size: 2.2em;
}
```

Öffnet die Seite im Browser. Vergleicht das Ergebnis mit dem eurer Sitznachbarin oder eures Sitznachbarn. Was fällt auf?

---

## 🟩 Regelstandard

### Aufgabe M2.3 – Lebenslauf-Abschnitte gestalten

Schaut euch die **vollständige `style.css`** im Informationsheft an. Übertragt die Regeln für `h2`, `p`, `a` und `a:hover` in eure eigene `style.css` und passt die Farben so an, dass sie zu eurem persönlichen Design passen.

Fügt außerdem eine **Klasse** hinzu. Vergebt in `index.html` einem besonderen Absatz (z. B. eine Auszeichnung oder ein besonderes Hobby) die Klasse `hervorhebung`:

```html
<p class="hervorhebung">Klassensprecher, Schuljahr 2023/2024</p>
```

Und gestaltet diese Klasse in `style.css`:

```css
.hervorhebung {
  background-color: #EBF3FB;
  padding: 8px 12px;
  border-left: 4px solid #2E75B6;
}
```

Erklärt euch gegenseitig schriftlich in **2 Sätzen**: Was ist der Unterschied zwischen einem **Tag-Selektor** und einem **Klassen-Selektor**? Warum ist die Klasse hier die bessere Wahl als ein Tag-Selektor?

---

### Aufgabe M2.4 – Das Box-Modell begreifen und anwenden

Schaut euch das **Box-Modell-Diagramm** im Informationsheft an. Wählt einen Abschnitt eures Lebenslaufs (z. B. „Über mich") und gebt ihm in `index.html` die Klasse `abschnitt`:

```html
<section>
  <h2>Über mich</h2>
  <p class="abschnitt">Ich bin 15 Jahre alt...</p>
</section>
```

Gestaltet diese Klasse in `style.css` und setzt bewusst alle vier Box-Modell-Eigenschaften:

```css
.abschnitt {
  padding: 16px;
  border: 2px solid #2E75B6;
  margin: 24px 0;
}
```

Zeichnet danach das Box-Modell dieses Elements **auf Papier** und beschriftet alle vier Bereiche (`content`, `padding`, `border`, `margin`) mit den von euch gewählten Werten. Erklärt schriftlich in **2 Sätzen** den Unterschied zwischen `padding` und `margin`.

---

## 🟦 Expertenstandard

### Aufgabe M2.5 – Kontrast prüfen und WCAG bewerten

Schaut euch den Kontrast-Vergleich im Informationsheft an:

```css
/* ✅ GUTES Kontrastverhältnis */
body { background-color: #FFFFFF; color: #333333; }

/* ❌ SCHLECHTES Kontrastverhältnis */
body { background-color: #EEEEEE; color: #AAAAAA; }
```

Überprüft die Farbkombination eurer eigenen `style.css` mit dem [WebAIM Kontrast-Checker](https://webaim.org/resources/contrastchecker/). Tragt die Ergebnisse hier ein:

| Hintergrundfarbe | Textfarbe | Gemessenes Verhältnis | WCAG AA erfüllt? |
|---|---|---|---|
| | | | |

Falls das Verhältnis unter **4,5:1** liegt, passt eure Farben an und dokumentiert die neue Kombination. Erklärt schriftlich in **mindestens 3 Sätzen**, warum dieser Standard existiert und welche gesellschaftliche Bedeutung er hat.

---

### Aufgabe M2.6 – Relative Einheiten und Media-Query

Schaut euch den Vergleich zwischen `px` und `em` im Informationsheft an. Ändert alle fixen `px`-Schriftgrößen in eurer `style.css` auf `em`-Werte um und begründet schriftlich in **2 Sätzen**, warum das für die Barrierefreiheit wichtig ist.

Recherchiert anschließend, was eine **Media-Query** in CSS ist, und fügt folgende Regel in eure `style.css` ein:

```css
@media (max-width: 600px) {
  body {
    font-size: 0.9em;
    padding: 10px;
  }
}
```

Erklärt schriftlich in **mindestens 3 Sätzen**: Was bewirkt diese Regel? Warum ist responsives Design heute notwendig? Welche Personengruppen profitieren besonders davon?

---

## Reflexion

Bewertet am Ende der Stunde, wie gut ihr die CSS-Grundlagen verstanden habt.

| Reflexionssatz | 😊 | 😐 | 😔 |
|---|:---:|:---:|:---:|
| Ich kann eine CSS-Regel (Selektor, Eigenschaft, Wert) erklären und schreiben. | | | |
| Ich kann eine externe CSS-Datei erstellen und korrekt mit HTML verlinken. | | | |
| Ich kenne den Unterschied zwischen Tag-Selektor und Klassen-Selektor. | | | |
| Ich verstehe das Box-Modell und habe es auf Papier gezeichnet. | | | |
| Ich habe das Kontrastverhältnis meiner Seite geprüft und dokumentiert. | | | |
| Ich verwende relative Einheiten (`em`) statt fixer `px`-Angaben. | | | |
| Ich habe nach jeder Aufgabe einen Commit in GitHub Education gemacht. | | | |

---

*Lernmodule HTML/CSS/JavaScript – Klasse 9 | Realschule Hessen | Marienschule Offenbach*
*Abzugeben: dieses Arbeitsheft (gedruckt oder als PDF) | `style.css` im GitHub Education Repository*
