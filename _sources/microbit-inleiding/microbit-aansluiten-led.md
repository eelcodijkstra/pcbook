# Voorbeeld: aansluiten LED en drukknop

## Inleiding

In deze paragraaf laten we zien hoe je een externe led en externe drukknop kunt koppelen aan de Micro:bit. We volgen deze stappen:

1. Aansluiten van de drukknop en vervolgens testen daarvan
2. Aansluiten van de LED en vervolgens testen daarvan
3. Een programma maken waarmee je de LED aan en uit kunt zetten met de drukknop.

Bekijk eerst de onderstaande filmpjes over de drukknop en de LED.

<iframe width="560" height="315" src="https://www.youtube.com/embed/t_Qujjd_38o" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

Behind the MakeCode Hardware - Buttons

<iframe width="560" height="315" src="https://www.youtube.com/embed/qqBmvHD5bCw" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

Behind the MakeCode Hardware - LEDs

## Stap 1

Stap 1: Aansluiten van de drukknop

Maak de volgende opstelling.

:::{figure} figs/breadboard-drukknop.png
:width: 600

Breadboard met drukknop

:::

De bovenste rij op het breadboard in het plaatje hierboven is dus de min (0V), de rij daaronder is de plus (3V). Het knopje is dus verbonden met pin P0 en de min (0V).

Het drukknopje heeft vier pinnen, die twee aan twee zijn verbonden. Als je het knopje indrukt worden alle vier pinnen met elkaar verbonden. Zie: http://www.teachwithict.com/uploads/5/5/8/2/5582303/published/button-fig-1.png?1531054399.

Je kunt nu op pin P0 meten of het knopje wordt ingedrukt. Belangrijk is om eerst te testen of dit werkt. Dat kan bijvoorbeeld met het volgende programma. Probeer het uit en kijk of het knopje werkt. Als je het knopje indrukt moet er een hartje verschijnen op de Micro:bit.

```Python
from microbit import *

pin0.set_pull(pin.PULL_UP)

while True:
    if pin0.read_digital() == 0:  # button pressed
        display.show(Image.HEART)
    else:
        display.show(Image.SQUARE_SMALL)
        
```

Merk op dat als je het drukknopje *indrukt*, deze pin P0 verbindt met 0V (GND).
In dat geval geeft `pin0.read_digital()` de waarde 0.
Als je het knopje loslaat, is Pin 0 door de *pull-up* weerstand verbonden met 3V.
`pin0.read_digital()` geeft dan de waarde 1.


Enkele opmerkingen voor de experts:

De pinnen P0, P1, P2, maar ook P5 en P11 hebben een ingebouwde weerstand, die hoeft er dus niet bij worden geplaatst.
De micro:bit heeft een ingebouwde pull-up, zie ook: https://makecode.microbit.org/reference/pins/set-pull.

## Stap 2

Nu je weet dat het drukknopje werkt kun je het ledje gaan aansluiten. Daarbij zijn twee dingen belangrijk:

1. Een led kan doorbranden als er teveel spanning op staat. Daarom moet je altijd een weerstand gebruiken. Voor de ledjes die bij de uitvinderskit zitten kun je een ledje gebruiken van 47 Ohm. Dit zijn de weerstanden met de kleuren: geel, paars, zwart, goud. Als je meer wilt weten over deze kleurcodering, zie bijvoorbeeld: https://www.weerstandcalculator.nl/
2. Een led is een diode. Dat betekent dat de stroom er maar van één kant door kan. Zorg dat je de platte zijde verbindt met de – (min, 0V) en de bolle zijde met de + (plus, 3V). Doe je het andersom, dan zal de led niet branden. Je kunt het ook zien aan de lengte van de twee pootjes van de led, het lange pootje is de +, het korte pootje de min.

Breid het systeem uit met een led zoals in het onderstaande schema. Je ziet, de led is aangesloten op pin P1. Die fungeert als een soort schakelaar waarmee je de led aan en uit kunt zetten.

:::{figure} figs/breadboard-drukknop-led.png
:width: 600

Breadboard met drukknop en led

:::

Nu moet je eerst de led testen. Je kunt de led bijvoorbeeld steeds aan en uit zetten, met het onderstaande programma.

Let op: we gebruiken hier `sleep()` puur voor het testen van de afzonderlijke LED. In de module leer je om een *timer* te gebruiken in plaats van `sleep()`, zie cyclus 2.

```Python
from microbit import *

while True:
    pin1.write_digital(1)
    sleep(500)
    pin1.write_digital(0)
    sleep(500)
```

## Stap 3

Stap 3: Bedien de LED met de drukknop

De volgende stap is om de twee onderdelen (drukknop en led) te combineren: als het knopje wordt ingedrukt (en weer wordt losgelaten) gaat de led aan. Wordt het knopje nogmaals ingedrukt, dan gaat de led weer uit. In deze module werken we altijd met een toestandsdiagram, dus ook nu. Je kunt bijvoorbeeld het volgende toestandsdiagram gebruiken.

:::{figure} figs/drukknop-led-automaat.png
:width: 500

Toestandsdiagram van lamp-besturing

:::

* Toestand 1: de lamp is uit
* Toestand 2: de lamp is aan

Het programma ziet er dan als volgt uit


```Python
from microbit import *

prev_buttonvalue = 1
led_state = 1  # led off

while True:
    button_value = pin0.read_digital()
    if button_value == 0 and prev_buttonvalue == 1:
        if led_state == 1:
            led_state = 2
            pin1.digital_write(1)
        else:
            led_state = 1
            pin1.digital_write(0)
    prev_buttonvalue = button_value         
```

*Werkt het?*

:::{admonition} Button-event en actie
De functie `pin0.read_digital()` geeft, zoals eerder beschreven, in dit geval `0` als de drukknop ingedrukt is, en anders `1`. Dit is het *signaal* van de drukknop, dat op elk moment de waarde aangeeft.

Voor het toestandsdiagram werken we niet met signalen, maar met *events* (momentane gebeurtenissen), bijvoorbeeld de event van het indrukken van de drukknop. In het drukknop-signaal zie je dat als de overgang van 1 naar 0.
Om deze overgang te detecteren vergelijken we de vorige waarde en de huidige waarde van het signaal. Als dit overeenkomt met 1 -> 0, de event van het indrukken de drukknop, dan voeren we actie bij deze event uit. Deze actie hangt af van de toestand.

Voor de ingebouwde drukknoppen A en B heb je de functie `button.was_pressed()` die een dergelijke event detecteert. De functie `button.is_pressed()` geeft de actuele waarden: het *signaal* van de drukknop.

:::

:::{mchoice} Vraag over pinnen
:correct: a,b,c

Zet een vinkje bij de stelling(en) die waar zijn.

* Een pin op de micro:bit kan zowel input als output zijn.
* Een pin kan zowel digitale als analoge signalen verwerken.
* Computers werken met enen (1) en nullen (0). Je kunt voor de micro:bit zeggen: als er 0 volt op een pin staat is dat gelijk aan een 0. Als er 3 volt op een pin staat is dat gelijk aan een 1.
    * OK
