# Bremer Windsurfing Club e.V. – Website

Die Website des Bremer Windsurfing Club e.V., gebaut mit [Hugo](https://gohugo.io/) und gehostet auf [GitHub Pages](https://pages.github.com/).

---

## Für Nicht-Techniker: So bearbeitet ihr die Website

### Texte ändern

Alle Texte der Website befinden sich im Ordner **`content/`**. Die Dateien sind im Markdown-Format (`.md`) – das ist reiner Text mit ein paar einfachen Formatierungen.

| Seite                     | Datei                              |
|---------------------------|------------------------------------|
| **Startseite**            | `content/_index.md`                |
| **Verein / Vorstand**     | `content/verein/_index.md`         |
| **Sport / Training**      | `content/sport/_index.md`          |
| **Termine & Fahrten**     | `content/termine/index.md`         |
| **Mitmachen / Beitritt**  | `content/mitmachen/_index.md`      |
| **Kontakt / Impressum**   | `content/kontakt/index.md`         |

#### Markdown-Kurzanleitung

```markdown
# Große Überschrift
## Mittlere Überschrift
### Kleine Überschrift

**Fetter Text**
*Kursiver Text*

- Aufzählung Punkt 1
- Aufzählung Punkt 2

[Link-Text](https://www.beispiel.de)

![Bildbeschreibung](images/mein-bild.jpg)
```

### Bilder hochladen

1. Legt euer Bild in den Ordner **`staticimages/`**
2. Benennt es sinnvoll (z.B. `training-2026.jpg` – keine Leerzeichen, keine Umlaute!)
3. Verwendet es in einer Markdown-Datei so:
   ```markdown
   ![Beschreibung des Bildes](images/training-2026.jpg)
   ```

### PDFs hochladen

1. Legt eure PDF-Datei in den Ordner **`static/pdf/`**
2. Verlinkt sie im Markdown so:
   ```markdown
   [Dokumentname](/pdf/mein-dokument.pdf)
   ```

### Das Hintergrundbild ändern

1. Legt ein neues Bild in **`staticimages/`** (z.B. `header-neu.jpg`)
2. Öffnet die Datei **`hugo.toml`**
3. Sucht die Zeile `featured_image = 'images/topbildbwc.jpg'`
4. Ändert den Dateinamen

### Termine aktualisieren

1. Öffnet die Datei **`content/termine/index.md`**
2. Passt die Termine in den `<div class="termin-item">` Blöcken an
3. Kopiert einen bestehenden Block und ändert Datum und Text

### Vorstandsmitglieder ändern

1. Öffnet die Datei **`content/verein/_index.md`**
2. Ändert die Namen und E-Mail-Adressen in den `<div class="vorstand-card">` Blöcken

---

## Änderungen veröffentlichen

### Option A: Direkt auf GitHub (einfachste Methode)

1. Geht auf eure GitHub-Repository-Seite
2. Navigiert zur gewünschten Datei
3. Klickt auf das **Stift-Symbol** (Edit)
4. Macht eure Änderungen
5. Klickt auf **"Commit changes"**
6. Die Website wird automatisch in ca. 1-2 Minuten aktualisiert!

### Option B: Über Git (für Fortgeschrittene)

```bash
git add .
git commit -m "Text aktualisiert"
git push
```

---

## Für Entwickler

### Voraussetzungen

- [Hugo Extended](https://gohugo.io/installation/) (v0.147.0+)
- [Go](https://go.dev/dl/) (für Hugo Module)
- [Git](https://git-scm.com/)

### Lokale Entwicklung

```bash
# Repository klonen
git clone https://github.com/bremerwindsurfing/website.git
cd website

# Lokalen Server starten
hugo server -D

# Website öffnen: http://localhost:1313/
```

### Projektstruktur

```
├── content/                  ← Alle Texte und Inhalte
│   ├── _index.md             ← Startseite
│   ├── verein/_index.md      ← Vorstand, Satzung, Organisation
│   ├── sport/_index.md       ← Training, Material, Regeln
│   ├── termine/index.md      ← Termine & Fahrten
│   ├── mitmachen/_index.md   ← Beitritt, Surfschein, Kündigung
│   └── kontakt/index.md      ← Kontakt, Impressum, Datenschutz
├── static/
│   ├── images/               ← Bilder (Logo, Header, Fotos)
│   ├── pdf/                  ← PDFs (Satzung, Regeln, etc.)
│   └── css/custom.css        ← Eigenes Design (Farben, Layout)
├── layouts/partials/         ← Layout-Anpassungen (Footer, etc.)
├── hugo.toml                 ← Konfiguration (Vereinsname, Menü)
├── go.mod                    ← Hugo-Module (Theme-Verwaltung)
└── .github/workflows/        ← Automatisches Deployment
```

### GitHub Pages einrichten (einmalig)

1. Repository auf GitHub erstellen
2. Code pushen
3. In den Repository-Einstellungen unter **Settings → Pages**:
   - **Source:** "GitHub Actions" auswählen
4. Fertig! Die Website wird bei jedem Push automatisch gebaut und veröffentlicht.

### Design anpassen

Die Farben und das Layout werden in `static/css/custom.css` definiert. Die wichtigsten Variablen stehen ganz oben in der Datei:

```css
:root {
  --bwc-blue: #0077b6;       /* Hauptfarbe */
  --bwc-blue-dark: #005f8a;  /* Dunklere Variante */
  --bwc-blue-light: #90e0ef; /* Hellere Variante */
}
```

---

## Lizenz

Dieses Projekt ist für den internen Gebrauch des Bremer Windsurfing Club e.V. bestimmt.
