# Feierabendseminar: Umgang mit KI in der Wissenschaft

Beamer-Vortrag im vorhandenen LeipzigClean-Design, 16:9.
24 Hauptfolien plus zwei Literaturseiten. Die Motivationsfolie hat fünf
kumulative Einblendungen; deshalb enthält die Präsentations-PDF 30 Seiten.
Die ursprünglichen Punkte und die Formulierungen der goldenen Regel und des
FERC-Frameworks sind erhalten. Lange Abschnitte sind auf mehrere Folien verteilt.

## Kompilieren

```text
latexmk main.tex
```

Die vorhandene `.latexmkrc` wählt XeLaTeX. Die Literatur verwendet Biber:

```text
xelatex -interaction=nonstopmode -halt-on-error main.tex
biber main
xelatex -interaction=nonstopmode -halt-on-error main.tex
xelatex -interaction=nonstopmode -halt-on-error main.tex
```

Benötigt werden Beamer, fontspec, TikZ, tcolorbox, biblatex, csquotes,
babel/ngerman, booktabs und tabularx. Kein Shell-Escape erforderlich.
Arial wird verwendet, sofern installiert; sonst TeX Gyre Heros.
Auf einem anderen Rechner können dadurch Zeilenumbrüche leicht abweichen.

## Inhalt bearbeiten

- `main.tex`: Folien, Quellenverweise und kurze Sprechernotizen.
- `TitlePageInfo.tex`: Titel sowie optionale Angaben zu Name, Institut und Termin.
- `references.bib`: vorhandene Literatur plus ergänzte Fachquellen.
- `tao_forschungsprozess.tikz`: editierbares Schaubild nach Tao (2026).
- `beamerthemeLeipzigClean.sty`: unverändertes Design und Farben.
- `images/`: vollständige Screenshots, Workflow-Grafik, Klimagrafiken,
  Originalabbildungen aus Tao (2026) und Leipzig-Logo.
- `notes.tex`: optionaler Einstieg für Folien mit eingeblendeten Sprechernotizen.

Die Reihenfolge der Motivationsbilder lautet `10_advances`, `astra`,
`navier_stokes`, `hugging_face`, `727_papers`. Die Angaben `<1->` bis `<5->`
lassen jedes neue Bild dauerhaft über den vorherigen erscheinen. Position,
Breite beziehungsweise Höhe stehen direkt beim jeweiligen TikZ-Knoten. Die
Bilder werden vollständig und proportional skaliert, ohne `trim` oder `clip`.
Spätere Einblendungen überlagern frühere Bilder.
Die Bilder verlinken auf die jeweiligen Originalmitteilungen.

Das Anwendungsbeispiel verwendet `\redrow{linker Text}{rechte Erklärung}`.
Beide Spalten sind oben bündig; die linke Beschriftung erscheint rot. Das
Tao-Diagramm benötigt die TikZ-Bibliothek `arrows.meta` und die Farben des
Leipzig-Themes. Es ist eine ausdrücklich gekennzeichnete Übertragung auf
allgemeine Wissenschaft, kein unverändertes Diagramm aus dem Paper.
`images/math_knowledge.pdf` und `images/problem_solving.pdf` enthalten dagegen
die Originalabbildungen 2 und 4 aus dem bereitgestellten Paper
arXiv:2608.16753v1 (PDF-Seiten 5 und 9).

Für eine kürzere Fassung können die zweite Leiden-Folie und eine der
Ressourcenfolien in den Anhang verschoben werden.

Das Design basiert auf dem Leipzig Beamer Template von Badal Mondal:
https://de.overleaf.com/latex/templates/leipzig-beamer-template/vxzvtsfytgcj
