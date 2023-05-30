# Ultrasone afstandssensor

Ultrasoonsensoren werken met geluid dat niet hoorbaar is voor mensen. De bekendste toepassing zoals we die in het dagelijks leven tegenkomen is ongetwijfeld de parkeersensor. Er zitten daarbij meerdere ultrasoonsensoren in de bumper van een auto gemonteerd. Als je te dicht bij een andere auto, een muurtje of een paaltje komt klinkt er een alarm.

:::{figure} figs/ultrasone-sensor.jpg
:width: 300
:align: center

Ultrasone sensor
:::

De ultrasoonsensor zendt geluid uit en vangt de weerkaatsing van dat geluid weer op. Op die manier kun je bepalen wat de afstand is tot een object. Het lijkt op hoe vleermuizen hun omgeving waarnemen. Ook vleermuizen maken voor mensen onhoorbaar geluid.

:::{figure} figs/vleermuis.jpg
:width: 300
:align: center

Vleermuis
Bron: https://nl.wikipedia.org/wiki/Vleermuizen#/media/File:Big-eared-townsend-fledermaus.jpg
:::

:::{exercise} Kwaliteit van de ultrasoonsensor

De afbeelding van de ultrasoonsensor hierboven is van het type HC-SR04. Achterhaal het bereik en de nauwkeurigheid van de ultrasoonsensor HC-SR04 op basis van de datasheet. Het gaat met name om de volgende vragen:

Bereik:

1. Wat is de afstand waarbinnen de ultrasone afstandssensor een voorwerp kan detecteren?
2. Wat is de hoek waarbinnen de ultrasone afstandssensor een voorwerp kan detecteren.

Nauwkeurigheid:

1. Hoe nauwkeurig zijn de gegevens die de sensor oplevert?

Hieronder vind je twee links naar datasheets over de HC-SR04 Ultrasoonsensor.

* https://cdn.sparkfun.com/datasheets/Sensors/Proximity/HCSR04.pdf
* https://www.mpja.com/download/hc-sr04_ultrasonic_module_user_guidejohn.pdf

:::


:::{shortanswer} Vraag: infrarood of ultrasoonsensor

Waarom is het niet verstandig om voor een parkeersensor een (passieve) infraroodsensor te gebuiken?

:::

:::{shortanswer} Vraag: afstand berekenen

Een ultrasone sensor geeft een geluidsignaal en vangt dit 1 milliseconde later weer op. Op hoeveel centimeter afstand bevindt zich een object dat dit geluidssignaal weerkaatst?

:::

## Aansluiten en programmeren van de piezo-buzzer

In de inleiding Micro:bit laten we zien hoe je een piezo-buzzer kunt aansluiten. 

:::{exercise} Werk deelprobleem 2 uit tot een werkend programma

Sluit de piezo-buzzer aan en maak op basis van de toestandsdiagrammen die je eerder hebt gemaakt een werkend systeem. Werk in kleine stapjes: eerst deelprobleem 2a, dan deelprobleem 2b, etc).

:::

