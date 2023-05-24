# Voorbeeld: aansluiten piezobuzzer

Met een piezo-buzzer kun je een alarm laten klinken of een muziekje laten horen. In dit deel laten we zien hoe je de piezo-buzzer kunt aansluiten. De piezo buzzer zit bij de uitvinderskit. Zie ook: https://www.kitronik.co.uk/blog/inventors-kit-experiment-6-help.

Mocht je geen piezo-buzzer hebben, dan kun je ook gebruikmaken van oortjes om geluid te laten (zie de afbeelding hieronder). Daarvoor heb je krokodillebekjes nodig. Zie ook het volgende filmpje over het maken van geluid met de Micro:bit.

<iframe width="560" height="315" src="https://www.youtube.com/embed/cxfPNc4Wefo" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

Voor het aansluiten van een een piezo-buzzer kun je het onderstaande schema gebruiken. Je ziet dat de piezo-buzzer is aangesloten op pin 2 (P2). Je ziet daarbij ook de aansluiting van de ultrasoonsensor. Je kunt echter ook prima eerst alleen de piezo-buzzer aansluiten en testen, zodat je aan deelprobleem 2 kunt werken.

:::{figure} figs/breadboard-buzzer.png
:width: 600

Breadboard met buzzer

:::

Met onderstaande programma kun je testen of de piezo-buzzer werkt. De micro:bit heeft allerlei melodietjes ingebouwd ( zie: https://microbit-micropython.readthedocs.io/en/latest/tutorials/music.html) Met de parameter `pin=pin2` geef je aan dat de piezo-buzzer op pin 2 is aangesloten.

```Python
from microbit import *
import music

music.play(music.NYAN, pin=pin2)
```

Je kunt ook je eigen melodie maken, bijvoorbeeld:

```Python
from microbit import *
import music

music.play(['c2:4', 'e:2', 'g:2', 'c3:4'], pin=pin2)
```

Voor het spelen van een toon op een bepaalde toonhoogte (frequentie) en duur gebruik je `music.pitch(freqency, duration)`, bijvoorbeeld:


```Python
from microbit import *
import music

music.pitch(440, pin=pin2)
```

Als het goed is hoor je een hoge toon bij het starten van het programma. De piezo-buzzer blijft nu de hele tijd aan. Om de piezo-buzzer uit te zetten gebruik je `music.stop()`, bijvoorbeeld: je het volgende blokje gebruiken.

```Python
from microbit import *
import music

music.pitch(440, pin=pin2)
sleep(1000)
music.stop(pin=pin2)
```

:::{admonition} Muziek op de microbit V2
Versie 2 van de micro:bit heeft een ingebouwde luidspreker (buzzer), deze kun je direct gebruiken voor bovenstaande voorbeelden. Je geeft dan geen pin-nummer op.
Met de functies `speaker.on()` en `speaker.off` kun je deze luidspreker aan- en uitzetten, bijvoorbeeld als je een externe buzzer of luidspreker wilt gebruiken.
:::