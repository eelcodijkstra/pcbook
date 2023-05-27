# Valdetectie

In het algemene deel van deze cyclus ({ref}`voorbeeld-valdetectie`) hebben een voorbeeld gegeven voor een valdetectiehorloge. Hier laten zien hoe je dat zelf kunt maken.

Het zijn eigenlijk twee aparte systemen die met elkaar communiceren. Op de micro:bit zit een zender en ontvanger waarmee je radio-signalen kunt versturen en ontvangen. Hieronder vind je een filmpje waarin dat wordt uitgelegd.

<iframe width="560" height="315" src="https://www.youtube.com/embed/Re3H2ISfQE8" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

We laten eerst zien hoe je het toestandsdiagram voor het horloge kunt omzetten in een micro:bit programma.

:::{figure} figs/toestandsdiagram-valdetectie-0.png

Toestandsdiagram 

:::

De gebeurtenissen zijn:

* gevallen -> op de micro:bit kun je detecteren of er wordt geschud met de micro:bit
* reset-knop ingedrukt -> hiervoor gebruiken we knop A.

Hieronder het programma. Bij het opstarten moet je aangeven in welke groep de radiosignalen moeten worden verzonden. Je kunt de micro:bit namelijk in verschillende groepen met elkaar laten communiceren.

```Python
from microbit import *
import radio

state = 1
radio.config(group=1)
radio.on()

while True:
    if accelerometer.was_gesture('shake'):
        if state == 1:
            state = 2
            radio.send("gevallen")
        
    if button_a.was_pressed():
        if state == 2:
            state = 1
            radio.send("ok")
```


:::{figure} figs/toestandsdiagram-valdetectie-1.png

Toestandsdiagram 

:::
 

Dan het systeem van degene die hulp moet gaan bieden.

```Python
from microbit import *
import radio

state = 1
radio.config(group=1)
radio.on()

while True:      
    if button_b.was_pressed():
        state = 1
        display.show(Image.HAPPY)
 
    msg = radio.receive()
    if msg == "gevallen":
        if state == 1:
            state = 2
            display.show(Image.SAD)
    elif msg == "ok":
        if state == 2:
            state = 1
            display.show(Image.HAPPY) 
```



De gebeurtenissen zijn:

* signaal "gevallen" ontvangen
* signaal "ok" ontvangen
* reset-knop ingedrukt -> hiervoor gebruiken we knop B

Je kunt deze twee programma's op twee verschillende micro:bits zetten en testen. Let er goed op dat de woorden ("gevallen" en "OK") die worden verstuurd en ontvangen op beide systemen precies gelijk zijn, het is hoofdlettergevoelig.

