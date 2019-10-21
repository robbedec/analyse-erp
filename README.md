# HOGENT sjabloon rapport/verslag

Deze repository bevat een LaTeX stijlsjabloon voor de opmaak van een verslag, rapport of ander lang document dat de HOGENT huisstijl, zoals ingevoerd in 2019, volgt.

## Titelpagina

Er zijn twee varianten voor de voorpagina voorzien, elk in de vorm van een LaTeX package:

- `hogent-titlepage-plain` -- Een eenvoudige titelpagina met instelbare kleuren en het HOGENT-logo rechtsonder
- `hogent-titlepage-image` -- Een titelpagina met een afbeelding als achtergrond

Compileer en bekijk de voorbeelddocumenten om een idee te krijgen van het resultaat.

Eenvoudige voorpagina:

```latex
\documentclass{hogent-report}

\usepackage{hogent-titlepage-plain}

\title{Stageverslag Acme Inc.}
\author{Pieter Pieters}
\date{30 mei 2019}

\begin{document}
    \inserttitlepage[hgblue]

    % ...
\end{document}
```

Voorpagina met afbeelding:

```latex
\documentclass{hogent-report}

\usepackage{hogent-titlepage-image}

\title{Stageverslag Acme Inc.}
\author{Pieter Pieters}
\date{30 mei 2019}

\begin{document}
    \inserttitlepage[white]{img/background.png}

    % ...
\end{document}
```

## Afbeeldingen hoofdstuktitels

Bij de hoofdstuktitels is het mogelijk om een afbeelding op de achtergrond toe te voegen.

```latex
\begin{document}
    % ...
    \usechapterimagetrue
    \chapterimage{img/chapter-background.png}

    \chapter{Inleiding}
    % ...
```

Na het commando `\chapterimage`, krijgen alle hoofdstuktitels de opgegeven afbeelding als achtergrond. Als je voor elk hoofdstuk een andere afbeelding wilt, herhaal `\chapterimage{}` vóór elke `\chapter{}`.

Om het gebruik van afbeeldingen in hoofdstuktitels uit te schakelen, gebruik `\usechapterimagefalse`.

## Broncode invoegen

Het sjabloon definieert een commando `\codefragment` met 3 verplichte argumenten:

1. De programmeertaal
2. Pad naar het broncodebestand
3. Bijschrift met uitleg over de code

Voorbeeld:

```latex
\codefragment{java}{src/HelloWorld.java}{Een eenvoudig Java-programma.}
```

## HOGENT huisstijlkleuren

Het sjabloon definieert de kleuren van het [kleurenpalet van de HOGENT huisstijl](https://hnet.hogent.be/themas/communicatie/huisstijl-logo-s-en-sjablonen/kleurgebruik/). Omdat de gelinkte pagina enkel voor HOGENT-personeel toegankelijk is, volgt hier een overzicht van de kleuren:

| Kleur        | R    | G    | B    |
| :---         | ---: | ---: | ---: |
| hgdarkgreen  | 22   | 176  | 165  |
| hgpink       | 241  | 157  | 160  |
| hgochre      | 250  | 188  | 50   |
| hgorange     | 239  | 135  | 103  |
| hgpurple     | 187  | 144  | 189  |
| hgblue       | 76   | 162  | 213  |
| hglightgreen | 165  | 202  | 114  |
| hgbrown      | 216  | 176  | 131  |
| hggrey       | 195  | 187  | 175  |
| hgyellow     | 244  | 222  | 0    |

## Omgevingen voor voorbeelden, stellingen, ...

Er zijn vier *theorem*-omgevingen gedefinieerd:

- `theorem` (Stelling + bewijs)
- `corollary` (Gevolg + bewijs)
- `definition` (Definitie van een begrip)
- `exercise` (Opgave van een oefening)
- `example` (Voorbeeld)

Elk heeft een specifieke stijl, hetzij met een kader, dikke rand links of gekleurde achtergrond. Voorbeeld gebruik:

```latex
\begin{theorem}[titel]
  hoofdtekst
\end{theorem}
```

## Bibliografie

Het sjabloon voorziet het invoegen van een bibliografie, opgemaakt volgens de APA-stijl. Voeg geraadpleegde werken toe aan een bestand `referenties.bib`, in biber/biblatex-formaat.

## Bijdragen, fouten, verbeteringen

Bugs, vragen voor verbeteringen, enz. zijn welkom! Je kan die registreren via de Issues. Je kan zelf ook verbeteringen aanbrengen via Pull Requests.

- De vormgeving van dit stijlsjabloon is gebaseerd op het "[Legrand Orange Book](http://www.latextemplates.com/template/the-legrand-orange-book)" sjabloon door Mathias Legrand, met aanpassingen specifiek voor HOGENT.

Volgende personen hebben bijgedragen aan deze sjablonen:

- Bert Van Vreckem (maintainer)
- Jens Buysse
- Chantal Teerlinck
- Jeroen Maelbrancke
- Matts Devriendt
- Niels Corneille
- Patrick Van Brussel
- Simon Rondelez
