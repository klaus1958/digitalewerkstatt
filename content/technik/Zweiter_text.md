---
title: "zweiter Text"
weight: 10
tags: ['learn']
categories: ['Hugo', 'Javascript lernen'] 
---
- Das gilt es zu beachten
    - die Versionsverwaltung findet mit github statt
    - die Dateien liegen aber in der Nexcloud\Klaus\Hugoprojekt\digitalewerkstatt
    und werden damit synchronisiert.
    - evtl. in Github den Pfad ändern oder syncen nur mit Github ohne nextcloud

- Projekt ist jetzt nur noch bei git ( kein nextcloud) Zusätzlich ,gitignore angelegt damit public und resources nicht synchronisiert werden
- tatsächlich werden als trenner / und nicht \ verwendet !!!!!



# veröffentlichen
und wie kann ich jetzt ein e hugo seit in githubpages anzeigen (browsen)
Um deine Hugo-Seite direkt über GitHub Pages im Browser anzuzeigen, nutzt du am besten eine GitHub Actions Pipeline. Das ist der modernste und sauberste Weg, weil GitHub deine Seite dann bei jedem git push vollautomatisch im Hintergrund baut und veröffentlicht.
Hier ist die Schritt-für-Schritt-Anleitung, um das einzurichten:
## 1. GitHub Actions Datei erstellen
Du musst GitHub mitteilen, wie es deine Hugo-Seite bauen soll. Dafür legen wir eine Konfigurationsdatei an:

   1. Erstelle in deinem Hugo-Projekt (in den Windows-Dokumenten) einen neuen Ordner namens .github (mit Punkt am Anfang).
   2. Erstelle darin einen Unterordner namens workflows.
   3. Erstelle in diesem Ordner eine Datei namens hugo.yaml.
   4. Kopiere den folgenden offiziellen Deployment-Code Hugo GitHub Pages Deployment Workflow in diese Datei und speichere sie:

name: Deploy Hugo site to Pages
on:
  push:
    branches:
      - main  # Falls dein Hauptzweig 'master' heißt, hier 'master' eintragen
permissions:
  contents: read
  pages: write
  id-token: write
concurrency:
  group: "pages"
  cancel-in-progress: false
defaults:
  run:
    shell: bash
jobs:
  build:
    runs-on: ubuntu-latest
    env:
      HUGO_VERSION: 0.140.0 # Hier bei Bedarf deine Hugo-Version eintragen
    steps:
      - name: Checkout
        uses: actions/checkout@v4
        with:
          submodules: recursive
          fetch-depth: 0
      - name: Setup Pages
        id: pages
        uses: actions/configure-pages@v5
      - name: Install Hugo
        run: |
          wget -O ${{ runner.temp }}/hugo.deb https://github.com{HUGO_VERSION}/hugo_extended_${HUGO_VERSION}_linux-amd64.deb
          sudo dpkg -i ${{ runner.temp }}/hugo.deb      - name: Build with Hugo
        env:
          HUGO_CACHEDIR: ${{ runner.temp }}/hugo_cache
          HUGO_ENV: production
        run: |
          hugo \
            --gc \
            --minify \
            --baseURL "${{ steps.pages.outputs.base_url }}/"      - name: Upload artifact
        uses: actions/upload-pages-artifact@v3
        with:
          path: ./public

  deploy:
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    runs-on: ubuntu-latest
    needs: build
    steps:
      - name: Deploy to GitHub Pages
        id: deployment
        uses: actions/deploy-pages@v4

## 2. Änderungen hochladen
Pushe diese neue Datei über VS Code oder GitHub Desktop zu GitHub (z. B. mit der Commit-Nachricht: GitHub Actions für Pages hinzugefügt).
## 3. GitHub Pages im Repository aktivieren
Jetzt musst du GitHub noch sagen, dass es diese Pipeline auch für die Anzeige nutzen soll:

   1. Öffne dein Repository im Browser auf GitHub.
   2. Klicke oben auf den Reiter ⚙️ Settings (Einstellungen).
   3. Klicke in der linken Menüleiste auf Pages.
   4. Wähle unter Build and deployment bei Source die Option GitHub Actions aus (anstatt Deploy from a branch). [1, 2] 

## 4. Das Ergebnis prüfen
Sobald du das umgestellt hast, startet GitHub den Bauprozess.

* Du kannst den Fortschritt auf GitHub im Reiter Actions live mitverfolgen.
* Sobald dort ein grünes Häkchen erscheint, findest du direkt auf der Settings -> Pages-Seite ganz oben den Link zu deiner fertigen Website (die URL sieht meistens so aus: https://github.io).

Wenn du den Link anklickst, öffnet sich deine Hugo-Seite live im Browser!
Möchtest du danach direkt sehen, wie du das Projekt jetzt fehlerfrei auf deinen Firmenrechner klonst?

[1] [https://developer.mozilla.org](https://developer.mozilla.org/de/docs/Learn_web_development/Howto/Tools_and_setup/Using_GitHub_pages)
[2] [https://docs.github.com](https://docs.github.com/de/desktop/working-with-your-remote-repository-on-github-or-github-enterprise/viewing-a-pull-request-in-github-desktop)



# Das möchte ich lernen

- Javascript-Kurs Brad Traversy
