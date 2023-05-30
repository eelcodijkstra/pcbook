# Stap 1: aansluiten en testen van de PIR-sensor

Het doel van deze opdracht is om een PIR-sensor aan te sluiten en te testen. Daarvoor moet je weten hoe de PIR-sensor precies kan worden gekoppeld aan de Micro:bit.

:::{exercise} Gegevens PIR-sensor

Zoek op internet een datasheet van de PIR-sensor die jij gebruikt. Het typenummer van de PIR-sensor die wij gebruiken is: HC-SR501. Als jij hetzelfde type PIR-sensor gebruikt kun je op dat typenummer zoeken. In het engels heet het: PIR motion sensor of PIR motion detector. PIR staat voor Pyroelectric InfraRed. Zie ook:

https://learn.adafruit.com/pir-passive-infrared-proximity-motion-sensor/how-pirs-work

Noteer de volgende eigenschappen:

1. Spanning waarop de PIR sensor werkt
2. De stroomsterkte die de PIR sensor zal afnemen
3. De verschillende aansluitingen
4. Wat verandert er bij het detecteren van een beweging?
5. Wat kun je instellen aan de PIR sensor? (Wat kun je doen met de twee schroefjes op de PIR-sensor?)
6.  De hoek waaronder de PIR sensor beweging kan detecteren
7. De afstand waarbinnen hij nog beweging kan detecteren
7. Wat is het verschil tussen H-mode en L-mode?

:::

Bij het aansluiten van een externe sensor of actuator is het belangrijk om er zeker van te zijn dat deze goed werkt en dat te testen voordat je verder gaat.

Zoals je waarschijnlijk hebt gezien, werkt de sensor op 5 tot 20 V. De micro:bit geeft echter slecht 3V af. Daarom hebben we een externe voedingsbron nodig. Gebruik daarvoor een batterijhouder met 3 AAA-batterijen. Die geeft 4,5 V af, dat is eigenlijk nog te weinig, maar het blijkt toch voldoende te zijn om de PIR-sensor te laten werken.

Bouw de schakeling zoals hieronder. Sluit de Micro:bit aan op de computer via USB. Let op: vergeet niet de zwarte verbinding aan de linkerkant.



 

Nu moeten we testen of de PIR-sensor werkt. Om goed te kunnen testen kun je het beste:

de vertraging van de PIR-sensor (time delay) op z'n laagst zetten
de trigger op repeatable zetten: zorg dat de jumper in de H-mode staat. Op internet vind je overigens tegenstrijdige informatie over wat de L-mode is en wat de H-mode is. Zorg dat je zoekt op het juiste type.
De eenvoudigste manier om te testen is door de output van de sensor op de een of andere manier weer te geven. Dat kan met het volgende eenvoudige programma.



Test het programma en de werking van de sensor. Wanneer verschijnt er een 0? Wanneer een 1? Wat gebeurt er als je de instellingen (gevoeligheid en vertraging) van de PIR-sensor aanpast? Wat gebeurt er als je de trigger aanpast (L-mode of H-mode)?

Wees je er van bewust dat de PIR-sensor steeds even tijd nodig heeft bij het opstarten. Ook zal de PIR-sensor bij het overgaan van HIGH (1) naar LOW (0) minstens 3 seconden op LOW blijven, voordat de output weer HIGH kan worden (als er een beweging wordt gedetecteerd).

Je kunt het programma ook testen met een seriele verbinding.