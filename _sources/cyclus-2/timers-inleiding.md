(timers-theorie)=
# Timers

De PIR (passieve infrarood) bewegingssensor geeft als output een HIGH (of 1) als deze een beweging detecteert; als er geen beweging is geeft de sensor als output LOW (of 0). Je kunt de gevoeligheid en de vertraging van de sensor aanpassen met de instelpotmeters, zoals in de figuur hieronder is te zien. De vertraging is de tijd voordat het signaal LOW wordt, na de laatst gedetecteerde beweging.

:::{figure} figs/pir-sensor-instellingen.png
:width: 300
:align: center

Instellingen van een PIR-sensor

:::

De hoofdopdracht voor deze cyclus is het maken van lantaarnpaal waarvan het licht gaat branden als er iemand langsloopt. Het licht van een lantaarnpaal moet aan gaan als een beweging wordt gedetecteerd en weer uit als er geen beweging meer is. Je kunt dat als volgt in een toestandsdiagram weergeven.

:::{figure} figs/diagram-beweging-lamp.png
:width: 600
:align: center

Toestandsdiagram lamp

:::

 

* Toestand 1: lamp staat uit
* Toestand 2: lamp staat aan

Het hangt van de instelpotmeter op de PIR-sensor af hoe lang het duurt voordat de lamp weer uitgaat. Je kunt de situatie weergeven in een tabel zoals hieronder. Deze tabel is nog niet volledig ingevuld.

:::{fillintheblank}

| Wat gebeurt er? | Lamp aan of uit? | Toestand?  |
| :--: | :--: | :--: |
| Niemand in de buurt | Lamp is uit | Toestand 1 |
| Een fietser komt langs | {blank}`aan` | {blank}`2` |
| De fietser is net weg | {blank}`aan` | {blank}`2` |
| Het is een tijdje stil | {blank}`uit` |{blank}`1` |

* dummy

:::