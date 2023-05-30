# Voorbeeld: aansluiten motor

## Inleiding

In deze paragraaf leer je hoe je een motor kunt aansluiten op de Mico:bit. Dit is gebaseerd op: https://www.kitronik.co.uk/blog/experiment-4-using-a-transistor-to-drive-a-motor/.

Het gaat om een eenvoudige electrische DC-motor. Het is geen servo-motor, maar het is wel goed om het verschil tussen deze twee type motoren te weten. Dat wordt in het onderstaande filmpje uitgelegd.

<iframe width="560" height="315" src="https://www.youtube.com/embed/okxooamdAP4" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

Het doel is om met de A-knop en B-knop een motor aan te sturen. De motorbesturing werkt direct met de toestand van de knoppen: alleen als je één of meer knoppen ingedrukt hebt (en houdt) draait de motor.

* Als geen van de knoppen **is** ingedrukt staat de motor uit.
* Als de A-knop is ingedrukt (en B niet) draait de motor op 25%.
* Als de B-knop is ingedrukt (en A niet) draait de motor op 50%
* Als de A- en B-knop beide zijn ingedrukt draait de motor op 100%.

Je leert hierbij dat je een motor niet zomaar op een pin kunt aansluiten, omdat de pinnen van de micro:bit onvoldoende stroom kunnen leveren voor een motor.

Zorg dat je stapsgewijs werkt:

* Stap 1: sluit de motor aan en test of deze werkt.
* Stap 2: maak de functietabel
* Stap 3: maak het programma en test dit

## Stap 1: Sluit de motor aan

Sluit de motor aan volgens het schema hieronder. Je hebt daarvoor de volgende onderdelen nodig, die vind je allemaal in de uitvinderskit.

* Een terminal connector. Hiermee kun je de motor makkelijk en veilig aan het breadboard verbinden.
* Een motor, zoals bijvoorbeeld een windmolentje
* Een weerstand van 2.2kΩ. Deze heeft de kleuren rood, rood, rood, goud.
* Een transistor

:::{figure} figs/breadboard-motor.png
:width: 600

Breadboard met transistor en motor

:::

De transistor heeft drie pootjes. Het middelste pootje werkt als een soort schakelaar. Als de spanning op het middelste pootje hoog is (3 volt), dan is de poort open en kan er stroom via de buitenste pootjes lopen. Als de spanning op het middelste bootje laag is (0 volt), dan is de poort dicht en kan er geen stroom lopen. De transistor zorgt ervoor dat de stroom voor de motor niet via één van de pinnen van de micro:bit hoeft te gaan, maar rechtstreeks op de 3V en GND kan worden aangesloten. Daardoor krijgt de motor voldoende stroom om te kunnen draaien (en brandt de pin van de micro:bit niet door). We kunnen de motor nu aan- en uitzetten via pin 0.

Test of de motor werkt, bijvoorbeeld met het onderstaande programma. Als het goed is begint de motor op ongeveer 50% te draaien. Je kunt de waarde 512 veranderen in het programma (tussen 0 en 1023) en daarmee bepalen hoe snel de motor moet draaien. Ook hier wordt weer gebruik gemaakt van Pulse Width Modulation, zie Over PWM: Pulse With Modulation.

```Python
from microbit import *

while True:
    pin0.write_digital(512)
```    
    
:::{admonition} microbit V2 of V1 - welke stromen?
De micro:bit V2 kan via de 3V aansluiting ongeveer 190 mA leveren (van de 300mA voeding wordt ca. 110 mA door het bordje zelf gebruikt). De microbit V1 levert via deze aansluiting max. 90 mA.

zie ook: [verschillen microbit V1 en v2](https://www.sossolutions.nl/blog/het-verschil-tussen-de-bbc-micro-bit-v1-en-bbc-micro-bit-v2/)
:::
    
## Stap 2: functietabel

De besturing van de motor met de knoppen werkt *direct* (ofwel: *functioneel*): er is geen sprake van toestanden.
Alleen zolang de knoppen ingedrukt zijn, draait de motor. (Anders gezegd: je gebruik het *signaal* van de knoppen voor de aansturing van de motor.) Voor deze besturingsfunctie maken we de volgende tabel:
    
| knop(pen)  | motor |
| :---       | :---  |
| (geen)     | 0     |
| A (niet B) | 25%   |
| B (niet A) | 50%   |
| A+B        | 100%  |

## Stap 3: het programma

We gebruiken het *signaal* van de knoppen, dus de functie `button.is_pressed()`, in plaats van de *event*-functie `button.was_pressed()`.

```Python
from microbit import *

while True:
    if not button_a.is_pressed and not button_b.is_pressed():
        pin0.write_analog(0)
    elif button_a.is_pressed and not button_b.is_pressed():
        pin0.write_analog(256)
    elif not button_a.is_pressed() and button_b.is_pressed():
        pin0.write_analog(512)
    elif button_a.is_pressed() and button_b.is_pressed():
        pin0.write_analog(1023)
```

Test je schakeling en programma. *Werkt dit?*

**Opmerking.** We kiezen er hier voor om de tabel zo direct mogelijk te vertalen in het programma, zonder "optimalisaties". Dit betekent dat we de functies vaker aanroepen dan strikt nodig: als je geneste if-statements gebruikt kun je met minder aanroepen volstaan. Probeer zelf een dergelijke variant van het programma te maken.

:::{admonition} Testen van je *sketch*
Met een *sketch* bedoelen we (in Arduino-termen) de combinatie van hardware en software. Als het niet werkt, kan het probleem op drie plekken zitten:

* in de hardware-schakeling
* in de software
* in de aansluiting tussen de hardware en de software

Een voorbeeld van dit laatste is als je in de software pin 1 aanstuurt en in de hardware pin 0 aangesloten hebt.

Je kunt deze onderdelen proberen afzonderlijk testen:

* je kunt controleren of de motorschakeling werkt, door het kabeltje voor de aansturing van de transistor tijdelijk op 3V aan te sluiten, in plaats van op pin 0.
* je kunt controleren of de software werkt, met de juiste pinnen, door een LED met serieweerstand aan te sluiten op pin 0.
:::

