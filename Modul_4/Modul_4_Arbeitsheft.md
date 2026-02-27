# Modul 4 – Arbeitsheft
## Thema: Barrierefreie Webseiten & Abschlussprojekt

> **Ziel dieses Moduls:** Du vervollständigst deinen Lebenslauf – du bringst semantisches HTML5 ein, stellst Barrierefreiheit sicher und gibst das fertige Projekt über GitHub Education ab.
>
> **Lies zunächst das Informationsheft vollständig durch**, bevor du mit den Aufgaben beginnst. Teilt die Aufgaben so auf, dass beide Teammitglieder aktiv am Code arbeiten.

> **GitHub Education:** Stelle sicher, dass dein Repository **öffentlich** ist und **GitHub Pages** aktiviert ist – deine Lehrkraft ruft die fertige Webseite direkt im Browser auf. Führe nach jeder Aufgabe einen **Commit** durch, z. B. `"M4.3 – Semantisches HTML eingebaut"`.

---

## 🟥 Mindeststandard

### Aufgabe M4.1 – Barrierefreiheit erklären und rechtlichen Rahmen kennen

Schaut euch im Informationsheft den Abschnitt zu **WCAG** und **Informatik, Mensch und Gesellschaft** an. Erklärt euch gegenseitig im Partnerinterview, was Barrierefreiheit im Web bedeutet.

Beantwortet danach schriftlich:
- Nennt **mindestens zwei Personengruppen**, die von barrierefreien Webseiten profitieren, und erklärt je in einem Satz, warum.
- Welches deutsche Gesetz und welche EU-Richtlinie verpflichten öffentliche Stellen zur Barrierefreiheit?

Tragt die rechtlichen Grundlagen in die Tabelle ein:

| Gesetz / Richtlinie | Gilt für | Kernaussage |
|---|---|---|
| BGG §12a | | |
| EU-Richtlinie 2016/2102 | | |
| European Accessibility Act | | |

Orientiert euch an den Stichworten: Screen-Reader · Kontrast · Tastaturnavigation · WCAG · BGG §12a

---

### Aufgabe M4.2 – Checkliste durcharbeiten

Öffnet eure `index.html` und geht die **Barrierefreiheits-Checkliste** aus dem Informationsheft Punkt für Punkt durch. Hakt in der folgenden Tabelle ab, was bereits erfüllt ist, und notiert fehlende Punkte:

| Prüfpunkt | ✅ Erfüllt | ❌ Fehlt noch |
|---|:---:|:---:|
| `<html lang="de">` vorhanden | | |
| `<meta charset="UTF-8">` vorhanden | | |
| Sinnvoller `<title>` vorhanden | | |
| Alle `<img>`-Tags haben ein `alt`-Attribut | | |
| Kontrastverhältnis ≥ 4,5:1 (bereits in M2 geprüft) | | |
| Interaktive Elemente sind `<button>`-Tags | | |
| Seite mit Tab-Taste vollständig bedienbar | | |
| Urheberrecht und Persönlichkeitsrecht beachtet | | |

Ergänzt mindestens **zwei fehlende Punkte** in eurem Code.

---

## 🟩 Regelstandard

### Aufgabe M4.3 – Semantisches HTML einbauen

Schaut euch den **Vorher/Nachher-Vergleich** im Informationsheft genau an. Strukturiert eure `index.html` jetzt so um, dass sie die semantischen HTML5-Elemente verwendet. Ersetzt alle `<div>`-Container durch die passenden semantischen Tags:

```html
<!-- ALT (ersetzen): -->
<div id="kopf"> ... </div>
<div id="inhalt"> ... </div>
<div id="fuss"> ... </div>

<!-- NEU (einsetzen): -->
<header> ... </header>
<main> ... </main>
<footer> ... </footer>
```

Sorgt dafür, dass eure Seite folgende Struktur hat (wie in der vollständigen `index.html` im Informationsheft gezeigt):

```html
<header>
  <!-- Name, Foto, Navigation -->
</header>

<main>
  <section id="ueber-mich"> ... </section>
  <section id="schulbildung"> ... </section>
  <section id="hobbys"> ... </section>
</main>

<footer id="kontakt">
  <!-- Kontakt, Quellenangaben -->
</footer>
```

