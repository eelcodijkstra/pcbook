# Aansluiten op een batterij

Soms is het nodig om de Micro:bit los te koppelen van de PC om het te kunnen testen. Je kunt de Micro:bit dan aansluiten op een batterij. Gebruik daarvoor een batterijhouder met 2 AAA-batterijen.

:::{figure} figs/microbit-batterij.jpeg
:width: 300

Batterijhouder voor 2 AAA batterijen

:::


Sluit de batterijhouder aan op de aparte aansluiting hiervoor, deze zit naast de USB-aansluiting. Als de micro:bit is aangesloten op de batterijhouder zie je geen ledjes meer knipperen, waardoor het lijkt alsof de micro:bit niet aanstaat. Zie ook: https://support.microbit.org/support/solutions/articles/19000013982-how-do-i-power-my-micro-bit-.

De micro:bit geeft een spanning van 3V af. Sommige sensoren, zoals de PIR-sensor en de ultrasoonsensor hebben een hogere spanning nodig om goed te functioneren. Daarvoor kun je batterijen gebruiken. Hieronder zie je een batterijhouder voor 3 AAA batterijen, deze geeft een spanning van ongeveer 4,5 V af.

Het lijkt er op dat deze sensoren (de PIR-sensor en ultrasoonsensor) wel werken als de de micro:bit is aangesloten via de USB-kabel.

:::{warning}
Sluit deze batterijhouder met 3 AAA-batterijen nooit rechtstreeks op de micro:bit aan, de micro:bit kan door de hogere spanning kapot gaan. Als je de micro:bit op batterijen wilt aansluiten, gebruiken dan de batterijhouder voor 2 batterijen.
:::

:::{admonition} micro:bit V2 - aan- en uitschakelen
Je kunt de micro:bit versie 2 aan- en uitschakelen als deze verbonden is met een batterij.
Je kunt dan de batterij aangesloten laten, terwijl de microbit uitgezet is (en geen stroom verbruikt).

* uitzetten: houd de reset/power-knop tenminste 5 seconden ingedrukt
    * als de micro:bit op een batterij is aangesloten, schakel je deze zo uit
    * als de micro:bit op een USB-voeding (of host-computer) is aangesloten, zet je deze zo in "low-power slaap"
* aanzetten: kort indrukken
    * de micro:bit start op, en voert het aanwezige programma uit
:::