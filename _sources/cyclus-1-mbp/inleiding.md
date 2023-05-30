# Inleiding

Het doel is nu om een hotelschakeling te bouwen met de micro:bit. Een hotelschakeling bestaat uit twee schakelaars en een lamp. Op de Micro:bit zitten twee drukknoppen, die gaan we gebruiken in plaats van de schakelaars die thuis aan de muur zitten. Dat maakt het makkelijker om een protoype te maken.

We gaan het stapsgewijs opbouwen. Eerst maak je een systeem met één drukknop. Met die drukknop moet je de lamp aan en uit kunnen zetten. In plaats van een lamp gebruiken we de ledjes van de micro:bit.

De enige gebeurtenis is dus:

* de drukknop wordt ingedrukt (en ook weer losgelaten)

De acties zijn:

* zet lamp aan
* zet lamp uit

Hieronder vind je het toestandsdiagram.

:::{figure} figs/toestandsdiagram-hotel-0.png
:width: 400
:align: center

Toestandsdiagram hotelschakeling

:::

## Omzetten naar micro:bit programma

De functie `button_a.was_pressed()` geeft aan of knop A ingedrukt geweest is sinds de vorige aanroep.
Hiermee detecteer je de gebeurtenis (event) van het indrukken en loslaten van de knop.
Deze functie gebruik je op de volgende manier in je programma:

```Python
from microbit import *

while True:
    if button_a.was_pressed():
        # ... handle button event: action
```

Met behulp van dit voorbeeld kun je het programma maken dat hoort bij het toestandsdiagram.

Alle toestanden krijgen een nummer:

* 0 - Lamp is uit
* 1 - Lamp is aan

Hieronder vind je het begin van dat programma. Hopelijk kun je de relatie met het toestandsdiagram herkennen. Je ziet:

```Python
from microbit import *

led_state = 0
leds_on = Image("99999:"
                "99999:"
                "99999:"
                "99999:"
                "99999")
leds_off = Image("00000:"
                 "00000:"
                 "00000:"
                 "00000:"
                 "00000")

while True:
    if button_a.was_pressed():
        if led_state == 0:
            led_state = 1
            display.show(leds_on)
        else:
            # maak deze code zelf
```

Het programma bevat één variabele: `led_state`. Die krijgt aan het begin, bij opstarten, de waarde 0. Dat is immers de begintoestand.

Voor elke toestandsovergang is er een tak in de `if` van de "button event handler".
In de bijbehorende actie wordt de toestand aangepast en wordt de actie van de overgang uitgevoerd.

**Opdracht: maak het programma af**

Maak nu het programma af op basis van het toestandsdiagram. Test het programma. Bij het testen ga je in ieder geval voor iedere toestand alle mogelijke toestandsovergangen na. Dat is in dit geval heel makkelijk, later wordt het al iets moeilijker.
 

:::{exercise} Opdracht: bouw een hotelschakeling

Bouw nu de hotelschakeling. Je hebt twee drukknopjes (A en B). Je hebt dus de volgende gebeurtenissen:

* knopje A wordt ingedrukt (en losgelaten)
* knopje B wordt ingedrukt (en losgelaten)

De mogelijke acties zijn:

* zet lamp aan (zet de ledjes van de micro:bit aan)
* zet lamp uit (zet de ledjes van de micro:bit uit)

Maak eerst een toestandsdiagram en maak dan het programma in de micro:bit.

:::

**Opmerking** Als je een dergelijke schakeling (zoals geprogrammeerd in dit voorbeeld) gebruikt in een trappenhuis, dan loop je de kans dat je op de knop drukt om de lamp aan te doen, waarna deze direct weer uit gaat. Je probeert het nog een keer, en het gebeurt weer net zo. Wat is hier aan de hand?

* bij de andere knop staat iemand die de lamp ook aan wil zetten: deze drukt de knop in vlak nadat jij deze ingedrukt hebt. Deze tweede actie schakelt de lamp weer uit
* jullie proberen het beide nog een keer, met precies hetzelfde resultaat...

Alleen als één van beiden wat langer wacht, en ziet dat het licht al brandt, kom je uit deze herhaling...

Een vergelijkbaar scenario kun je krijgen als er een vertraging zit tussen het indrukken van de knop, en het moment dat de lamp aangaat. Als de lamp niet direct aangaat, drukt de gebruiker nog een keer op de knop, en schakelt daarmee (onbewust) de lamp uit.

Je kunt deze scenario's voorkomen door aan elke kant *twee knoppen* te gebruiken, één voor het aanzetten van de lamp, en één voor het uitzetten daarvan. 

:::{exercise} Bouw een hotelschakeling met dubbele knoppen

Er zijn twee gebeurtenissen (events):

* knop A wordt ingedrukt
* knop B wordt ingedrukt

met de acties:

* zet lamp aan
* zet lamp uit

Merk op dat je in dit geval geen toestand nodig hebt! Je kunt werken met een toestandsonafhankelijke oplossing.
Je kunt de besturing beschrijven in een simpele tabel:

| input-event | actie |
| :---        | :---  |
| knop A      |       |
| knop B      |       |

Maak eerst deze tabel af, en maak dan het bijbehorende programma.
