# Voorbeeld: een knipperend lampje

We geven je een voorbeeld van een knipperend lampje om te laten zien hoe je een timer kunt programmeren in de micro:bit. 
We gebruiken het onderstaande toestandsdiagram.

:::{figure} figs/diagram-knipperend-lampje.png
:width: 500

Toestandsdiagram voor een knipperend lampje

:::

* Toestand 1: lamp is uit
* Toestand 2: lamp is aan
 

Hieronder vind je een deel van de uitwerking. We gaan daarbij uit van een timer van 1000 milliseconden = 1 seconden. Kijk eventueel nogmaals bij de uitleg over het programmeren van timers als je het programma niet helemaal begrijpt.

```Python
import time
from microbit import *

toestand = 1
timerEindtijd = time.ticks_add(time.ticks_ms(), 1000)
display.clear()

while True:
    if time.ticks_diff(timerEindtijd, time.ticks_ms()) <= 0:
        if toestand == 1:
            display.show(Image.HEART)
            toestand = 2
        elif toestand == 2:
            display.clear()
            toestand = 1
        timerEindtijd = time.ticks_add(time.ticks_ms(), 1000)    

```


:::{exercise} Alternatieve timer-reset

1. Print de waarde van `timerEindtijd` aan het begin van het then-block van de timer-test.
Wat valt je op?

2. Verander de code voor de timer-reset in:

```Python
timerEindtijd = time.ticks_add(timerEindtijd, 1000)
```

Wat zie je nu bij de opeenvolgende waarden van de `timerEindtijd`?
:::

:::{exercise} Verander de aan/uit verhouding

1. In het bovenstaande programma is het display even lang aan als uit.
Pas het programma aan zodat de aan-tijd kan verschillen van de uit-tijd.
(Dat komt ook beter overeen met het toestandsdiagram.)

2. Wat gebeurt er als de aan-tijd 10 ms is, en de uit-tijd 90 ms?
Teken in een tijdgrafiek wat er gebeurt.
(Horizontaal de tijd, verticaal lamp aan/uit.)
:::