Testet anschließend mit der **Tab-Taste**, ob alle Links und Buttons erreichbar sind. Erklärt schriftlich in **mindestens 3 Sätzen**, warum semantisches HTML für Screen-Reader-Nutzerinnen und -Nutzer einen konkreten Unterschied im Alltag macht.

---

### Aufgabe M4.4 – Barrierefreiheit gesellschaftlich bewerten

Lest im Informationsheft den Abschnitt **„Informatik, Mensch und Gesellschaft"** noch einmal durch. Diskutiert in der Gruppe: Sollte Barrierefreiheit auch für **private Webseiten** (z. B. Blogs, Portfolios) verpflichtend sein?

Formuliert **je zwei Argumente** dafür und dagegen und haltet eure gemeinsame Position in **mindestens 5 Sätzen** fest. Bringt dabei folgende Begriffe ein:

> gesellschaftliche Teilhabe · Datenschutz · Urheberrecht · European Accessibility Act

---

## 🟦 Expertenstandard

### Aufgabe M4.5 – Navigation mit Anker-Links und ARIA einbauen

Schaut euch das **vollständige `<header>`-Beispiel** im Informationsheft an. Baut eine funktionierende Navigation in euren `<header>` ein, die auf alle Abschnitte eurer Seite verlinkt:

```html
<nav aria-label="Seitennavigation">
  <a href="#ueber-mich">Über mich</a>
  <a href="#schulbildung">Schulbildung</a>
  <a href="#hobbys">Hobbys</a>
  <a href="#kontakt">Kontakt</a>
</nav>
```

Stellt sicher, dass jeder verlinkten `<section>` die passende `id` gesetzt ist, z. B.:

```html
<section id="ueber-mich">
  <h2>Über mich</h2>
  ...
</section>
```

Fügt außerdem an passenden Stellen `aria-hidden="true"` für rein dekorative Elemente ein. Erklärt schriftlich in **mindestens 4 Sätzen**: Was sind ARIA-Attribute? Warum ist bei der Navigation `aria-label` sinnvoll? Wann ist semantisches HTML vorzuziehen?

---

### Aufgabe M4.6 – Code-Review mit einem anderen Team

Tauscht euren Repository-Link mit einem anderen Team aus. Überprüft deren Webseite systematisch anhand der vollständigen **Barrierefreiheits-Checkliste** aus dem Informationsheft sowie der Anforderungen aller vier Module.

Gebt dem anderen Team schriftliches Feedback mit **mindestens drei konkreten, begründeten Verbesserungsvorschlägen** – formuliert sie konstruktiv:

| Nr. | Gefundenes Problem | Konkreter Verbesserungsvorschlag |
|---|---|---|
| 1 | | |
| 2 | | |
| 3 | | |

Nehmt das Feedback des anderen Teams entgegen. Bearbeitet mindestens **zwei der erhaltenen Vorschläge** und dokumentiert die Änderungen als eigenen Commit mit der Nachricht `"M4.6 – Code-Review-Feedback eingearbeitet"`.

---

## Reflexion – Rückblick auf alle vier Module

Bewertet abschließend euren gesamten Lernprozess und eure fertige Webseite.

| Reflexionssatz | 😊 | 😐 | 😔 |
|---|:---:|:---:|:---:|
| Ich kann Barrierefreiheit im Web erklären und rechtliche Grundlagen benennen. | | | |
| Ich verwende semantische HTML5-Elemente korrekt in meiner Webseite. | | | |
| Ich habe das WCAG-Kontrastverhältnis (4,5:1) in meiner Webseite eingehalten. | | | |
| Meine Webseite ist mit der Tab-Taste vollständig bedienbar. | | | |
| Ich kann HTML, CSS und JavaScript sinnvoll in einer Webseite kombinieren. | | | |
| Ich habe das Urheberrecht und Persönlichkeitsrecht bei meinen Inhalten beachtet. | | | |
| Ich bin stolz auf die Webseite, die ich in allen vier Modulen erstellt habe. | | | |
| Ich habe regelmäßig Commits mit sinnvollen Beschreibungen gemacht. | | | |

---

*Lernmodule HTML/CSS/JavaScript – Klasse 9 | Realschule Hessen | Marienschule Offenbach*
*Abzugeben: dieses Arbeitsheft (gedruckt oder als PDF) | GitHub Education Repository-URL mit aktiviertem GitHub Pages*
