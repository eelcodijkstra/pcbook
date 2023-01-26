# Je eerste Python programma voor de Micro:bit

Je kunt met de Micro:bit al heel snel je eerste programma maken, bijvoorbeeld een knipperend hartje. Daarvoor heb je geen sensoren nodig.

:::{margin}
WebUSB wordt niet ondersteund door FireFox of Safari.
:::

We gebruiken hieronder de online Python editor voor de microbit. Deze kun je het beste gebruiken met een browser die WebUSB ondersteunt, zoals de recente versies van Chrome of Edge. 

Deze editor vind je op: https://python.microbit.org/v/3.
Je krijgt dan het volgende scherm:

:::{figure} figs/microbit-python-editor-1.png
:width: 600

Online Python editor voor de microbit
:::

Stap 1. Voer het programma in.

* ga naar de website https://python.microbit.org/v/3
* selecteer alle tekst in het edit-venster, en verwijder deze.
* kopieer de onderstaande programmatekst (knopje rechtsboven), en plak die in het edit-venster

```Python
from microbit import *

while True:
    display.show(Image.HEART_SMALL)
    sleep(500)
    display.show(Image.HEART)
    sleep(500)
```

Stap 2. Voer het programma uit in de simulator

* klik op de "run" knop: het driehoekje midden in het simulator-venster. Als het goed is, zie je nu een "kloppend hart" op een gesimuleerde microbit.
* je kunt de simulator stoppen met de stop-knop: het vierkantje onder de simulator

Stap 3. Voer het programma uit op de microbit

* verbind je microbit met een USB-poort van je computer
* klik op de knop "Send to microbit" onderaan en volg de aanwijzingen op het scherm
* via WebUSB wordt het programma direct op de microbit geladen en uitgevoerd.

Als je een andere browser gebruikt, heb je wat meer stappen nodig:

* de knop "Send to microbit" stuurt een programma-bestand naar je computer (in de Download-map);
* op je computer is de microbit zichtbaar als een extern opslagapparaat ("schijf", vgl. een USB-stick);
* op je computer sleep je het programma-bestand van de Download-map naar de microbit-schijf. Het wordt dan op de microbit geladen en direct uitgevoerd.

Als het programma op de microbit geladen is, dan kun je dit ook zonder computer uitvoeren:

* maak je microbit los van de computer
* verbind je microbit met een zelfstandige voeding: een batterij, een USB "powerbank", of een USB-netvoeding.
* het programma wordt direct uitgevoerd, zodra de microbit opstart.
 
Stap 4. Bewaar het programma ("project") op je computer

* geef het project een naam (boven het edit-venster), bijvoorbeeld "kloppend-hart"
* klik op "Save" onderaan het editvenster. Het ("hex")bestand wordt nu naar je computer gestuurd (download map).
* je kunt het bestand een volgende keer in de editor laden met de "Open" knop onderaan het edit-venster.
* je kunt het bestand ook op de microbit laden: dan wordt het direct uitgevoerd.



Opdracht Maak twee projecten na

Je gaat nu de Micro:bit verder verkennen. Werk in tweetallen. Kies twee projecten van de site https://makecode.microbit.org/# en bouw deze na in de Micro:bit.

Programmeeromgeving Micro:bit

Hieronder vind je een overzicht van de programmeeromgeving van de Micro:bit en een korte uitleg van de belangrijkste onderdelen.


## De programmeeromgeving van de Micro:bit
 

1. Start. Als je terugwilt naar het overzicht jouw projecten en voorbeelden van andere projecten.

2. Zoek je hulp, bijvoorbeeld over de werking van de verschillende blokken, kijk dan hier.

3. Bij de instellingen kun je onder meer de taal instellen.

4. In de simulatie-omgeving kun je je programma testen zonder dat je het eerst hoeft te downloaden.

5. Dit zijn de blokken waarmee je kunt programmeren. Als je een specifiek blok zoekt kan het helpen te kijken naar de kleur van het blok.

6. Je maakt een programma door de blokken naar de programmeeromgeving te slepen.

7. Hier kun je je programma downloaden zodat je het op je Micro:bit kunt zetten.

8. Sla je programma op onder een duidelijke naam zodat je het later makkelijk terug kunt vinden in je projecten overzicht.

Welke blokken gebruik je?

Je kunt de Micro:bit programmeren met behulp van de blokken. Een blok dat je bijna altijd gebruikt is het blok . Alles wat in dit blok staat wordt continu opnieuw door de Micro:bit uitgevoerd. Als je iets maar één keer wilt laten uitvoeren bij het opstarten van de Micro:bit gebruik je het blok .

Als je een keuze wilt programmeren (als-dan of als-dan-anders) dan gebruik je de blokken die staan bij . Voor herhalingen kijk je bij . Als je wilt dat er iets gebeurt op het moment dat de Micro:bit wordt geschud, gebruik je het blokje 

Controleer antwoord 