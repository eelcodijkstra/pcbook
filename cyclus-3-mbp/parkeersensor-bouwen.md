# Parkeersensor bouwen

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

De ultrasoonsensor werkt op een spanning van 5V en de Micro:bit geeft maar 3,3 Volt. Daarom gebruiken we een externe bron. De batterijhouder met 3 batterijen geeft slechts 4,5 volt af, maar dat blijkt toch voldoende te zijn voor de ultrasoonsensor. Je hebt dus nodig:

* Een ultrasoonsensor
* Een batterijhouder voor 3 AAA batterijen

Let op: sluit deze batterijhouder voor 3 batterijen nooit rechtstreeks op de Micro:bit aan, de Micro:bit kan door de hogere spanning kapot gaan. Als je de Micro:bit op batterijen wilt aansluiten, gebruik dan de batterijhouder voor 2 batterijen.

Je kunt het onderstaande schema gebruiken om de ultrasoonsensor aan te sluiten. De trigger van de sensor is aangesloten op pin 1 en de echo is aangesloten op pin 0. Let op de zwarte verbinding aan de linkerkant, vergeet deze niet.

:::{figure} figs/microbit-ultrasoonsensor.png
:width: 600
:align: center

Aansluiten van een ultrasoonsensor op de microbit
:::

## Programmeren van de ultrasoonsensor

:::{admonition} AANPASSEN AAN PYTHON
...aanpassen
:::

Nu de sensor is aangesloten kun je deze gaan testen. Daarvoor moet je eerst een nieuw pakket installeren in de Micro:bit omgeving. Klik op ‘Pakket toevoegen’ en zoek op ‘Sonar’.



Als het goed is zie je dan een blokje Sonar verschijnen.



Je kunt het volgende programma maken om een de geluidssensor te testen. De trigger is aangesloten op pin 1 (P1), de echo op pin 0 (P0) en de afstand op centimeters.



Als je gebruik maakt van de seriele aansluiting om te debuggen kun je het onderstaande programma gebruiken.



Let op: soms geeft de ultrasoonsensor de waarde 0 terug, houd daar rekening mee als je de parkeersensor verder gaat ontwikkelen.

:::{exercise} Werk deelprobleem 1 uit tot een werkend programma

Sluit de ultrasoonsensor aan en maak op basis van de toestandsdiagrammen die je eerder hebt gemaakt een werkend systeem. Werk in kleine stapjes: eerst deelprobleem 1a, dan deelprobleem 1b, etc).
:::
 
## Aansluiten en programmeren van de piezo-buzzer

In de inleiding Micro:bit laten we zien hoe je een piezo-buzzer kunt aansluiten. 

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