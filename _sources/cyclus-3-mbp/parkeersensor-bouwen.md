# Parkeersensor bouwen (MB)

Nu wordt het tijd om de ultrasoonsensor aan te sluiten op de Micro:bit en de parkeersensor te bouwen. In dit hoofdstuk geven we aanwijzingen voor het aansluiten van de ultrasoonsensor.

Zorg dat je steeds stapsgewijs werkt. Deel het probleem op in kleinere problemen zoals staat beschreven in het algemene deel van cyclus 3.

Voor deelprobleem 1 (ultrasoonsensor gebruiken) kan je het als volgt opdelen in kleine stapjes:

1. Sluit de ultrasoonsensor aan en test of deze werkt.
2. Maak een toestandsdiagram voor deelprobleem 1a.
3. Maak het bijbehorende programma.
4. Test het programma. Verbeter het programma eventueel.
5. Maak het toestandsdiagram voor deelprobleem 1b.
6. Etc etc.

Voor deelprobleem 2 (piezobuzzer gebruiken) kan je het als volgt opdelen in kleine stapjes.

1. Sluit de piezobuzzer aan en test of deze werkt.
2. Maak een toestandsdiagram voor deelprobleem 2a.
3. Maak het bijbehorende programma.
4. Test het programma. Verbeter het programma eventueel.
5. Maak het toestandsdiagram voor deelprobleem 2b.
6. Etc etc.

Je kunt in plaats van de piezobuzzer ook een headset gebruiken (zie de afbeelding hieronder).

:::{admonition} microbit versie 2: ingebouwde luidspreker

De microbit versie 2 heeft een ingebouwde luidspreker. Je hoeft dan geen externe buzzer o.i.d. te gebruiken.

:::

## Achterhalen werking ultrasoonsensor

:::{exercise} Hoe werkt de ultrasoonsensor?
In de datasheet van de ultrasoonsensor vind je informatie over hoe de sensor werkt en hoe je deze kunt aansluiten. Je hebt eerder al uitgezocht wat het bereik en de nauwkeurigheid zijn van de ultrassoonsensor. Maar dat zegt nog niets over hoe je de sensor kunt aansluiten. Zoek de volgende aanvullende informatie op in de datasheets.

* Spanning waarop de ultrasone afstandssensor werkt
* De stroomsterkte die de ultrasone afstandssensor zal afnemen
* De betekenis van de pinnen op de sensor.
* Hoe werkt wordt de sensor? Met andere woorden, hoe bepaalt de sensor de afstand tot een object? Wat betekenen de aanduidingen Rx en Tx op de sensor?

:::

## Aansluiten van de ultrasoonsensor

De ultrasoonsensor werkt op een spanning van 5V en de micro:bit geeft maar 3,3 Volt. Daarom gebruiken we een externe bron. De batterijhouder met 3 batterijen geeft slechts 4,5 volt af, maar dat blijkt toch voldoende te zijn voor de ultrasoonsensor. Je hebt dus nodig:

* Een ultrasoonsensor
* Een batterijhouder voor 3 AAA batterijen

:::{warning}

Let op: sluit deze batterijhouder voor 3 batterijen nooit rechtstreeks op de micro:bit aan, de micro:bit kan door de hogere spanning kapot gaan. Als je de micro:bit op batterijen wilt aansluiten, gebruik dan de batterijhouder voor 2 batterijen.

:::

Je kunt het onderstaande schema gebruiken om de ultrasoonsensor aan te sluiten. De trigger van de sensor is aangesloten op pin 1 en de echo is aangesloten op pin 0. **Let op de zwarte (GND) verbinding aan de linkerkant, vergeet deze niet.**

:::{figure} figs/microbit-ultrasoonsensor.png
:width: 600
:align: center

Aansluiten van een ultrasoonsensor op de microbit
:::

## Programmeren van de ultrasoonsensor

De werking van de ultrasoonsensor zie je in de onderstaande grafiek. Bij een 10 ms puls op de "trigger" input stuurt de sensor een ultrasone geluidspuls. Daarna start de puls op de "echo" output; deze duurt totdat de echo van de geluidspuls ontvangen is. De duur van deze echo-puls is dan een maat voor de afstand. (N.B. het geluid legt de gezochte afstand tweemaal af: heen en terug.)

:::{figure} figs/ultrasone-afstandssensor-timing.png
:width: 500

Tijdsdiagram ultrasone afstandssensor

:::


Met de volgende microbit-functie bepaal je de lengte van een puls op een input-pin in ms (zie: https://microbit-micropython.readthedocs.io/en/v2-docs/machine.html).

```Python
machine.time_pulse_us(pin, pulse_level, timeout_us=1000000)
```

(Een resultaat < 0 geeft aan dat er een *timeout* opgetreden is.)

Het volgende programma laat zien hoe je de functie voor het meten van een puls gebruikt voor het meten van een afstand met de ultrasoonsensor. Dit programma kun je ook gebruiken voor het testen van de ultrasoonsensor-schakeling.


```Python
from microbit import *
import machine
import utime

trigger_pin = pin1
echo_pin = pin0
trigger_pin.write_digital(0)

while True:
    trigger_pin.write_digital(1) # 10 ms trigger puls
    utime.sleep_us(10)
    trigger_pin.write_digital(0)
    
    duration = machine.time_pulse_us(echo_pin, 1, 25000)  # time-out 25 ms
    if duration > 0:
        distance = duration * 343 // 2000        # in mm
        print("afstand (mm): " + str(distance))
    else:
        print("te ver")
    sleep(1000)    
```

Let op: soms krijg je als duur van de puls een waarde <= 0 terug, houd daar rekening mee als je de parkeersensor verder gaat ontwikkelen.

:::{exercise} Werk deelprobleem 1 uit tot een werkend programma

Sluit de ultrasoonsensor aan en maak op basis van de toestandsdiagrammen die je eerder hebt gemaakt een werkend systeem. Werk in kleine stapjes: eerst deelprobleem 1a, dan deelprobleem 1b, etc).
:::
 
## Aansluiten en programmeren van de piezo-buzzer

In de inleiding micro:bit laten we zien hoe je een piezo-buzzer kunt aansluiten. 

:::{exercise} Werk deelprobleem 2 uit tot een werkend programma

Sluit de piezo-buzzer aan en maak op basis van de toestandsdiagrammen die je eerder hebt gemaakt een werkend systeem. Werk in kleine stapjes: eerst deelprobleem 2a, dan deelprobleem 2b, etc).

:::

## Samenvoegen ultrasoonsensor en piezobuzzer

:::{exercise} Voeg beide systemen samen

Je hebt al gezien hoe je de twee toestandsdiagrammen kunt samenvoegen, zie https://maken.wikiwijs.nl/135427/Cyclus_3#!page-4912161.

Maak op basis van het nieuwe, samengevoegde toestandsdiagram een nieuw programma. Als je de ultrasoonsensor en/of piezo buzzer apart gaat aansluiten, test deze dan altijd voordat je verder gaat.

:::

Hieronder vind je een voorbeeld van een schema waarbij zowel de ultrasoonsensor als de piezobuzzer zijn aangesloten.

:::{figure} figs/buzzer-ultrasoon.png
:width: 600
:align: center

:::