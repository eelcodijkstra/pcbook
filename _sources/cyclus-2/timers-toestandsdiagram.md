# Toestandsdiagram met timer

Uit het voorbeeld met de PIR-sensor blijkt dat er een soort klokje in de sensor zit verwerkt. De sensor blijft een tijdje HIGH als output geven, ook al loopt er niemand meer voorbij. Je kunt echter ook zelf zo'n klokje programmeren, dat noemen we een *timer*. In dit hoofdstuk leer je om zelf een timer te gebruiken.


:::{figure} figs/kookwekker.jpg
:width: 150
:align: right

Kookwekker  
FreeImages.com/  
Pierre Amerlynck

:::

Een timer is een soort kookwekker. Je kunt de wekker instellen zodat deze over een bepaalde tijd, bijvoorbeeld 5 minuten, afloopt en dan een bel of alarm laat horen. Zo is het ook met een timer, alleen gaat het meestal niet om minuten, maar om seconden of zelfs miliseconden.

Hoe kun je een timer in een toestandsdiagram gebruiken? Daarvoor heb je een actie en een gebeurtenis nodig. Dit is de actie die je kunt gebruiken voor een timer:

* start timer / reset timer

Als je het vergelijkt met een kookwekker: stel de wekker in, bijvoorbeeld op 10 seconden van nu. Resetten betekent dat je de timer weer terugzet naar de oorspronkelijke tijd nog voordat de timer is afgelopen. Het resetten van de timer is eigenlijk hetzelfde als het starten van de timer, daarom hebben we ze bij elkaar gezet.

Een gebeurtenis die hoort bij de timer is:

* timer loopt af

Als je het vergelijkt met een kookwekker: de kookwekker laat een bel of alarm horen.

Hieronder vind je een voorbeeld voor het systeem met de lantaarnpaal.

:::{figure} figs/diagram-beweging-lamp-timer.png
:width: 700
:align: center

Toestandsdiagram met timer

::: 

* Toestand 1: lamp is uit
* Toestand 2: lamp is aan

## Waarom timers?

Los van deze toepassing met de lantaarnpaal is het belangrijk dat je timers leert gebruiken. Het is belangrijk om het verschil tussen een *timer* en een *pauze* te begrijpen. Een pauze bij de lantaarnpaal zou als volgt werken. Nadat een beweging is gedetecteerd zet het systeem de lamp aan. Daarna komt een pauze van bijvoorbeeld 10 seconden. In die 10 seconden doet het systeem echter helemaal niets en kan het dus ook niet reageren op input vanuit de omgeving. Bij een lantaarnpaal is dat misschien niet zo erg, maar stel je hebt een zelfrijdende auto. Die zou tijdens de pauze nergens op reageren, dus ook niet op andere sensoren die aangeven dat er een andere auto aankomt. Levensgevaarlijk dus.

Bij een pauze reageert het systeem nergens meer op. Bij een timer is dat anders, die werkt als een kookwekker. Het systeem gaat gewoon door terwijl de seconden op de kookwekker wegtikken. Op het moment dat de kookwekker afgaat, kan het systeem actie ondernemen.