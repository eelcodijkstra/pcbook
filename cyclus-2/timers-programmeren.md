# Programmeren van een timer

Zoals gezegd: een timer is een soort kookwekker: je start een timer met een bepaalde tijd. Als de tijd voorbij is, loopt de timer af.

Om een timer te programmeren heb je één variabele nodig:

```
var timerEindtijd
```

Stel, je wilt een timer starten voor 10 seconden. Gebruik dan de volgende regel om de timer te starten of te resetten:

```
timerEindtijd = huidigeTijd + 10
```

Elke microcontroller (Micro:bit, Arduino, Lego Mindstorms) houdt bij hoeveel tijd is verstreken sinds de start van het systeem. In de regel hierboven staat dat aangegeven met huidigeTijd.

Om te zien of de timer afloopt gebruik je:

```
huidigeTijd >= timerEindtijd
```

Je controleert dus of de huidige tijd hoger is dan de eindtijd van de timer.

Een voorbeeld: het onderstaande toestandsdiagram werken we in pseudo-code uit.

:::{figure} figs/diagram-beweging-lamp-timer.png
:width: 700
:align: center

:::

 

Kijk of je de onderstaande pseudocode kunt relateren aan het toestandsdiagram en de informatie over de timer hierboven. Er zijn drie toestandsovergangen (drie pijlen, los van de starttoestand), daarom zie je drie keer: `ALS ... DAN`. We hebben er hier voor gekozen om gebruik te maken van EN in plaats van twee keer een losse `ALS ... DAN`. Vergelijk dit met de aanpak in cyclus 1. We gaan uit van een timer van 10 seconden.

```
EENMALIG BIJ OPSTARTEN:

   toestand wordt 1

 

HERHAAL:

   ALS (toestand is 1 EN beweging gedetecteerd) DAN

      zet lamp aan

      timerEindtijd = huidigeTijd + 10

      toestand wordt 2

   ALS (toestand is 2 EN beweging gedetecteerd) DAN

      timerEindtijd = huidigeTijd + 10

   ALS (toestand is 2 EN huidigeTijd >= timerEindtijd) DAN

      zet lamp uit

      timerEindtijd = huidigeTijd + 10

      toestand wordt 1
```

::::{exercise} Maak pseudocode voor knipperend lampje

Beschrijf de pseudocode voor het toestandsdiagram hieronder. Het gaat om een knipperend lampje. Kies zelf de duur van de timer.

:::{figure} figs/diagram-knipperend-lampje.png
:width: 700
:align: center

:::


* Toestand 1: lamp is uit
* Toestand 2: lamp is aan

::::